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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 8f2983bee93c623eb936ed12422134281418076b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342181"
---
# <a name="_lfind_s"></a>_lfind_s

Belirtilen anahtar için doğrusal arama yapar. [CRT](../../c-runtime-library/security-features-in-the-crt.md)Güvenlik Özellikleri açıklandığı gibi güvenlik geliştirmeleri ile [_lfind](lfind.md) bir sürümü.

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
Arama verilerinin tabanına işaretçi.

*number*<br/>
Dizi öğelerinin sayısı.

*Boyutu*<br/>
Baytlar dizi elemanlarının boyutu.

*Karşılaştırmak*<br/>
Karşılaştırma yordamı için işaretçi. İlk parametre *bağlam* işaretçisidir. İkinci parametre arama için anahtar için bir işaretçidir. Üçüncü parametre, anahtarla karşılaştırıldığında dizi öğesiiçin bir işaretçidir.

*Bağlam*<br/>
Karşılaştırma işlevinde erişilebilen bir nesneye işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa, **_lfind_s** *anahtarla*eşleşen *tabandaki* dizi öğesine bir işaretçi döndürür. Anahtar bulunamazsa, **_lfind_s** **NULL döndürür.**

Geçersiz parametreler işleve aktarılırsa, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlev **NULL**döndürür.

### <a name="error-conditions"></a>Hata Koşulları

|anahtar|base|compare|sayı|size|Errno|
|---------|----------|-------------|---------|----------|-----------|
|**Null**|herhangi bir|herhangi bir|herhangi bir|herhangi bir|**Eınval**|
|herhangi bir|**Null**|herhangi bir|!= 0|herhangi bir|**Eınval**|
|herhangi bir|herhangi bir|herhangi bir|herhangi bir|sıfır|**Eınval**|
|herhangi bir|herhangi bir|**Null**|a|herhangi bir|**Eınval**|

## <a name="remarks"></a>Açıklamalar

**_lfind_s** işlevi, *her genişlik* baytı olan *bir dizi sayı* öğesindeki değer *anahtarı* için doğrusal bir arama gerçekleştirir. **bsearch_s**aksine, **_lfind_s** dizi sıralanmış gerektirmez. *Temel* bağımsız değişken, aranacak dizi tabanına işaretçidir. *Karşılaştırma* bağımsız değişkeni, iki dizi öğesini karşılaştıran ve sonra ilişkilerini belirten bir değer döndüren, kullanıcı tarafından sağlanan bir yordamın işaretçisidir. **_lfind_s,** her aramada *bağlam* işaretçisini ve işaretçileri iki dizi öğesine geçirerek, arama sırasında *karşılaştırma* yordamını bir veya daha fazla kez çağırır. *Karşılaştırma* yordamı öğeleri karşılaştırmak gerekir sonra sıfırsız dönmek (öğeleri farklı olduğu anlamına gelir) veya 0 (öğeleri aynı anlamı).

**_lfind_s,** karşılaştırma işlevinin bağımsız değişkenlerine bağlam *işaretçisinin* eklenmesi ve işlevin parametre listesi dışında **_lfind** benzer. Aranan veri yapısı bir nesnenin parçasıysa ve *karşılaştırma* işlevinin nesnenin üyelerine erişmesi gerekiyorsa *bağlam* işaretçisi yararlı olabilir. *Karşılaştırma* işlevi, geçersiz işaretçiyi uygun nesne türüne ve bu nesnenin üyelerine erişebilir. *Bağlam* parametresinin **eklenmesi,** verileri *karşılaştırma* işlevinde kullanılabilir hale getirmek için statik değişkenlerin kullanılmasıyla ilişkili yeniden canlandırma hatalarını önlemek için ek bağlam kullanılabildiği için _lfind_s daha güvenli hale getirir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lfind_s**|\<search.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Arama ve Sıralama](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort_s](qsort-s.md)<br/>
[_lfind](lfind.md)<br/>
