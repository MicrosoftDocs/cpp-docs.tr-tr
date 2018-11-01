---
title: vscanf_s, vwscanf_s
ms.date: 11/04/2016
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
ms.assetid: 23a1c383-5b01-4887-93ce-534a1e38ed93
ms.openlocfilehash: 90100a5fbc03371a11f437acc12562d9ccf957f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519476"
---
# <a name="vscanfs-vwscanfs"></a>vscanf_s, vwscanf_s

Biçimlendirilmiş verileri standart giriş akışından okur. Bu sürümleri [vscanf, vwscanf](vscanf-vwscanf.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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

*Biçim*<br/>
Biçim Denetimi dizesi.

*arglist*<br/>
Değişken bağımsız değişken listesi.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla dönüştürülen ve atanan alanların sayısını döndürür; dönüş değeri, Okunmuş ancak atanmamış alanları içermez. 0 değeri hiçbir alan atanmamış belirtir. Dönüş değeri **EOF** bir hata için veya bir karakter okumak için yapılan ilk girişim dosya sonu karakteri veya dize sonu karakteri ile karşılaşılırsa. Varsa *biçimi* olduğu bir **NULL** işaretçiyse, geçersiz parametre işleyicisi çağrılır, açıklandığı [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **vscanf_s** ve **vwscanf_s** dönüş **EOF** ayarlayıp **errno** için **EINVAL**.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Vscanf_s** işlevi standart giriş akışından verileri okur **stdin** ve tarafından verilen konumlarda verileri Yazar *arglist* bağımsız değişken listesi. Listedeki her bağımsız değişken içinde bir tür belirleyiciye karşılık gelen bir tür bir değişken, bir işaretçi olmalıdır *biçimi*. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

**vwscanf_s** geniş karakterli sürümüdür **vscanf_s**; *biçimi* bağımsız değişkeni **vwscanf_s** geniş karakterli bir dizedir. **vwscanf_s** ve **vscanf_s** akış ANSI modunda açıldığında aynı şekilde davranır. **vscanf_s** UNICODE akışından girişi desteklemez.

Farklı **vscanf** ve **vwscanf**, **vscanf_s** ve **vwscanf_s** arabellek boyutu, tüm giriş parametreleri türü için belirtilmesi gerekir **c**, **C**, **s**, **S**, veya dize içine alınan denetim kümeleri **[]**. Karakter arabelleği boyutu, işaretçinin arabellek veya değişkene hemen ardından ek bir parametre olarak geçirilir. Karakter arabelleği boyutu bir **wchar_t** dizesi bayt cinsinden boyutu ile aynı değil.

Arabellek boyutu sondaki null karakterini içerir. Okunan belirtecin arabelleğe sığmasını sağlamak için bir genişlik belirtimi alanı kullanabilirsiniz. Hiçbir genişlik belirtimi alanı kullanılmazsa ve okunan belirteç arabelleğe sığamayacak kadar büyük ise, hiçbir şey o arabelleğe yazılır.

> [!NOTE]
> *Boyutu* parametre türüdür **işaretsiz**değil **size_t**.

Daha fazla bilgi için [scanf genişlik belirtimi](../../c-runtime-library/scanf-width-specification.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vtscanf_s**|**vscanf_s**|**vscanf_s**|**vwscanf_s**|

Daha fazla bilgi için [biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**vscanf_s**|\<stdio.h >|
|**wscanf_s**|\<stdio.h > veya \<wchar.h >|

Konsolu, Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsolları ile ilişkili standart akış işleyicileri **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri bunları UWP uygulamalarında kullanmadan önce yeniden yönlendirilmesi gerekiyor . Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

Bu program örnekte girdi verildiğinde Bu çıktıyı oluşturur:

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
[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[vscanf, vwscanf](vscanf-vwscanf.md)<br/>
