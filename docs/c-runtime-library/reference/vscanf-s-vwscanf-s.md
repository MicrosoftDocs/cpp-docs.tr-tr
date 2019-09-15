---
title: vscanf_s, vwscanf_s
ms.date: 11/04/2016
api_name:
- vscanf_s
- vwscanf_s
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _vtscanf_s
- vscanf_s
- vwscanf_s
ms.assetid: 23a1c383-5b01-4887-93ce-534a1e38ed93
ms.openlocfilehash: 4d08679d08fb5b212306cbaeec200d16803a85ef
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70945406"
---
# <a name="vscanf_s-vwscanf_s"></a>vscanf_s, vwscanf_s

Standart giriş akışından biçimlendirilen verileri okur. [Vscanf, mescanf](vscanf-vwscanf.md) 'nin bu SÜRÜMLERINDE, [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri vardır.

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

*format*<br/>
Biçim denetimi dizesi.

*Arglist*<br/>
Değişken bağımsız değişken listesi.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla dönüştürülen ve atanan alanların sayısını döndürür; dönüş değeri, okunan ancak atanmamış alanları içermez. 0 dönüş değeri hiçbir alan atanmadığını gösterir. Dönüş değeri bir hata için **EOF** veya ilk kez bir karakteri okumak için ilk denemede dosya sonu karakteri veya dize sonu karakteriyle karşılaşılırsa. *Biçim* **null** Işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **vscanf_s** ve **vwscanf_s** **EOF** döndürür ve **errno** öğesini **EINVAL**olarak ayarlayın.

Bu ve diğer hata kodları hakkında bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Vscanf_s** işlevi standart giriş akışı **stdin** ' den verileri okur ve verileri *Arglist* bağımsız değişken listesi tarafından verilen konumlara yazar. Listedeki her bağımsız değişken, *biçimdeki*bir tür belirticisine karşılık gelen bir tür değişkenine bir işaretçi olmalıdır. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

**vwscanf_s** , **vscanf_s**öğesinin geniş karakterli bir sürümüdür; vwscanf_s *Biçim* bağımsız değişkeni geniş karakterli bir dizedir. **vwscanf_s** ve **VSCANF_S** , akış ANSI modunda açılırsa aynı şekilde davranır. **vscanf_s** , UNICODE akışından girişi desteklemez.

**Vscanf** ve **cscanf**, **vscanf_s** ve **vwscanf_s** 'in aksine, **c**, **c**, **s**, **s**veya [] içindeki dize denetim kümeleri türündeki tüm giriş parametreleri için arabellek boyutunun belirtilmesini gerektirir. Karakterdeki arabellek boyutu, arabellek veya değişken işaretçisinin hemen ardından ek bir parametre olarak geçirilir. **Wchar_t** dizesinin karakter cinsinden arabellek boyutu bayt cinsinden boyutla aynı değildir.

Arabellek boyutu, Sonlandırıcı null değerini içerir. Okunan belirtecin arabelleğe sığmasını sağlamak için Width belirtim alanını kullanabilirsiniz. Bir genişlik belirtimi alanı kullanılmıyorsa ve okunan belirteç arabelleğe sığmayacak kadar büyük ise, bu arabelleğe hiçbir şey yazılmaz.

> [!NOTE]
> *Boyut* parametresi, **size_t**değil, **işaretsiz**türündedir.

Daha fazla bilgi için bkz. [scanf Width belirtimi](../../c-runtime-library/scanf-width-specification.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vtscanf_s**|**vscanf_s**|**vscanf_s**|**vwscanf_s**|

Daha fazla bilgi için bkz. [Biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**vscanf_s**|\<stdio. h >|
|**wscanf_s**|\<stdio. h > veya \<wchar. h >|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Console, **STDIN**, **stdout**ve **stderr**Ile ilişkili standart akış TUTAMAÇLARı, C çalışma zamanı işlevlerinin UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

Bu programa örnekteki giriş verildiğinde, bu çıktıyı üretir:

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
