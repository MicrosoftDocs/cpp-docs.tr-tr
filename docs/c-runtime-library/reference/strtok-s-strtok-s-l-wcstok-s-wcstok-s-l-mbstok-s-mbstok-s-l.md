---
title: strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l
ms.date: 03/25/2019
apiname:
- _wcstok_s_l
- _mbstok_s_l
- _mbstok_s
- strtok_s
- wcstok_s
- _strtok_s_l
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
- ntoskrnl.exe
apitype: DLLExport
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
ms.openlocfilehash: e2c237927aa133d33085be40b88789c1024d6b34
ms.sourcegitcommit: 6e4dd21759caaed262a7255735cf8d6e8fb9f4d7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/26/2019
ms.locfileid: "58476896"
---
# <a name="strtoks-strtoksl-wcstoks-wcstoksl-mbstoks-mbstoksl"></a>strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l

Sonraki belirtece, geçerli yerel ayarı veya geçirilen bir yerel ayarı kullanarak bir dize içinde bulur. Bu sürümleri [strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l](strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> **_mbstok_s** ve **_mbstok_s_l** Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*str*<br/>
Belirteç veya belirteçleri bulmak için içeren bir dize.

*Sınırlayıcılar*<br/>
Kullanılacak sınırlayıcı karakter kümesi.

*Bağlam*<br/>
İşlev çağrıları arasında konum bilgileri depolamak için kullanılır.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bulunan sonraki belirteç için bir işaretçi döndürür *str*. Döndürür **NULL** zaman başka belirteç bulundu. Her çağrının değiştirir *str* sonra döndürülen belirteci oluşan ilk sınırlayıcısı için bir null karakter koyarak tarafından.

### <a name="error-conditions"></a>Hata koşulları

|*str*|*Sınırlayıcılar*|*Bağlam*|Dönüş değeri|**errno**|
|----------------|------------------|---------------|------------------|-------------|
|**NULL**|Tüm|null bir işaretçi işaretçisi|**NULL**|**EINVAL**|
|Tüm|**NULL**|Tüm|**NULL**|**EINVAL**|
|Tüm|Tüm|**NULL**|**NULL**|**EINVAL**|

Varsa *str* olduğu **NULL** ancak *bağlam* bir işaretçi geçerli bağlam işaretçisi, hata yoktur.

## <a name="remarks"></a>Açıklamalar

**Strtok_s** işlevler ailesini bulur sonraki belirteç *str*. Karakter kümesi *sınırlayıcılar* belirteç bulunamıyor olası ayırıcısını belirtir *str* geçerli çağrıda. **wcstok_s** ve **_mbstok_s** geniş karakter ve çok baytlı karakter sürümleridir **strtok_s**. Bağımsız değişkenler ve dönüş değerleri **wcstok_s** ve **_wcstok_s_l** geniş karakterli dizelerdir; **_mbstok_s** ve **_mbstok_s_l**çok baytlı karakter dizeleridir. Bu işlevler, aynı şekilde davranır.

Bu işlev, parametrelerini doğrular. Bir hata durumu oluştuğunda hata koşullarını tabloda olduğu gibi geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve dönüş **NULL**.

Yapılan ilk çağrıda **strtok_s**, işlev önde gelen sınırlayıcılar atlar ve ilk belirteci için bir işaretçi döndürür *str*, sonlandırıcı null karakteri ile belirteç. Daha fazla belirteçleri dışında kalan bölünebilir *str* bir dizi çağrıda tarafından **strtok_s**. Her çağrı **strtok_s** değiştirir *str* sonra o çağrı tarafından döndürülen belirteci null karakteri ekleyerek. *Bağlam* hangi dize okuyun ve dizesinde sonraki belirtece okunacak olduğu işaretçi izler. Sonraki belirteçten okunacak *str*, çağrı **strtok_s** ile bir **NULL** değerini *str* bağımsız değişken ve aynı  *bağlam* parametresi. **NULL** *str* bağımsız değişken nedenleri **strtok_s** sonraki belirtece değiştirilmiş aranacak *str*. *Sınırlayıcılar* bağımsız değişkeni, bir çağrısından sonraki herhangi bir değer alabilir, böylece sınırlayıcı kümesi farklılık gösterebilir.

Bu yana *bağlam* parametresi olarak kullanılan statik arabellek yerini **strtok** ve **_strtok_l**, aynı anda aynı iş parçacığı, iki dizeyi ayrıştırmak mümkündür.

Çıkış değeri ayarından etkilenir **LC_CTYPE** yerel ayarının kategori ayarına. Daha fazla bilgi için [setlocale](setlocale-wsetlocale.md).

Bu işlevlerin sürümleri **_l** soneki, bu yerel ayara bağımlı davranış için geçerli iş parçacığı yerel ayarı kullanın. Sürümlerle **_l** soneki, bunun yerine tarafından belirtilen yerel ayarı kullanmaları dışında aynıdır *yerel ayar* parametresi. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtok_s**|\<String.h >|
|**_strtok_s_l**|\<String.h >|
|**wcstok_s**,<br />**_wcstok_s_l**|\<String.h > veya \<wchar.h >|
|**_mbstok_s**,<br />**_mbstok_s_l**|\<Mbstring.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|\_UNICODE & \_MBCS tanımlı değil|\_MBCS tanımlanan|_UNICODE tanımlanmış|
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

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
