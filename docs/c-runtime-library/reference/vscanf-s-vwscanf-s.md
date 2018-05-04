---
title: vscanf_s, vwscanf_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- vscanf_s
- vwscanf_s
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
- _vtscanf_s
- vscanf_s
- vwscanf_s
dev_langs:
- C++
ms.assetid: 23a1c383-5b01-4887-93ce-534a1e38ed93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c32d1e50f554c32917f9fa0450abba15463386ab
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="vscanfs-vwscanfs"></a>vscanf_s, vwscanf_s

Standart giriş akışı verileri okuma biçimlendirilmiş. Bu sürümleri [vscanf, vwscanf](vscanf-vwscanf.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
int vscanf_s(
   const char *format,
   va_list arglist
);
int vwscanf_s(
   const wchar_t *format,
   va_list arglist
);
```

### <a name="parameters"></a>Parametreler

*Biçimi*<br/>
Biçim denetim dizesi.

*arglist*<br/>
Değişken bağımsız değişken listesi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı bir şekilde dönüştürülür ve atanan alan sayısını döndürür; dönüş değerini okumak ancak atanmamış alanları içermez. Dönüş değeri 0, hiçbir alan atandığını belirtir. Dönüş değeri **EOF** bir hata için veya dosya sonu karakteri veya dize son karakter bir karakter okumak için ilk deneme karşılaştıysanız. Varsa *biçimi* olan bir **NULL** işaretçi, geçersiz parametre işleyicisi çağrılır, açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **vscanf_s** ve **vwscanf_s** dönmek **EOF** ve **errno** için **EINVAL**.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Vscanf_s** işlevi standart giriş akışından veri okuyan **stdin** ve tarafından verilen konumları verileri Yazar *arglist* bağımsız değişken listesi. Listedeki her bir bağımsız değişkeni bir tür belirteci karşılık gelen bir türde bir değişken için bir işaretçi olmalıdır *biçimi*. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

**vwscanf_s** bir joker karakter sürümü **vscanf_s**; *biçimi* bağımsız değişkeni **vwscanf_s** bir joker karakter dizesidir. **vwscanf_s** ve **vscanf_s** akış ANSI modunda açılırsa aynı şekilde davranır. **vscanf_s** UNICODE akışı girişten desteklemiyor.

Farklı **vscanf** ve **vwscanf**, **vscanf_s** ve **vwscanf_s** tüm giriş parametreleri türü için belirtilen arabellek boyutu gerektirir **c**, **C**, **s**, **S**, veya dize içine denetim kümeleri **[]**. Arabellek boyutu karakter cinsinden işaretçinin arabellek veya değişken hemen ardından ek bir parametre olarak geçirilir. Arabellek boyutu için karakter cinsinden bir **wchar_t** dizesi bayt cinsinden boyutu ile aynı değil.

Arabellek boyutu sonlandırma null içerir. Genişlik belirtimi alan okunduktan belirteci belleğe sığmayacak emin olmak için kullanabilirsiniz. Genişlik belirtimi alan kullanılır ve okunan belirteci arabellek sığmayacak kadar büyük ise, hiçbir şey bu arabelleğe yazılır.

> [!NOTE]
> *Boyutu* parametredir türü **imzasız**değil **size_t**.

Daha fazla bilgi için bkz: [sacnf genişlik belirtimi](../../c-runtime-library/scanf-width-specification.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vtscanf_s**|**vscanf_s**|**vscanf_s**|**vwscanf_s**|

Daha fazla bilgi için bkz: [biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**vscanf_s**|\<stdio.h >|
|**wscanf_s**|\<stdio.h > veya \<wchar.h >|

Konsol Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsol ile ilişkili standart akış tanıtıcıları **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri UWP uygulamalarında kullanabilmek için önce yeniden yönlendirilmesi gerekiyor . Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_vscanf_s.c
// compile with: /W3
// This program uses the vscanf_s and vwscanf_s functions
// to read formatted input.

#include <stdio.h>
#include <stdarg.h>
#include <stdlib.h>

int call_vscanf_s(char *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vscanf_s(format, arglist);
    va_end(arglist);
    return result;
}

int call_vwscanf_s(wchar_t *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vwscanf_s(format, arglist);
    va_end(arglist);
    return result;
}

int main( void )
{
    int   i, result;
    float fp;
    char  c, s[81];
    wchar_t wc, ws[81];
    result = call_vscanf_s("%d %f %c %C %s %S", &i, &fp, &c, 1,
                           &wc, 1, s, _countof(s), ws, _countof(ws) );
    printf( "The number of fields input is %d\n", result );
    printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c, wc, s, ws);
    result = call_vwscanf_s(L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,
                            &wc, 1, s, _countof(s), ws, _countof(ws) );
    wprintf( L"The number of fields input is %d\n", result );
    wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp, c, wc, s, ws);
}
```

Bu program örnekte giriş verildiğinde bu çıkışı üretir:

```Input
71 98.6 h z Byte characters
36 92.3 y n Wide characters
```

```Output
The number of fields input is 6
The contents are: 71 98.599998 h z Byte characters
The number of fields input is 6
The contents are: 36 92.300003 y n Wide characters
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[vscanf, vwscanf](vscanf-vwscanf.md)<br/>
