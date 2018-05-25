---
title: strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 467184acd7ef78ee52f1605d23f2d3b80e6adb83
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="strtoks-strtoksl-wcstoks-wcstoksl-mbstoks-mbstoksl"></a>strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l

Sonraki belirteç geçerli yerel ya da geçirilen bir yerel ayar kullanarak bir dize bulur. Bu sürümleri [strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l](strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> **_mbstok_s** ve **_mbstok_s_l** Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

unsigned char* _mbstok_s(
   unsigned char* str,
   const unsigned char* delimiters,
   char** context,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Belirteç veya belirteçler bulmak için içeren bir dize.

*Sınırlayıcılar*<br/>
Kullanılacak sınırlayıcı karakter kümesi.

*bağlam*<br/>
İşlev çağrıları arasında konum bilgilerini depolamak için kullanılır.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

İşaretçi bulunan sonraki belirteç döndüren *str*. Döndürür **NULL** başka belirteç bulunduğunda. Her çağrı değiştirir *str* tarafından döndürülen belirteç sonra oluşan ilk sınırlayıcısı için bir null karakter değiştirerek.

### <a name="error-conditions"></a>Hata koşulları

|*str*|*Sınırlayıcılar*|*bağlam*|Dönüş değeri|**errno**|
|----------------|------------------|---------------|------------------|-------------|
|**NULL**|tüm|null işaretçinin işaretçi|**NULL**|**EINVAL**|
|tüm|**NULL**|tüm|**NULL**|**EINVAL**|
|tüm|tüm|**NULL**|**NULL**|**EINVAL**|

Varsa *str* olan **NULL** ancak *bağlamı* işaretçi geçerli bağlam işaretçi hata yoktur.

## <a name="remarks"></a>Açıklamalar

**Strtok_s** ailesi işlevlerini bulur sonraki belirteç *str*. Karakter kümesi *sınırlayıcıları* bulunamadı belirteç olası sınırlayıcılar belirtir *str* geçerli çağrıda. **wcstok_s** ve **_mbstok_s** joker karakter ve çok baytlı karakter sürümleri **strtok_s**. Bağımsız değişkenleri ve dönüş değerleri **wcstok_s** ve **_wcstok_s_l** joker karakter olan dizeleri; bu **_mbstok_s** ve **_mbstok_s_l**çok baytlı karakter dizeleri belirtilmiştir. Bu işlevler aynı şekilde aksi davranır.

Bu işlev parametrelerini doğrular. Bir hata koşulu oluşursa hata koşulları tablo olduğu gibi geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve geri dönüp **NULL**.

İlk çağrıda **strtok_s** işlevi başında sınırlayıcıları atlar ve ilk belirteci için bir işaretçi döndürür *str*, bir null karakter belirteciyle sonlandırılıyor. Daha fazla belirteçleri dışında kalan ayrılabilir *str* çağrıları için bir dizi **strtok_s**. Her çağrı **strtok_s** değiştirir *str* bu çağrı tarafından döndürülen belirteç sonra bir null karakter ekleyerek. *Bağlamı* hangi dize okuma ve dizesinde sonraki belirtece okunacak olduğu işaretçi izler. Sonraki belirtecinden okumak için *str*, çağrı **strtok_s** ile bir **NULL** değerini *str* bağımsız değişkeni ve aynı geçirin  *bağlam* parametresi. **NULL** *str* bağımsız değişkeni nedenler **strtok_s** sonraki belirteç değiştirilmiş aramak için *str*. *Sınırlayıcıları* bağımsız değişkeni, sonraki yapılan bir çağrı arasında bir değer alabilir, böylece sınırlayıcı kümesi farklılık gösterebilir.

Bu yana *bağlamı* parametresi yerini kullanılan statik arabellekleri **strtok** ve **_strtok_l**, iş parçacığı eşzamanlı olarak iki dizeleri ayrıştırma mümkündür.

Çıkış değerini ayarı tarafından etkilenen **LC_CTYPE** yerel kategori ayarı; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** soneki için bu yerel ayara bağımlı davranış geçerli iş parçacığı yerel ayarı kullanın. Sürümleriyle **_l** yerine kullandıkları dışında sonek aynı *yerel* parametresi. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtok_s**|\<String.h >|
|**_strtok_s_l**|\<String.h >|
|**wcstok_s**,<br />**_wcstok_s_l**|\<String.h > veya \<wchar.h >|
|**_mbstok_s**,<br />**_mbstok_s_l**|\<Mbstring.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
