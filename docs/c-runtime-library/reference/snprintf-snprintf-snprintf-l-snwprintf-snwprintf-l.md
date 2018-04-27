---
title: snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _snwprintf
- _snprintf
- _snprintf_l
- _snwprintf_l
- snprintf
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _snprintf
- snprintf_l
- snwprintf_l
- sntprintf
- snprintf
- _sntprintf
- _sntprintf_l
- sntprintf_l
- snwprintf
- _snprintf_l
- _snwprintf
- _snwprintf_l
dev_langs:
- C++
helpviewer_keywords:
- snwprintf_l function
- sntprintf_l function
- snprintf_l function
- _snwprintf_l function
- _sntprintf_l function
- _snwprintf function
- _snprintf function
- _sntprintf function
- _snprintf_l function
- snwprintf function
- snprintf function
- sntprintf function
- formatted text [C++]
ms.assetid: 5976c9c8-876e-4ac9-a515-39f3f7fd0925
caps.latest.revision: 35
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8c47f3d1a65d9a48f0a76cd6dd9876d799e583f
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="snprintf-snprintf-snprintfl-snwprintf-snwprintfl"></a>snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l
Biçimlendirilmiş verileri bir dizeye yazar. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md).

## <a name="syntax"></a>Sözdizimi

```C
int snprintf(
   char *buffer,
   size_t count,
   const char *format [,
   argument] ...
);
int _snprintf(
   char *buffer,
   size_t count,
   const char *format [,
   argument] ...
);
int _snprintf_l(
   char *buffer,
   size_t count,
   const char *format,
   locale_t locale [,
   argument] ...
);
int _snwprintf(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format [,
   argument] ...
);
int _snwprintf_l(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
template <size_t size>
int _snprintf(
   char (&buffer)[size],
   size_t count,
   const char *format [,
   argument] ...
); // C++ only
template <size_t size>
int _snprintf_l(
   char (&buffer)[size],
   size_t count,
   const char *format,
   locale_t locale [,
   argument] ...
); // C++ only
template <size_t size>
int _snwprintf(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format [,
   argument] ...
); // C++ only
template <size_t size>
int _snwprintf_l(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   locale_t locale [,
   argument] ...
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Çıktı için depolama konumu.

*Sayısı*<br/>
Depolanacak maksimum karakter sayısı.

*Biçimi*<br/>
Biçim denetimi dizesi.

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için bkz: [biçim belirtim Sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

Let **len** sonlandırma null dahil değil biçimlendirilen verileri dize uzunluğu olmalıdır. Her ikisi de **len** ve *sayısı* için bayt cinsinden olan **snprintf** ve **_snprintf**, geniş karakter için **_snwprintf**.

Tüm İşlevler için ise **len** < *sayısı*, **len** karakter depolanır *arabellek*, null Sonlandırıcı eklenir, ve **len** döndürülür.

**Snprintf** işlevi kesen çıktı zaman **len** büyük veya eşit *sayısı*, null Sonlandırıcı adresindeki yerleştirerek `buffer[count-1]`. Döndürülen değer **len**, çıktı durumunda olması gereken karakter sayısını *sayısı* kadar büyüktü. **Snprintf** işlevi bir kodlama hatası oluşursa negatif bir değer döndürür.

Tüm işlevleri dışında **snprintf**, **len** = *sayısı*, **len** karakter depolanır  *Arabellek*, null-Sonlandırıcı eklenir, ve **len** döndürülür. Varsa **len** > *sayısı*, *sayısı* karakter depolanır *arabellek*, eklenmiş ve negatif null-Sonlandırıcı değeri döndürülür.

Varsa *arabellek* null işaretçi ve *sayısı* sıfır **len** sonlandırma null hariç çıkış biçimlendirmek için gereken karakter sayısı döndürülür. Aynı başarılı arama yapmak için *bağımsız değişkeni* ve *yerel ayar* parametreleri, en az bulunduran bir arabellek ayırın **len** + 1 karakter.

Varsa *arabellek* null işaretçi ve *sayısı* sıfır olmayan, olduğundan veya *biçimi* null işaretçi açıklandığı gibi geçersiz parametre işleyicisi çağrılır [ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler -1 döndürür ve **errno** için **EINVAL**.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Snprintf** işlevi ve **_snprintf** işlevleri biçimi ve depolama ailesi *sayısı* veya daha az karakter *arabellek*. **Snprintf** işlevi her zaman bir sonlandırma boş çıkış gerekirse kesilmesiyle karakter depolar. **_Snprintf** ailesi işlevlerini biçimlendirilmiş dize uzunluğu kesinlikle ise bir sonlandırma null karakter yalnızca ekler değerinden *sayısı* karakter. Her *bağımsız değişkeni* (varsa) dönüştürülür ve karşılık gelen biçimi belirtiminde göre çıktısı *biçimi*. Biçim sıradan karakterden oluşan ve aynı form ve olarak işlev *biçimi* bağımsız değişkeni için [printf](printf-printf-l-wprintf-wprintf-l.md). Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

> [!IMPORTANT]
> Emin *biçimi* kullanıcı tanımlı bir dize değil. Çünkü **_snprintf** işlevleri NULL sonlandırma garanti etmez; özellikle, dönüş değeri olduğunda *sayısı*— null Sonlandırıcı ekler kodu tarafından izlenir emin olun. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).

Visual Studio 2015 ve Windows 10 UCRT itibaren **snprintf** artık aynıdır **_snprintf**. **Snprintf** işlevi davranıştır şimdi C99 standart uyumlu.

**_snwprintf** bir joker karakter sürümü **_snprintf**; işaretçi bağımsız değişkenleri **_snwprintf** joker karakter dizelerdir. Kodlama hataları algılama **_snwprintf** uygulamasında farklılık gösterebilir **_snprintf**. **_snwprintf**, tıpkı **swprintf**, hedef türü yerine bir dizeye çıktısı Yazar **dosya**.

Bu işlevleri sürümlerini **_l** soneki, geçerli iş parçacığı yerel ayar yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.

C++ dilinde, daha yeni ve daha güvenli karşıtları başlatan şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_sntprintf**|**_snprintf**|**_snprintf**|**_snwprintf**|
|**_sntprintf_l**|**_snprintf_l**|**_snprintf_l**|**_snwprintf_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**snprintf**, **_snprintf**, **_snprintf_l**|\<stdio.h >|
|**_snwprintf**, **_snwprintf_l**|\<stdio.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_snprintf.c
// compile with: /W3
#include <stdio.h>
#include <stdlib.h>

#if !defined(__cplusplus)
typedef int bool;
const bool true = 1;
const bool false = 0;
#endif

#define FAIL 0 // change to 1 and see what happens

int main(void)
{
   char buffer[200];
   const static char s[] = "computer"
#if FAIL
"computercomputercomputercomputercomputercomputercomputercomputer"
"computercomputercomputercomputercomputercomputercomputercomputer"
"computercomputercomputercomputercomputercomputercomputercomputer"
"computercomputercomputercomputercomputercomputercomputercomputer"
#endif
   ;
   const char c = 'l';
   const int i = 35;
#if FAIL
   const double fp = 1e300; // doesn't fit in the buffer
#else
   const double fp = 1.7320534;
#endif
   /* !subtract one to prevent "squeezing out" the terminal nul! */
   const int bufferSize = sizeof(buffer)/sizeof(buffer[0]) - 1;
   int bufferUsed = 0;
   int bufferLeft = bufferSize - bufferUsed;
   bool bSuccess = true;
   buffer[0] = 0;

   /* Format and print various data: */

   if (bufferLeft > 0)
   {
      int perElementBufferUsed = _snprintf(&buffer[bufferUsed],
      bufferLeft, "   String: %s\n", s ); // C4996
      // Note: _snprintf is deprecated; consider _snprintf_s instead
      if (bSuccess = (perElementBufferUsed >= 0))
      {
         bufferUsed += perElementBufferUsed;
         bufferLeft -= perElementBufferUsed;
         if (bufferLeft > 0)
         {
            int perElementBufferUsed = _snprintf(&buffer[bufferUsed],
            bufferLeft, "   Character: %c\n", c ); // C4996
            if (bSuccess = (perElementBufferUsed >= 0))
            {
               bufferUsed += perElementBufferUsed;
               bufferLeft -= perElementBufferUsed;
               if (bufferLeft > 0)
               {
                  int perElementBufferUsed = _snprintf(&buffer
                  [bufferUsed], bufferLeft, "   Integer: %d\n", i ); // C4996
                  if (bSuccess = (perElementBufferUsed >= 0))
                  {
                     bufferUsed += perElementBufferUsed;
                     bufferLeft -= perElementBufferUsed;
                     if (bufferLeft > 0)
                     {
                        int perElementBufferUsed = _snprintf(&buffer
                        [bufferUsed], bufferLeft, "   Real: %f\n", fp ); // C4996
                        if (bSuccess = (perElementBufferUsed >= 0))
                        {
                           bufferUsed += perElementBufferUsed;
                        }
                     }
                  }
               }
            }
         }
      }
   }

   if (!bSuccess)
   {
      printf("%s\n", "failure");
   }
   else
   {
      /* !store nul because _snprintf doesn't necessarily (if the string
       * fits without the terminal nul, but not with it)!
       * bufferUsed might be as large as bufferSize, which normally is
       * like going one element beyond a buffer, but in this case
       * subtracted one from bufferSize, so we're ok.
       */
      buffer[bufferUsed] = 0;
      printf( "Output:\n%s\ncharacter count = %d\n", buffer, bufferUsed );
   }
   return EXIT_SUCCESS;
}
```

```Output
Output:
   String: computer
   Character: l
   Integer: 35
   Real: 1.732053

character count = 69
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[vprintf İşlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
