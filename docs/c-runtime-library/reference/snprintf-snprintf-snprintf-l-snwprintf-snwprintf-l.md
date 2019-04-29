---
title: snprintf _snprintf, _snprintf_l _snwprintf, _snwprintf_l
ms.date: 11/04/2016
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
ms.openlocfilehash: 202f2f12de3955a2c9b0f785c3e89280d91a4a95
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62355725"
---
# <a name="snprintf-snprintf-snprintfl-snwprintf-snwprintfl"></a>snprintf _snprintf, _snprintf_l _snwprintf, _snwprintf_l

Biçimlendirilmiş verileri bir dizeye yazar. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md).

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

*Biçim*<br/>
Biçim denetimi dizesi.

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için [biçim belirtim Sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

İzin **len** Sonlandırıcı null içermeden, biçimlendirilmiş veri dizesinin uzunluğunda olabilir. Her ikisi de **len** ve *sayısı* için bayt cinsinden **snprintf** ve **_snprintf**, geniş karakterler için **_snwprintf**.

Tüm İşlevler için **len** < *sayısı*, **len** karakter depolanır *arabellek*, bir sonlandırıcı null eklenmez ve **len** döndürülür.

**Snprintf** işlevi keser çıkış olduğunda **len** büyüktür veya eşittir *sayısı*, bir sonlandırıcı null adresindeki yerleştirerek `buffer[count-1]`. Döndürülen değer **len**, çıkış, bulunması gereken karakter sayısı *sayısı* kadar büyüktü. **Snprintf** işlevi kodlama bir hata oluştuğunda negatif bir değer döndürür.

Tüm İşlevler dışında **snprintf**, **len** = *sayısı*, **len** karakter depolanır  *Arabellek*, sonlandırıcı null eklenmez ve **len** döndürülür. Varsa **len** > *sayısı*, *sayısı* karakter depolanır *arabellek*, eklenmiş ve negatif Sonlandırıcı null değer döndürülür.

Varsa *arabellek* null bir işaretçiyse ve *sayısı* sıfır **len** Sonlandırıcı null içerilmeden çıktıyı biçimlendirmek için gereken karakter sayısı döndürülür. Aynı başarılı çağrı yapmak için *bağımsız değişken* ve *yerel* parametreleri, en az tutan bir arabellek ayırın **len** + 1 karakter.

Varsa *arabellek* null bir işaretçiyse ve *sayısı* sıfır veya *biçimi* null bir işaretçiyse, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler -1 döndürür ve **errno** için **EINVAL**.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Snprintf** işlevi ve **_snprintf** işlevleri biçimi ve depolama ailesine *sayısı* ya da daha az karakter *arabellek*. **Snprintf** işlevi her zaman çıkış gerekirse kesiliyor bir sonlandırıcı null karakter de depolar. **_Snprintf** ailesi işlevleri, biçimlendirilmiş dizenin uzunluğu kesinlikle ise bir sonlandırıcı null karakter yalnızca ekler küçüktür *sayısı* karakter. Her *bağımsız değişken* (varsa) dönüştürülür ve karşılık gelen kapsamındaki biçim belirtimine göre çıkışı olan *biçimi*. Biçim sıradan karakterlerden oluşur ve aynı forma ve işleve sahiptir *biçimi* için bağımsız değişken [printf](printf-printf-l-wprintf-wprintf-l.md). Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

> [!IMPORTANT]
> Emin *biçimi* kullanıcı tanımlı bir dize değil. Çünkü **_snprintf** işlevleri null sonlandırma garanti etmez; özellikle, dönüş değeri olduğunda *sayısı*— null sonlandırıcıyı ekleyen kodu tarafından izlenir emin olun. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

Visual Studio 2015 ve Windows 10 UCRT itibaren **snprintf** artık aynıdır **_snprintf**. **Snprintf** işlevi davranışı, artık uyumlu C99 standardı.

**_snwprintf** geniş karakterli sürümüdür **_snprintf**; işaretçi bağımsız değişkenler **_snwprintf** geniş karakterli dizelerdir. İçinde kodlama hatalarının algılanması **_snwprintf** farklı **_snprintf**. **_snwprintf**gibi **swprintf**, türünde bir hedef yerine bir dizeye çıktı Yazar **dosya**.

Sahip bu işlevlerin sürümleri **_l** sonekine, geçerli iş parçacığı yerel ayarı yerine iletilen yerel ayar parametresini kullanmalarıdır.

C++ dilinde, daha yeni ve daha güvenli karşıtları başlatan şablon aşırı yüklemeleri vardır. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_sntprintf**|**_snprintf**|**_snprintf**|**_snwprintf**|
|**_sntprintf_l**|**_snprintf_l**|**_snprintf_l**|**_snwprintf_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**snprintf**, **_snprintf**,  **_snprintf_l**|\<stdio.h >|
|**_snwprintf**, **_snwprintf_l**|\<stdio.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
   /* !subtract one to prevent "squeezing out" the terminal null! */
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
      /* !store null because _snprintf doesn't necessarily (if the string
       * fits without the terminal null, but not with it)!
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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[vprintf İşlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
