---
title: strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l
ms.date: 4/2/2020
api_name:
- _wcstok_s_l
- _mbstok_s_l
- _mbstok_s
- strtok_s
- wcstok_s
- _strtok_s_l
- _o__mbstok_s
- _o__mbstok_s_l
- _o_strtok_s
- _o_wcstok_s
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcstok_s_l
- _wcstok_s_l
- _tcstok_s
- _mbstok_s_l
- strtok_s
- wcstok_s
- _mbstok_s
- _strtok_s_l
helpviewer_keywords:
- _strtok_s_l function
- _mbstok_s_l function
- strings [C++], searching
- mbstok_s_l function
- wcstok_s_l function
- _wcstok_s_l function
- _tcstok_s function
- _tcstok_s_l function
- strtok_s_l function
- wcstok_s function
- tokens, finding in strings
- mbstok_s function
- _mbstok_s function
- strtok_s function
ms.assetid: 7696c972-f83b-4617-8c82-95973e9fdb46
ms.openlocfilehash: 52c998f14fee080efc1d288abbba012752757632
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82912673"
---
# <a name="strtok_s-_strtok_s_l-wcstok_s-_wcstok_s_l-_mbstok_s-_mbstok_s_l"></a>strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l

Geçerli yerel ayarı veya geçirilen yerel ayarı kullanarak bir dizedeki sonraki belirteci bulur. [Strtok, _strtok_l, wcstok, _wcstok_l, _mbstok _mbstok_l](strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) bu SÜRÜMLERINDE, [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri vardır.

> [!IMPORTANT]
> **_mbstok_s** ve **_mbstok_s_l** , Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
char* strtok_s(
   char* str,
   const char* delimiters,
   char** context
);

char* _strtok_s_l(
   char* str,
   const char* delimiters,
   char** context,
   _locale_t locale
);

wchar_t* wcstok_s(
   wchar_t* str,
   const wchar_t* delimiters,
   wchar_t** context
);

wchar_t *_wcstok_s_l(
   wchar_t* str,
   const wchar_t* delimiters,
   wchar_t** context,
   _locale_t locale
);

unsigned char* _mbstok_s(
   unsigned char* str,
   const unsigned char* delimiters,
   char** context
);

unsigned char* _mbstok_s_l(
   unsigned char* str,
   const unsigned char* delimiters,
   char** context,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
Bulunacak belirteç veya belirteçleri içeren bir dize.

*ıcı*<br/>
Kullanılacak sınırlayıcı karakter kümesi.

*bağlam*<br/>
İşleve yapılan çağrılar arasında konum bilgilerini depolamak için kullanılır.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

*Str*içinde bulunan bir sonraki belirtece bir işaretçi döndürür. Daha fazla belirteç bulunamadığında **null** değerini döndürür. Her çağrı, döndürülen belirteçle sonra oluşan ilk sınırlayıcı için null bir karakter koyarak *Str* 'yi değiştirir.

### <a name="error-conditions"></a>Hata koşulları

|*üstbilgisine*|*ıcı*|*bağlam*|Döndürülen değer|**errno**|
|----------------|------------------|---------------|------------------|-------------|
|**DEĞER**|kaydedilmemiş|null işaretçisine işaretçi|**DEĞER**|**EıNVAL**|
|kaydedilmemiş|**DEĞER**|kaydedilmemiş|**DEĞER**|**EıNVAL**|
|kaydedilmemiş|kaydedilmemiş|**DEĞER**|**DEĞER**|**EıNVAL**|

*Str* **null** ise ancak *bağlam* geçerli bir bağlam işaretçisine yönelik işaretçisiyse, hata yoktur.

## <a name="remarks"></a>Açıklamalar

**Strtok_s** ailesi işlevleri, *Str*içindeki bir sonraki belirteci bulur. *Sınırlayıcıdaki* karakter kümesi, geçerli çağrıda *Str* içinde bulunan belirtecin olası sınırlayıcılarını belirler. **wcstok_s** ve **_mbstok_s** , **strtok_s**geniş karakter ve çok baytlı karakter sürümleridir. **Wcstok_s** ve **_wcstok_s_l** bağımsız değişkenleri ve dönüş değerleri geniş karakterli dizelerdir; **_mbstok_s** ve **_mbstok_s_l** olanlar çok baytlı karakter dizeleridir. Bu işlevler, aynı şekilde davranır.

Bu işlev, parametrelerini doğrular. Bir hata koşulu oluştuğunda, hata koşulları tablosunda olduğu gibi, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** ' ı **EINVAL** olarak ayarlar ve **null**döndürür.

**Strtok_s**ilk çağrısında, işlev baştaki sınırlayıcıları atlar ve *Str*içindeki ilk belirtece bir işaretçi döndürür ve belirteci null karakterle sonlandırmaz. Daha fazla belirteç, **strtok_s**için bir dizi çağrı tarafından *Str* 'nin geri kalanı bozulabilir. Her **strtok_s** çağrısı, bu çağrı tarafından döndürülen belirteçten sonra bir null karakter ekleyerek *Str* 'yi değiştirir. *Bağlam* işaretçisi, hangi dizenin okunmakta olduğunu ve dizedeki sonraki belirtecin okunacağı yeri izler. *Str*'deki bir sonraki belirteci okumak için, *Str* bağımsız değişkeni olarak **null** bir değer ile **strtok_s** çağırın ve aynı *bağlam* parametresini geçirin. **Null** *Str* bağımsız değişkeni, **strtok_s** değiştirilen *Str*içindeki bir sonraki belirteci aramasına neden olur. Sınırlayıcılar kümesinin değişebilmesi için *sınırlayıcılar* bağımsız değişkeni, bir sonrakine bir çağrıdan herhangi bir değer alabilir.

*Bağlam* parametresi **strtok** ve **_strtok_l**' de kullanılan statik arabelleklerin yerini aldığı için aynı iş parçacığında iki dizeyi eşzamanlı olarak ayrıştırılabilir.

Çıkış değeri yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir. Daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md).

**_L** soneki olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli iş parçacığı yerel ayarını kullanır. **_L** sonekine sahip sürümler, bunun yerine *yerel ayar* parametresi tarafından belirtilen yerel ayarı kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtok_s**|\<String. h>|
|**_strtok_s_l**|\<String. h>|
|**wcstok_s**,<br />**_wcstok_s_l**|\<String. h> veya \<wchar. h>|
|**_mbstok_s**,<br />**_mbstok_s_l**|\<mbstring. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|\_UNICODE & \_MBCS tanımlı değil|\_Tanımlanan MBCS|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstok_s**|**strtok_s**|**_mbstok_s**|**wcstok_s**|
|**_tcstok_s_l**|**_strtok_s_l**|**_mbstok_s_l**|**_wcstok_s_l**|

## <a name="example"></a>Örnek

```C
// crt_strtok_s.c
// In this program, a loop uses strtok_s
// to print all the tokens (separated by commas
// or blanks) in two strings at the same time.

#include <string.h>
#include <stdio.h>

char string1[] =
    "A string\tof ,,tokens\nand some  more tokens";
char string2[] =
    "Another string\n\tparsed at the same time.";
char seps[]   = " ,\t\n";
char *token1 = NULL;
char *token2 = NULL;
char *next_token1 = NULL;
char *next_token2 = NULL;

int main(void)
{
    printf("Tokens:\n");

    // Establish string and get the first token:
    token1 = strtok_s(string1, seps, &next_token1);
    token2 = strtok_s(string2, seps, &next_token2);

    // While there are tokens in "string1" or "string2"
    while ((token1 != NULL) || (token2 != NULL))
    {
        // Get next token:
        if (token1 != NULL)
        {
            printf(" %s\n", token1);
            token1 = strtok_s(NULL, seps, &next_token1);
        }
        if (token2 != NULL)
        {
            printf("        %s\n", token2);
            token2 = strtok_s(NULL, seps, &next_token2);
        }
    }
}
```

```Output
Tokens:
A
        Another
string
        string
of
        parsed
tokens
        at
and
        the
some
        same
more
        time.
tokens
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
