---
title: scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l
ms.date: 03/26/2019
apiname:
- wscanf_s
- _wscanf_s_l
- scanf_s
- _scanf_s_l
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
- wscanf_s
- _tscanf_s_l
- _wscanf_s_l
- scanf_s
- _tscanf_s
- _scanf_s_l
helpviewer_keywords:
- reading data [C++], from input streams
- buffers [C++], buffer overruns
- _scanf_s_l function
- _wscanf_s_l function
- tscanf_s_l function
- tscanf_s function
- scanf_s function
- data [C++], reading from input stream
- wscanf_s function
- _tscanf_s_l function
- _tscanf_s function
- scanf_s_l function
- formatted data [C++], from input streams
- wscanf_s_l function
- buffers [C++], avoiding overruns
ms.assetid: 42cafcf7-52d6-404a-80e4-b056a7faf2e5
ms.openlocfilehash: 28697cac20181c3dda0581c7486ebb673aec1241
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357089"
---
# <a name="scanfs-scanfsl-wscanfs-wscanfsl"></a>scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l

Biçimlendirilmiş verileri standart giriş akışından okur. Bu sürümleri [scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
int scanf_s(
   const char *format [,
   argument]...
);
int _scanf_s_l(
   const char *format,
   locale_t locale [,
   argument]...
);
int wscanf_s(
   const wchar_t *format [,
   argument]...
);
int _wscanf_s_l(
   const wchar_t *format,
   locale_t locale [,
   argument]...
);
```

### <a name="parameters"></a>Parametreler

*Biçim*<br/>
Biçim Denetimi dizesi.

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla dönüştürülen ve atanan alanların sayısını döndürür. Dönüş değeri, Okunmuş ancak atanmamış alanları içermez. 0 değeri hiçbir alan atanmamış belirtir. Dönüş değeri **EOF** bir hata veya dosya sonu karakteri veya dize sonu karakteri bir karakter okumak için yapılan ilk girişim içinde bulunur. Varsa *biçimi* olduğu bir **NULL** işaretçiyse, geçersiz parametre işleyicisi çağrılır, açıklandığı [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **scanf_s** ve **wscanf_s** dönüş **EOF** ayarlayıp **errno** için **EINVAL**.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Scanf_s** işlevi standart giriş akışından verileri okur **stdin**ve içine Yazar *bağımsız değişken*. Her *bağımsız değişken* tür tanımlayıcısına karşılık gelen bir değişken türü bir işaretçi olmalıdır *biçimi*. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

**wscanf_s** geniş karakterli sürümüdür **scanf_s**; *biçimi* bağımsız değişkeni **wscanf_s** geniş karakterli bir dizedir. **wscanf_s** ve **scanf_s** akış ANSI modunda açıldığında aynı şekilde davranır. **scanf_s** şu anda UNICODE akışından girişi desteklemez.

Sahip bu işlevlerin sürümleri **_l** kullanmaları dışında soneki aynı *yerel ayar* geçerli iş parçacığı yerel ayarı yerine parametre.

Farklı **scanf** ve **wscanf**, **scanf_s** ve **wscanf_s** bazı parametreler için arabellek boyutlarını belirtin gerektirir. İçin tüm boyutlarının belirtin **c**, **C**, **s**, **S**, veya dize denetim kümesi **[]** parametreleri. Karakter arabelleği boyutu, ek bir parametre olarak geçirilir. Hemen işaretçinin arabellek veya değişkene izler. Örneğin, bir dize okuyorsanız, bu dize için arabellek boyutu şöyle aktarılır:

```C
char s[10];
scanf_s("%9s", s, (unsigned)_countof(s)); // buffer size is 10, width specification is 9
```

Arabellek boyutu, terminal null karakterini içerir. Uygun arabelleğine okunan belirtecin emin olmak için bir genişlik belirtimi alanı kullanabilirsiniz. Bir belirteç sığmayacak kadar büyük olduğunda olmadığı sürece bir genişlik belirtimi hiçbir şey arabelleğe yazılır.

> [!NOTE]
> Boyut parametresi türünde **işaretsiz**değil **size_t**. Statik atama dönüştürerek bir **size_t** değerini **işaretsiz** 64 bit için yapılandırma derleme.

Arabellek boyutu parametresinin bayt sayısını değil karakter sayısı açıklar. Bu örnekte, arabellek türü genişliğini biçim belirticisi genişliğini eşleşmiyor.

```C
wchar_t ws[10];
wscanf_s(L"%9S", ws, (unsigned)_countof(ws));
```

**S** biçim belirticisi anlamına gelir "karşıtı" varsayılan genişliğini işlev tarafından desteklenen karakter genişliği kullanın. Karakter genişliği tek bayttır, ancak işlev çift baytlı karakterleri destekler. Bu örnekte, en çok dokuz tek bayt geniş karakter dizesindeki okur ve bunları bir çift bayt genişliğinde karakter arabelleğine koyar. Karakterler tek baytlık değer olarak kabul edilir; ilk iki karakter `ws[0]` içinde depolanır, ikinci iki karakter `ws[1]` içinde depolanır ve bu şekilde devam eder.

Bu örnek, tek bir karakter okur:

```C
char c;
scanf_s("%c", &c, 1);
```

Null sonlandırılmış dizeler için birden çok karakter okunduğunda, tamsayılar genişlik belirtimi ve arabellek boyutu için kullanılır.

```C
char c[4];
scanf_s("%4c", c, (unsigned)_countof(c)); // not null terminated
```

Daha fazla bilgi için [scanf genişlik belirtimi](../../c-runtime-library/scanf-width-specification.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tscanf_s**|**scanf_s**|**scanf_s**|**wscanf_s**|
|**_tscanf_s_l**|**_scanf_s_l**|**_scanf_s_l**|**_wscanf_s_l**|

Daha fazla bilgi için [biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**scanf_s**, **_scanf_s_l**|\<stdio.h >|
|**wscanf_s**, **_wscanf_s_l**|\<stdio.h > veya \<wchar.h >|

Konsolu, Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Standart akış işleyicileri **stdin**, **stdout**, ve **stderr** C çalışma zamanı işlevleri bunları UWP uygulamalarında kullanmadan önce yeniden yönlendirilmelidir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_scanf_s.c
// This program uses the scanf_s and wscanf_s functions
// to read formatted input.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int      i,
            result;
   float    fp;
   char     c,
            s[80];
   wchar_t  wc,
            ws[80];

   result = scanf_s( "%d %f %c %C %s %S", &i, &fp, &c, 1,
                     &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );
   printf( "The number of fields input is %d\n", result );
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c,
           wc, s, ws);
   result = wscanf_s( L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,
                      &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );
   wprintf( L"The number of fields input is %d\n", result );
   wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp,
            c, wc, s, ws);
}
```

Bu program, bu girdi verildiğinde aşağıdaki çıktıyı oluşturur:

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
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
