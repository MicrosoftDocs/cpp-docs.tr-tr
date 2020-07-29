---
title: scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l
ms.date: 03/26/2019
api_name:
- wscanf_s
- _wscanf_s_l
- scanf_s
- _scanf_s_l
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
ms.openlocfilehash: 8811bd0b6e4009cd6aba570e65d0687fab465614
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231370"
---
# <a name="scanf_s-_scanf_s_l-wscanf_s-_wscanf_s_l"></a>scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l

Standart giriş akışından biçimlendirilen verileri okur. [Scanf, _scanf_l, wscanf _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md) bu SÜRÜMLERINDE, [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri vardır.

## <a name="syntax"></a>Söz dizimi

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

*formatını*<br/>
Biçim denetimi dizesi.

*değişkendir*<br/>
İsteğe bağlı bağımsız değişkenler.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla dönüştürülen ve atanan alanların sayısını döndürür. Dönüş değeri, okunan ancak atanmamış alanları içermez. 0 dönüş değeri, atanan alan olmadığını gösterir. Dönüş değeri bir hata için **EOF** veya ilk kez bir karakteri okumak için ilk denemede dosya sonu karakteri veya dize sonu karakteri bulunursa. *Biçim* **null** Işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa **scanf_s** ve **wscanf_s** **EOF** döndürür ve **errno** ' ı **EINVAL**olarak ayarlayın.

Bu ve diğer hata kodları hakkında bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Scanf_s** işlevi standart giriş akışından, **stdin**'den verileri okur ve *bağımsız değişkene*yazar. Her *bağımsız değişken* , *biçimdeki*tür belirticisine karşılık gelen bir değişken türünün işaretçisi olmalıdır. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

**wscanf_s** , **scanf_s**geniş karakterli bir sürümüdür; wscanf_s *Biçim* bağımsız değişkeni **wscanf_s** , geniş karakterli bir dizedir. **wscanf_s** ve **SCANF_S** , akış ANSI modunda açılırsa aynı şekilde davranır. **scanf_s** , UNICODE akışından girişi desteklememektedir.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine *yerel ayar* parametresini kullanmaları dışında aynıdır.

**Scanf** ve **wscanf**'den farklı olarak **scanf_s** ve **wscanf_s** bazı parametrelerin arabellek boyutlarını belirtmenizi gerektirir. Tüm **c**, **c**, **s** **, veya**dize denetim kümesi **[]** parametrelerinin boyutlarını belirtin. Karakterdeki arabellek boyutu ek bir parametre olarak geçirilir. Arabelleği veya değişkeni için işaretçiyi hemen takip eder. Örneğin, bir dizeyi okuyorsanız, bu dize için arabellek boyutu aşağıdaki gibi geçirilir:

```C
char s[10];
scanf_s("%9s", s, (unsigned)_countof(s)); // buffer size is 10, width specification is 9
```

Arabellek boyutu, terminali null değerini içerir. Okunan belirtecin arabelleğe sığmasını sağlamak için bir genişlik belirtimi alanı kullanabilirsiniz. Bir belirteç sığmayacak kadar büyükse, bir genişlik belirtimi olmadıkça hiçbir şey arabelleğe yazılmaz.

> [!NOTE]
> Boyut parametresi **`unsigned`** **size_t**değil türündedir. **Size_t** değerini **`unsigned`** 64 bitlik derleme yapılandırmalarına dönüştürmek için statik bir tür dönüştürme kullanın.

Arabellek boyutu parametresi, bayt değil en fazla karakter sayısını tanımlar. Bu örnekte, arabellek türünün genişliği Biçim belirticisinin genişliğiyle eşleşmez.

```C
wchar_t ws[10];
wscanf_s(L"%9S", ws, (unsigned)_countof(ws));
```

**S** Biçim Belirleyicisi, işlevin desteklediği varsayılan genişlik olan "karşıt" karakter genişliğini kullanır. Karakter genişliği tek bayttır, ancak işlev çift baytlık karakterleri destekler. Bu örnek, en fazla dokuz tek bayt geniş karakter dizesini okur ve bunları çift baytlık bir karakter arabelleğine koyar. Karakterler tek baytlık değer olarak kabul edilir; ilk iki karakter `ws[0]` içinde depolanır, ikinci iki karakter `ws[1]` içinde depolanır ve bu şekilde devam eder.

Bu örnek tek bir karakteri okur:

```C
char c;
scanf_s("%c", &c, 1);
```

Null sonlandırılmış olmayan dizeler için birden çok karakter okunıyorsa, hem genişlik belirtimi hem de arabellek boyutu için tamsayılar kullanılır.

```C
char c[4];
scanf_s("%4c", c, (unsigned)_countof(c)); // not null terminated
```

Daha fazla bilgi için bkz. [scanf Width belirtimi](../../c-runtime-library/scanf-width-specification.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tscanf_s**|**scanf_s**|**scanf_s**|**wscanf_s**|
|**_tscanf_s_l**|**_scanf_s_l**|**_scanf_s_l**|**_wscanf_s_l**|

Daha fazla bilgi için bkz. [Biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**scanf_s**, **_scanf_s_l**|\<stdio.h>|
|**wscanf_s**, **_wscanf_s_l**|\<stdio.h> veya \<wchar.h>|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Standart akış, **stdin**, **stdout**ve **stderr** 'in, C çalışma zamanı işlevlerinin bunları UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmesi gerekir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \_ _swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
