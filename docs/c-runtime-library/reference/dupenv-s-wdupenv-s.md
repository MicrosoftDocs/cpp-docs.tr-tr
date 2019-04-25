---
title: _dupenv_s, _wdupenv_s
ms.date: 11/04/2016
apiname:
- _dupenv_s
- _wdupenv_s
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: bc8af3282b57c9fa411aac97f5fa4d414bc3305b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288868"
---
# <a name="dupenvs-wdupenvs"></a>_dupenv_s, _wdupenv_s

Geçerli ortamdan bir değer alır.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Değişken değerini depolayan arabellek.

*numberOfElements*<br/>
Boyutu *arabellek*.

*varName*<br/>
Ortam değişkeni adı.

## <a name="return-value"></a>Dönüş Değeri

Başarı, bir hata kodu sıfır.

Bu işlevler kendi parametrelerini doğrular; varsa *arabellek* veya *varname* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse işlevler **errno** için **EINVAL** ve dönüş **EINVAL**.

Bu işlevler yeterli bellek ayıramıyorsa, ayarladıkları *arabellek* için **NULL** ve *numberOfElements* 0'dönüş **ENOMEM**.

## <a name="remarks"></a>Açıklamalar

**_Dupenv_s** işlevi için ortam değişkenleri listesi arar *varname*. Değişken bulunamıyorsa **_dupenv_s** bir arabelleği ayırır ve değişken değerini arabelleğe kopyalar. Arabelleğin adresi ve uzunluğu, döndürülen *arabellek* ve *numberOfElements*. Arabelleğin kendisini ayırarak tarafından **_dupenv_s** daha uygun bir alternatif sağlayan [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

> [!NOTE]
> Bunu çağırarak belleğin boşaltılması arama programının sorumluluğundadır [ücretsiz](free.md).

Değişkeni, ardından bulunamazsa *arabellek* ayarlanır **NULL**, *numberOfElements* 0 olarak ayarlanır ve bu durum bir hata olarak kabul edilmediğinden dönüş değeri 0'dır Koşul.

Arabellek boyutu ilgilenmiyorsanız geçirebilirsiniz **NULL** için *numberOfElements*.

**_dupenv_s** Windows işletim sistemi büyük/küçük harfe duyarlı değildir. **_dupenv_s** için genel değişkeni tarafından işaret edilen ortamın kopyasını kullanır **_environ** ortama erişmek için. Konusundaki yorumlara bakın [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md) bir irdelemesi **_environ**.

Değer *arabellek* ; ortam değişkeni değerinin bir kopyasıdır değiştirmeye, ortam üzerinde hiçbir etkisi vardır. Kullanım [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md) bir ortam değişkeninin değerini değiştirmek için işlevi.

**_wdupenv_s** geniş karakterli sürümüdür **_dupenv_s**; bağımsız değişkenleri **_wdupenv_s** geniş karakterli dizelerdir. **_Wenviron** genel değişkeni, bir geniş karakter sürümünü **_environ**. Konusundaki yorumlara bakın [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md) hakkında daha fazla bilgi **_wenviron**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s**|**_dupenv_s**|**_dupenv_s**|**_wdupenv_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_dupenv_s**|\<stdlib.h >|
|**_wdupenv_s**|\<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
[Ortam Sabitleri](../../c-runtime-library/environmental-constants.md)<br/>
[_dupenv_s_dbg, _wdupenv_s_dbg](dupenv-s-dbg-wdupenv-s-dbg.md)<br/>
[getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)<br/>
[_putenv_s, _wputenv_s](putenv-s-wputenv-s.md)<br/>
