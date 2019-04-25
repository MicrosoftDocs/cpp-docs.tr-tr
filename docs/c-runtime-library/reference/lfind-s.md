---
title: _lfind_s
ms.date: 11/04/2016
apiname:
- _lfind_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 08c04d9d1ca69998d54304c96468298013907179
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286433"
---
# <a name="lfinds"></a>_lfind_s

Belirtilen anahtar için doğrusal bir arama gerçekleştirir. Bir sürümünü [_lfind](lfind.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Arama veri tabanı için işaretçi.

*Sayı*<br/>
Dizi öğelerinin sayısı.

*Boyutu*<br/>
Dizi öğeleri bayt cinsinden boyutu.

*Karşılaştırma*<br/>
Karşılaştırma yordamı işaretçisi. İlk parametre *bağlam* işaretçi. İkinci parametre arama için anahtar bir işaretçisidir. Üçüncü parametre bir anahtar ile Karşılaştırılacak dizi öğesinin işaretçisidir.

*Bağlam*<br/>
Karşılaştırma işlev erişilebilen bir nesne için bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa **_lfind_s** dizisi öğeye bir işaretçi döndürür *temel* eşleşen *anahtar*. Anahtar bulunamazsa **_lfind_s** döndürür **NULL**.

Geçersiz parametreler bir işleve geçirilirse geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev döndürür **NULL**.

### <a name="error-conditions"></a>Hata koşulları

|anahtar|taban|compare|sayı|size|errno|
|---------|----------|-------------|---------|----------|-----------|
|**NULL**|Tüm|Tüm|Tüm|Tüm|**EINVAL**|
|Tüm|**NULL**|Tüm|!= 0|Tüm|**EINVAL**|
|Tüm|Tüm|Tüm|Tüm|sıfır|**EINVAL**|
|Tüm|Tüm|**NULL**|Bir|Tüm|**EINVAL**|

## <a name="remarks"></a>Açıklamalar

**_Lfind_s** işlevi, doğrusal bir arama değeri gerçekleştirir *anahtarı* bir dizide *numarası* öğeleri, her biri *genişliği* bayt. Farklı **bsearch_s**, **_lfind_s** sıralanacak dizi gerektirmez. *Temel* bağımsız değişken temel aranacak dizi işaretçidir. *Karşılaştırma* bağımsız kullanıcı tarafından sağlanan iki diziyi öğe karşılaştırır ve sonra bunların belirten bir değeri döndüren bir yordam işaretçidir. **_lfind_s** çağrıları *karşılaştırma* geçirme, arama sırasında rutin bir veya daha fazla kez *bağlam* işaretçi ve her çağrıda iki dizi öğeleri işaretçileri. *Karşılaştırma* yordamı öğeleri karşılaştırma sonra döndürür (öğeleri farklı sıfır olmayan anlamına gelir) veya 0 (öğeleri aynı olduğu anlamına gelir).

**_lfind_s** benzer **_lfind** eklenmesi dışında *bağlam* karşılaştırma işlevinin bağımsız değişkenleri ve işlevin parametre listesine işaretçi. *Bağlam* işaretçi Aranan veri yapısı, bir nesnenin parçası ise kullanışlı olabilir ve *karşılaştırmak* işlevi bir nesnenin üyelerine erişim gerekir. *Karşılaştırma* işlevi uygun nesne türü ve erişim üyeleri o nesnenin void işaretçisine çevirebilirsiniz. Ek *bağlam* parametreyi yapar **_lfind_s** daha güvenli veri kullanılabilir hale getirmek için statik değişkenler kullanmayla ilişkili yeniden giriş hataları önlemek için ek bağlam kullanılabildiğinden *karşılaştırma* işlevi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lfind_s**|\<Search.h >|

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

[Arama ve Sıralama](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort_s](qsort-s.md)<br/>
[_lfind](lfind.md)<br/>
