# query_id-blum

Anda bisa membuat bookmark dengan nama "query_id sercher" dengan langkah-langkah berikut:

1. Buka bookmark manager di browser Anda.
2. Buat bookmark baru dan beri nama "query_id sercher".
3. Salin kode di bawah ini ke dalam bidang URL:

```javascript
javascript:(function(){
    document.querySelectorAll('iframe').forEach(function(iframe, index){
        const iframeUrl = new URL(iframe.src);
        const params = new URLSearchParams(iframeUrl.hash.substring(1));
        const tgWebAppData = params.get('tgWebAppData');
        if(tgWebAppData){
            const queryId = tgWebAppData.split('&')[0].split('=')[1];
            alert('Query ID: ' + queryId);
        } else {
            alert('tgWebAppData tidak ditemukan di Iframe ' + index);
        }
    });
})();
```

4. Simpan bookmark tersebut.

Sekarang Anda bisa menggunakan bookmark "query_id sercher" pada halaman yang relevan untuk mendapatkan `query_id`.
