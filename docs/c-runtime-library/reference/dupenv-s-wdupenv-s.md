---
title: _dupenv_s, _wdupenv_s
ms.date: 4/2/2020
api_name:
- _dupenv_s
- _wdupenv_s
- _o__dupenv_s
- _o__wdupenv_s
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- tdupenv_s
- _dupenv_s
- wdupenv_s
- dupenv_s
- _tdupenv_s
- _wdupenv_s
helpviewer_keywords:
- _dupenv_s function
- _tdupenv_s function
- _wdupenv_s function
- environment variables
- wdupenv_s function
- dupenv_s function
- tdupenv_s function
ms.assetid: b729ecc2-a31d-4ccf-92a7-5accedb8f8c8
ms.openlocfilehash: f65f1da3e8cef077df04d0bdb7eb2aaf75afd9fa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348065"
---
# <a name="_dupenv_s-_wdupenv_s"></a>_dupenv_s, _wdupenv_s

Geçerli ortamdan bir değer alır.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _dupenv_s(
   char **buffer,
   size_t *numberOfElements,
   const char *varname
);
errno_t _wdupenv_s(
   wchar_t **buffer,
   size_t *numberOfElements,
   const wchar_t *varname
);
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Değişkenin değerini depolamak için arabellek.

*numberOfElements*<br/>
*Arabellek*boyutu.

*Varname*<br/>
Çevre değişken adı.

## <a name="return-value"></a>Dönüş Değeri

Sıfır başarı, başarısızlık bir hata kodu.

Bu işlevler parametrelerini doğrular; *arabellek* veya *varname* **NULL**ise, geçersiz parametre işleyicisi [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, işlevleri **EINVAL** **için errno** ayarlayın ve **EINVAL**döndürün.

Bu işlevler yeterli bellek ayıramıyorsa, *arabelleği* **NULL'a** ayarlarlar ve *OfElements'i* 0'a ayarlarlar ve **ENOMEM'i**döndürürler.

## <a name="remarks"></a>Açıklamalar

**_dupenv_s** işlevi *varname*için ortam değişkenleri listesini arar. Değişken bulunursa, **_dupenv_s** bir arabellek ayırır ve değişkenin değerini arabelleğe kopyalar. Arabelleğe'nin adresi ve uzunluğu *arabellek* ve *numaraOfElements*döndürülür. Arabellek kendisi ayırarak, **_dupenv_s** [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)için daha uygun bir alternatif sağlar.

> [!NOTE]
> Ücretsiz [arayarak](free.md)belleği boşaltmak arama programının sorumluluğudur.

Değişken bulunmazsa, *arabellek* **NULL**olarak ayarlanır, *numberOfElements* 0 olarak ayarlanır ve bu durum bir hata koşulu olarak kabul edilmez, çünkü dönüş değeri 0'dır.

Arabelleğen boyutuyla *ilgilenmiyorsanız, numberOfElements*için **NULL'u** geçebilirsiniz.

**_dupenv_s** Windows işletim sisteminde büyük/küçük harf duyarlı değildir. **_dupenv_s,** ortama erişmek için küresel değişken **_environ** işaret ettiği ortamın kopyasını kullanır. _environ tartışmak için [_wgetenv_s getenv_s'daki](getenv-s-wgetenv-s.md) **Açıklamalar'a**bakın.

*Arabellekteki* değer, ortam değişkeninin değerinin bir kopyasıdır; değiştirilmesinin ortam üzerinde hiçbir etkisi yoktur. Bir ortam değişkeninin değerini değiştirmek için [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md) işlevini kullanın.

**_wdupenv_s** **_dupenv_s**geniş karakterli bir versiyonudur; **_wdupenv_s** bağımsız değişkenleri geniş karakterli dizeleri dir. **_wenviron** global **değişken, _environ**geniş karakterli bir sürümüdür. **getenv_s'daki Açıklamalar'a** [bakın,](getenv-s-wgetenv-s.md) _wenviron hakkında daha fazla _wgetenv_s.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s**|**_dupenv_s**|**_dupenv_s**|**_wdupenv_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_dupenv_s**|\<stdlib.h>|
|**_wdupenv_s**|\<stdlib.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_dupenv_s.c
#include  <stdlib.h>

int main( void )
{
   char *pValue;
   size_t len;
   errno_t err = _dupenv_s( &pValue, &len, "pathext" );
   if ( err ) return -1;
   printf( "pathext = %s\n", pValue );
   free( pValue );
   err = _dupenv_s( &pValue, &len, "nonexistentvariable" );
   if ( err ) return -1;
   printf( "nonexistentvariable = %s\n", pValue );
   free( pValue ); // It's OK to call free with NULL
}
```

```Output
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl
nonexistentvariable = (null)
```

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[Çevre Sabitleri](../../c-runtime-library/environmental-constants.md)<br/>
[_dupenv_s_dbg, _wdupenv_s_dbg](dupenv-s-dbg-wdupenv-s-dbg.md)<br/>
[getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)<br/>
[_putenv_s, _wputenv_s](putenv-s-wputenv-s.md)<br/>
