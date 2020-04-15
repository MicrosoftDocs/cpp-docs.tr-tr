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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 9fe89fb897a5459b16c49060359b4bb40bc062a7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365217"
---
# <a name="strtok_s-_strtok_s_l-wcstok_s-_wcstok_s_l-_mbstok_s-_mbstok_s_l"></a>strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l

Geçerli yerel alanı veya geçirilen bir yerel durumu kullanarak bir dizedeki sonraki belirteci bulur. [Strtok, _strtok_l, wcstok, _wcstok_l, _mbstok _mbstok_l](strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) bu sürümleri, [CRT Güvenlik Özellikleri](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmeleri var.

> [!IMPORTANT]
> **_mbstok_s** ve **_mbstok_s_l,** Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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

*Str*<br/>
Bulunması gereken belirteç veya belirteçleri içeren bir dize.

*Sınırlayıcı*<br/>
Kullanılacak sınır layıcı karakter kümesi.

*Bağlam*<br/>
İşlev çağrıları arasında konum bilgilerini depolamak için kullanılır.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Str'de bulunan bir sonraki belirteç için bir işaretçi *döndürür.* Başka belirteç bulunmadığında **NULL'u** döndürür. Her çağrı, döndürülen belirteçten sonra oluşan ilk sınır layıcıiçin null bir karakter ikame ederek *str'i* değiştirir.

### <a name="error-conditions"></a>Hata Koşulları

|*Str*|*Sınırlayıcı*|*Bağlam*|Döndürülen değer|**Errno**|
|----------------|------------------|---------------|------------------|-------------|
|**Null**|herhangi bir|null işaretçisine işaretçi|**Null**|**Eınval**|
|herhangi bir|**Null**|herhangi bir|**Null**|**Eınval**|
|herhangi bir|herhangi bir|**Null**|**Null**|**Eınval**|

*Str* **NULL** ise ancak *bağlam* geçerli bir bağlam işaretçisi için bir işaretçi ise, hata yoktur.

## <a name="remarks"></a>Açıklamalar

Fonksiyonlar **strtok_s** aile *str*sonraki belirteç bulur. *Sınırsırlayıcılarındaki* karakter kümesi, belirtecinin mevcut aramada *str'* de bulunma olasılığını belirtir. **wcstok_s** ve **_mbstok_s** **strtok_s**geniş karakterli ve çok bayt karakterli versiyonlarıdır. **wcstok_s** ve **_wcstok_s_l** bağımsız değişkenleri ve dönüş değerleri geniş karakterli dizeleridir; **_mbstok_s** ve **_mbstok_s_l** çok bayt karakterli dizeleri vardır. Bu işlevler aynı şekilde başka türlü çalışır.

Bu işlev parametrelerini doğrular. Hata Koşulları tablosunda olduğu gibi bir hata koşulu oluştuğunda, Geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, bu işlevler **EINVAL** **için errno** ayarlayın ve **NULL**döndürün.

**strtok_s**için ilk çağrıda , işlev önde gelen sınırlayıcıları atlar ve *str'deki*ilk belirteci için bir işaretçi döndürür , belirteci null bir karakterle sonlandırıyor. Daha fazla belirteçleri **strtok_s**için aramalar bir dizi *str* geri kalanı dışarı kırılmış olabilir. **strtok_s** için her çağrı belirteç bu çağrı tarafından döndürüldükten sonra null bir karakter ekleyerek *str* değiştirir. *Bağlam* işaretçisi, hangi dizenin okunduğunu ve dizede sonraki belirteç nerede okunacağını izler. *Str'den*sonraki belirteci okumak için, *str* bağımsız değişkeni için **NULL** değeri olan **strtok_s** çağırın ve aynı *bağlam* parametresini geçirin. **NULL** *str* bağımsız değişkeni, **strtok_s** değiştirilmiş *str'deki*bir sonraki belirteci aramasına neden olur. *Sınırdan arındırıcılar* bağımsız değişkeni, bir aramadan diğerine herhangi bir değer alabilir, böylece sınır layıcılar kümesi değişebilir.

*Bağlam* parametresi **strtok** ve **_strtok_l**kullanılan statik arabelleklerin yerini aldığı için, aynı iş parçacığında aynı anda iki dize ayrıştırmak mümkündür.

Çıktı değeri, LC_CTYPE **kategori** ayarını ayarlayarak etkilenir. Daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md)bakın.

Bu işlevlerin **_l** sonek olmayan sürümleri, bu yerelçözüme bağımlı davranış için geçerli iş parçacığı yerelsini kullanır. **_l** soneki olan sürümler, yerel *parametre* tarafından belirtilen yerelliği kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtok_s**|\<string.h>|
|**_strtok_s_l**|\<string.h>|
|**wcstok_s**,<br />**_wcstok_s_l**|\<string.h> \<veya wchar.h>|
|**_mbstok_s**,<br />**_mbstok_s_l**|\<mbstring.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|\_UNICODE \_& MBCS tanımlanmamış|\_MBCS tanımlı|_UNICODE tanımlanmış|
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
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
