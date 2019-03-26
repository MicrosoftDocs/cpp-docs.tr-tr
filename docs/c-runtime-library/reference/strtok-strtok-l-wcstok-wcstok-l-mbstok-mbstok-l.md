---
title: strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l
ms.date: 03/25/2019
apiname:
- _mbstok_l
- _mbstok
- wcstok
- _mbstok
- strtok
- _wcstok_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbstok
- strtok
- _tcstok
- wcstok
helpviewer_keywords:
- mbstok_l function
- strings [C++], searching
- tcstok function
- _tcstok function
- _strtok_l function
- strtok function
- mbstok function
- wcstok_l function
- _mbstok function
- tcstok_l function
- tokens, finding in strings
- _mbstok_l function
- wcstok function
- _wcstok_l function
- _tcstok_l function
- strtok_l function
ms.assetid: 904cb734-f0d7-4d77-ba81-4791ddf461ae
ms.openlocfilehash: 22dd01a0b2558c83ca1e25875a2ace7dd4ee15c0
ms.sourcegitcommit: 6e4dd21759caaed262a7255735cf8d6e8fb9f4d7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/26/2019
ms.locfileid: "58476922"
---
# <a name="strtok-strtokl-wcstok-wcstokl-mbstok-mbstokl"></a>strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l

Sonraki belirtece, geçerli yerel ayarı veya geçirilen bir belirtilen yerel ayarı kullanarak bir dize içinde bulur. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md).

> [!IMPORTANT]
> **_mbstok** ve **_mbstok_l** Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
char *strtok(
   char *strToken,
   const char *strDelimit
);
char *strtok_l(
   char *strToken,
   const char *strDelimit,
   _locale_t locale
);
wchar_t *wcstok(
   wchar_t *strToken,
   const wchar_t *strDelimit
);
wchar_t *wcstok_l(
   wchar_t *strToken,
   const wchar_t *strDelimit,
   _locale_t locale
);
unsigned char *_mbstok(
   unsigned char *strToken,
   const unsigned char *strDelimit
);
unsigned char *_mbstok_l(
   unsigned char *strToken,
   const unsigned char *strDelimit,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*strToken*<br/>
Belirteç veya belirteçleri içeren dize.

*strDelimit*<br/>
Sınırlayıcı karakter kümesi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bulunan sonraki belirteç için bir işaretçi döndürür *strToken*. İşlevler dönüş **NULL** zaman başka belirteç bulundu. Her çağrının değiştirir *strToken* sonra döndürülen belirteci oluşan ilk sınırlayıcısı için bir null karakter koyarak tarafından.

## <a name="remarks"></a>Açıklamalar

**Strtok** işlevi bulur sonraki belirteç *strToken*. Karakter kümesi *strDelimit* belirteç bulunamıyor olası ayırıcısını belirtir *strToken* geçerli çağrıda. **wcstok** ve **_mbstok** geniş karakter ve çok baytlı karakter sürümleridir **strtok**. Bağımsız değişkenler ve dönüş değeri **wcstok** geniş karakterli dizelerdir; **_mbstok** çok baytlı karakter dizeleridir. Bu üç işlev aynı şekilde davranır.

> [!IMPORTANT]
> Bu işlevler bir arabellek taşması sorunu duruma olası bir tehdit yansıtılmaz. Arabellek taşması sorunları, sistem saldırı, bir unwarranted ayrıcalık yükseltilmesi ile sonuçlanan sık kullanılan bir yöntemdir. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

Yapılan ilk çağrıda **strtok**, işlev önde gelen sınırlayıcılar atlar ve ilk belirteci için bir işaretçi döndürür *strToken*, sonlandırıcı null karakteri ile belirteç. Daha fazla belirteçleri dışında kalan bölünebilir *strToken* bir dizi çağrıda tarafından **strtok**. Her çağrı **strtok** değiştirir *strToken* null karakterden sonra ekleyerek **belirteci** çağrı tarafından döndürülen. Sonraki belirteçten okunacak *strToken*, çağrı **strtok** ile bir **NULL** değerini *strToken* bağımsız değişken. **NULL** *strToken* bağımsız değişken nedenleri **strtok** sonraki belirtece değiştirilmiş aranacak *strToken*. *StrDelimit* bağımsız değişkeni, bir çağrısından sonraki herhangi bir değer alabilir, böylece sınırlayıcı kümesi farklılık gösterebilir.

Çıkış değeri ayarından etkilenir **LC_CTYPE** yerel ayarının kategori ayarına. Daha fazla bilgi için [setlocale](setlocale-wsetlocale.md).

Bu işlevlerin sürümleri **_l** soneki, bu yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. Sürümlerle **_l** sonekine, bunun yerine iletilmiş yerel ayar parametresini kullanmalarıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

> [!NOTE]
> Her işlev, dizeyi belirteçlere ayrıştırmak için bir iş parçacığına yerel statik değişken kullanır. Bu nedenle, birden çok iş parçacığı aynı anda istenmeyen etkileri olmadan bu işlevleri çağırabilir. Ancak, tek bir iş parçacığı içinde Bu işlevlerden biri çağrısına Interleaving veri bozulması ve tutarsız sonuçlar üretmesi olasılığı yüksektir. Farklı dizeleri ayrıştırma, sonraki ayrıştırılacak başlatmadan önce bir dizeyi ayrıştırma tamamlayın. Ayrıca bir döngü içinde Bu işlevlerden biri burada başka bir işlev olarak da adlandırılır çağrılırken tehlike potansiyeli farkında olun. Bu işlevlerden birini kullanarak diğer işlev sona erer, veri bozulması tetikleyen bir araya eklemeli dizisi çağrılarının sonuçlanır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstok**|**strtok**|**_mbstok**|**wcstok**|
|**_tcstok**|**_strtok_l**|**_mbstok_l**|**_wcstok_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtok**|\<String.h >|
|**wcstok**|\<String.h > veya \<wchar.h >|
|**_mbstok**, **_mbstok_l**|\<Mbstring.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_strtok.c
// compile with: /W3
// In this program, a loop uses strtok
// to print all the tokens (separated by commas
// or blanks) in the string named "string".
//
#include <string.h>
#include <stdio.h>

char string[] = "A string\tof ,,tokens\nand some  more tokens";
char seps[]   = " ,\t\n";
char *token;

int main( void )
{
   printf( "Tokens:\n" );

   // Establish string and get the first token:
   token = strtok( string, seps ); // C4996
   // Note: strtok is deprecated; consider using strtok_s instead
   while( token != NULL )
   {
      // While there are tokens in "string"
      printf( " %s\n", token );

      // Get next token:
      token = strtok( NULL, seps ); // C4996
   }
}
```

```Output
Tokens:
A
string
of
tokens
and
some
more
tokens
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
