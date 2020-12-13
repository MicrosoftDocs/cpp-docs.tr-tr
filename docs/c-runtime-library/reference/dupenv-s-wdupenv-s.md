---
description: 'Hakkında daha fazla bilgi edinin: _dupenv_s _wdupenv_s'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 3163645b83ec701478cca76d98fe5e17acdc86d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332882"
---
# <a name="_dupenv_s-_wdupenv_s"></a>_dupenv_s, _wdupenv_s

Geçerli ortamdan bir değer alır.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*arabelleğin*<br/>
Değişkenin değerini depolayan arabellek.

*numberOfElements*<br/>
*Arabelleğin* boyutu.

*varname*<br/>
Ortam değişkeni adı.

## <a name="return-value"></a>Dönüş Değeri

Başarı durumunda sıfır, hata durumunda hata kodu.

Bu işlevler parametrelerini doğrular; *buffer* veya *varname* **null** ise, [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlevler **errno** olarak **EINVAL** ve **EINVAL** döndürür.

Bu işlevler yeterli bellek ayıramıyorsa, *buffer* 'ı null ve *numberOfElements* **değeri** 0 olarak ayarlar ve **ENOMEM** döndürür.

## <a name="remarks"></a>Açıklamalar

**_Dupenv_s** işlevi, *varname* için ortam değişkenlerinin listesini arar. Değişken bulunursa **_dupenv_s** bir arabellek ayırır ve değişkenin değerini arabelleğe kopyalar. Arabelleğin adresi ve uzunluğu, *buffer* ve *numberOfElements*' de döndürülür. Arabelleği ayırarak **_dupenv_s** , [_wgetenv_s getenv_s](getenv-s-wgetenv-s.md)daha uygun bir alternatif sağlar.

> [!NOTE]
> Bu, [ücretsiz](free.md)olarak arayarak belleği boşaltmak için çağıran programın sorumluluğundadır.

Değişken bulunamazsa, *buffer* **null** olarak ayarlanır, *numberOfElements* 0 olarak ayarlanır ve bu durum bir hata durumu olarak değerlendirilmediği için dönüş değeri 0 ' dır.

Arabelleğin boyutuyla ilgilenmiyorsanız *numberOfElements* Için **null değeri** geçirebilirsiniz.

**_Dupenv_s** Windows işletim sisteminde büyük küçük harfe duyarlı değildir. **_dupenv_s** , ortama erişmek için **_environ** genel değişken tarafından işaret edilen ortamın kopyasını kullanır. **_Environ** tartışmak için [getenv_s _wgetenv_s](getenv-s-wgetenv-s.md) açıklamaları bölümüne bakın.

*Buffer* değeri, ortam değişkeninin değerinin bir kopyasıdır; Bunun değiştirilmesi, ortam üzerinde hiçbir etkiye sahip değildir. Bir ortam değişkeninin değerini değiştirmek için [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md) işlevini kullanın.

**_wdupenv_s** , **_dupenv_s** geniş karakterli bir sürümüdür; **_wdupenv_s** bağımsız değişkenleri geniş karakterli dizelerdir. **_Wenviron** genel değişkeni, **_environ** geniş karakterli bir sürümüdür. **_Wenviron** hakkında daha fazla bilgi için [getenv_s _wgetenv_s](getenv-s-wgetenv-s.md) açıklamaları bölümüne bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s**|**_dupenv_s**|**_dupenv_s**|**_wdupenv_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_dupenv_s**|\<stdlib.h>|
|**_wdupenv_s**|\<stdlib.h> veya \<wchar.h>|

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

[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[Çevresel sabitler](../../c-runtime-library/environmental-constants.md)<br/>
[_dupenv_s_dbg, _wdupenv_s_dbg](dupenv-s-dbg-wdupenv-s-dbg.md)<br/>
[getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)<br/>
[_putenv_s, _wputenv_s](putenv-s-wputenv-s.md)<br/>
