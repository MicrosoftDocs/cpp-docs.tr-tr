---
title: _cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l
ms.date: 11/04/2016
apiname:
- _cwprintf_s_l
- _cprintf_s_l
- _cprintf_s
- _cwprintf_s
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
apitype: DLLExport
f1_keywords:
- _cwprintf_s_l
- _cprintf_s
- cwprintf_s
- _cprintf_s_l
- cwprintf_s_l
- cprintf_s_l
- _tcprintf_s
- cprintf_s
- _cwprintf_s
- tcprintf_s
helpviewer_keywords:
- tcprintf_s_l function
- _cprintf_s_l function
- _cwprintf_s_l function
- tcprintf_s function
- _tcprintf_s_l function
- _cwprintf_s function
- cwprintf_s function
- _cprintf_s function
- cprintf_s function
- _tcprintf_s function
- cprintf_s_l function
- cwprintf_s_l function
ms.assetid: c28504fe-0d20-4f06-8f97-ee33225922ad
ms.openlocfilehash: 3652587c9622c2eb9fe316782d1b1c7c9644dc8f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606525"
---
# <a name="cprintfs-cprintfsl-cwprintfs-cwprintfsl"></a>_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l

Biçimlendirir ve konsola yazdırır. Bu sürümleri [_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _cprintf_s(
   const char * format [,
   argument] ...
);
int _cprintf_s_l(
   const char * format,
   locale_t locale [,
   argument] ...
);
int _cwprintf_s(
   const wchar * format [,
   argument] ...
);
int _cwprintf_s_l(
   const wchar * format,
   locale_t locale [,
   argument] ...
);
```

### <a name="parameters"></a>Parametreler

*Biçim*<br/>
Biçim denetimi dizesi.

*Bağımsız değişken*<br/>
İsteğe bağlı parametreler.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Yazdırılan karakter sayısı.

## <a name="remarks"></a>Açıklamalar

Bu işlevler biçimlendirmek ve bir dizi karakter ve değerlerini doğrudan konsola yazdırma kullanarak **_putch** işlevi (**_putwch** için **_cwprintf_s**) çıktı karakter. Her *bağımsız değişken* (varsa) dönüştürülür ve karşılık gelen kapsamındaki biçim belirtimine göre çıkışı *biçimi*. Biçim aynı form ve işleve sahip *biçimi* parametresi için [printf_s](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) işlevi. Farklı **fprintf_s**, **printf_s**, ve **sprintf_s** işlevlerinin **_cprintf_s** ya da **_cwprintf_s** satır besleme karakterlerini satır başı satır besleme (CR-LF) birleşimlerine çevirir çıkış.

Önemli bir ayrımdır olan **_cwprintf_s** Windows NT'de kullanıldığı zaman Unicode karakterleri görüntüler. Farklı **_cprintf_s**, **_cwprintf_s** geçerli konsol yerel ayarlarını kullanır.

Sahip bu işlevlerin sürümleri **_l** sonekine, geçerli yerel ayarı yerine iletilen yerel ayar parametresini kullanmalarıdır.

> [!IMPORTANT]
> Emin *biçimi* kullanıcı tanımlı bir dize değil.

Güvenli olmayan sürümler gibi (bkz [_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)), bu işlevler kendi parametrelerini doğrular ve açıklandığı gibi geçersiz parametre işleyicisini çağırır [parametredoğrulama](../../c-runtime-library/parameter-validation.md), *biçimi* bir null işaretçidir. Bu işlevlerin güvenli olmayan sürümlerden biçim dizesinin kendisinin de doğrulanması bakımından farklıdır. Tüm bilinmeyen veya hatalı oluşturulmuş biçimlendirme tanımlayıcıları varsa, bu işlevler geçersiz parametre işleyicisini çağırır. Her durumda yürütmenin devam etmesine izin verilirse işlevler -1 döndürür. ayarlayıp **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcprintf_s**|**_cprintf_s**|**_cprintf_s**|**_cwprintf_s**|
|**_tcprintf_s_l**|**_cprintf_s_l**|**_cprintf_s_l**|**_cwprintf_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_cprintf_s**, **_cprintf_s_l**|\<conio.h >|
|**_cwprintf_s**, **_cwprintf_s_l**|\<conio.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_cprintf_s.c
// compile with: /c
// This program displays some variables to the console.

#include <conio.h>

int main( void )
{
   int      i = -16, h = 29;
   unsigned u = 62511;
   char     c = 'A';
   char     s[] = "Test";

   /* Note that console output does not translate \n as
    * standard output does. Use \r\n instead.
    */
   _cprintf_s( "%d  %.4x  %u  %c %s\r\n", i, h, u, c, s );
}
```

```Output
-16  001d  62511  A Test
```

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](cscanf-cscanf-l-cwscanf-cwscanf-l.md)<br/>
[fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)<br/>
[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)<br/>
[vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)<br/>
[Biçim Belirtim Sözdizimi: printf ve wprintf İşlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
