---
title: _lfind_s
ms.date: 4/2/2020
api_name:
- _lfind_s
- _o__lfind_s
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
- api-ms-win-crt-utility-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- lfind_s
- _lfind_s
helpviewer_keywords:
- linear searching
- keys, finding in arrays
- lfind_s function
- arrays [CRT], searching
- searching, linear
- _lfind_s function
ms.assetid: f1d9581d-5c9d-4222-a31c-a6dfafefa40d
ms.openlocfilehash: 589a413c9f1fb49fbfe8cd1b5eacb9d452716523
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916514"
---
# <a name="_lfind_s"></a>_lfind_s

Belirtilen anahtar için doğrusal bir arama gerçekleştirir. [CRT Içindeki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [_lfind](lfind.md) bir sürümü.

## <a name="syntax"></a>Sözdizimi

```C
void *_lfind_s(
   const void *key,
   const void *base,
   unsigned int *num,
   size_t size,
   int (__cdecl *compare)(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak nesne.

*base*<br/>
Arama verileri tabanı işaretçisi.

*number*<br/>
Dizi öğelerinin sayısı.

*boyutla*<br/>
Dizi öğelerinin bayt cinsinden boyutu.

*Karşılaştır*<br/>
Karşılaştırma yordamının işaretçisi. İlk parametre *bağlam* işaretçisidir. İkinci parametre, arama için bir tuşa işaretçidir. Üçüncü parametre, anahtar ile Karşılaştırılacak dizi öğesine yönelik bir işaretçidir.

*bağlam*<br/>
Karşılaştırma işlevinde erişilebilir olabilecek bir nesne işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa **_lfind_s** , *tabanında* eşleşen dizinin öğesine bir işaretçi *döndürür.* Anahtar bulunamazsa, **_Lfind_s** **null**döndürür.

İşleve geçersiz parametreler geçirilmemişse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **null**değerini döndürür.

### <a name="error-conditions"></a>Hata koşulları

|anahtar|base|compare|sayı|size|errno|
|---------|----------|-------------|---------|----------|-----------|
|**DEĞER**|kaydedilmemiş|kaydedilmemiş|kaydedilmemiş|kaydedilmemiş|**EıNVAL**|
|kaydedilmemiş|**DEĞER**|kaydedilmemiş|! = 0|kaydedilmemiş|**EıNVAL**|
|kaydedilmemiş|kaydedilmemiş|kaydedilmemiş|kaydedilmemiş|sıfır|**EıNVAL**|
|kaydedilmemiş|kaydedilmemiş|**DEĞER**|a|kaydedilmemiş|**EıNVAL**|

## <a name="remarks"></a>Açıklamalar

**_Lfind_s** işlevi, her *Genişlik* baytından oluşan *sayı* öğeleri dizisindeki değer *anahtarı* için doğrusal bir arama gerçekleştirir. **Bsearch_s**aksine, **_lfind_s** dizinin sıralanmasını gerektirmez. *Taban* bağımsız değişkeni, aranacak dizinin temelini gösteren bir işaretçidir. *Compare* bağımsız değişkeni, iki dizi öğesini karşılaştıran ve ilişkilerini belirten bir değer döndüren kullanıcı tarafından sağlanan yordamın bir işaretçisidir. **_lfind_s** arama sırasında *karşılaştırma* yordamını bir veya daha fazla kez çağırır, *bağlam* işaretçisini ve işaretçileri her çağrıda iki dizi öğesine geçirerek. *Compare* yordamı, öğeleri karşılaştırmalıdır ve sıfır dışında bir değere (öğelerin farklı olduğu anlamına gelir) veya 0 (öğeler özdeş) döndürür.

**_lfind_s** , karşılaştırma işlevinin bağımsız değişkenlerine ve işlevin parametre listesine *bağlam* işaretçisinin eklenmesi haricinde **_lfind** benzerdir. Arama veri yapısı bir nesnenin parçasıysa ve *Compare* işlevinin nesnenin üyelerine erişmesi gerekiyorsa *bağlam* işaretçisi yararlı olabilir. *Compare* işlevi, void işaretçisini uygun nesne türüne ve bu nesnenin üyelerine ekleyebilir. *Bağlam* parametresinin eklenmesi, verileri *karşılaştırma* işlevine uygun hale getirmek için statik değişkenlerle ilişkili hataların yeniden giriş oluşmasını önlemek için **_lfind_s** daha güvenli hale getirir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lfind_s**|\<Search. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```cpp
// crt_lfind_s.cpp
// This program uses _lfind_s to search a string array,
// passing a locale as the context.
// compile with: /EHsc
#include <stdlib.h>
#include <stdio.h>
#include <search.h>
#include <process.h>
#include <locale.h>
#include <locale>
#include <windows.h>
using namespace std;

// The sort order is dependent on the code page.  Use 'chcp' at the
// command line to change the codepage.  When executing this application,
// the command prompt codepage must match the codepage used here:

#define CODEPAGE_850

#ifdef CODEPAGE_850
// Codepage 850 is the OEM codepage used by the command line,
// so \x00e1 is the German Sharp S

char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };

#define GERMAN_LOCALE "German_Germany.850"

#endif

#ifdef CODEPAGE_1252
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df
   // for the German Sharp S
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };

#define GERMAN_LOCALE "German_Germany.1252"

#endif

// The context parameter lets you create a more generic compare.
// Without this parameter, you would have stored the locale in a
// static variable, thus making it vulnerable to thread conflicts
// (if this were a multithreaded program).

int compare( void *pvlocale, const void *str1, const void *str2)
{
    char *s1 = *(char**)str1;
    char *s2 = *(char**)str2;

    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));

    return use_facet< collate<char> >(loc).compare(
       s1, s1+strlen(s1),
       s2, s2+strlen(s2) );
}

void find_it( char *key, char *array[], unsigned int num, locale &loc )
{
   char **result = (char **)_lfind_s( &key, array,
                      &num, sizeof(char *), compare, &loc );
   if( result )
      printf( "%s found\n", *result );
   else
      printf( "%s not found\n", key );
}

int main( )
{
   find_it( "weit", array1, sizeof(array1)/sizeof(char*), locale(GERMAN_LOCALE) );
}
```

```Output
weit found
```

## <a name="see-also"></a>Ayrıca bkz.

[Arama ve sıralama](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort_s](qsort-s.md)<br/>
[_lfind](lfind.md)<br/>
