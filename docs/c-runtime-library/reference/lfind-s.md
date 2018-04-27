---
title: _lfind_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- linear searching
- keys, finding in arrays
- lfind_s function
- arrays [CRT], searching
- searching, linear
- _lfind_s function
ms.assetid: f1d9581d-5c9d-4222-a31c-a6dfafefa40d
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1de66bf40c22737874eff5d911701ffe123f327e
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="lfinds"></a>_lfind_s

Belirtilen anahtar için doğrusal arama gerçekleştirir. Bir sürümünü [_lfind](lfind.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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

*Anahtarı*<br/>
Aranacak nesne.

*base*<br/>
Arama veri tabanı işaretçi.

*Sayı*<br/>
Dizi öğe sayısı.

*Boyutu*<br/>
Dizi öğeleri bayt cinsinden boyutu.

*Karşılaştırma*<br/>
İşaretçi karşılaştırması yordama. İlk parametre *bağlamı* işaretçi. İkinci parametre için arama anahtar bir işaretçidir. Üçüncü parametre anahtarı ile Karşılaştırılacak dizi öğesi bir işaretçidir.

*bağlam*<br/>
Karşılaştırma işlevinde erişilebilen bir nesne için bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa, **_lfind_s** dizisi öğesine bir işaretçi döndüren *temel* eşleşen *anahtar*. Anahtar bulunamazsa **_lfind_s** döndürür **NULL**.

İşlev için geçersiz parametreler aktarılırsa geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve işlevi döndürür **NULL**.

### <a name="error-conditions"></a>Hata koşulları

|anahtar|taban|compare|NUM|size|errno|
|---------|----------|-------------|---------|----------|-----------|
|**NULL**|tüm|tüm|tüm|tüm|**EINVAL**|
|tüm|**NULL**|tüm|!= 0|tüm|**EINVAL**|
|tüm|tüm|tüm|tüm|sıfır|**EINVAL**|
|tüm|tüm|**NULL**|bir|tüm|**EINVAL**|

## <a name="remarks"></a>Açıklamalar

**_Lfind_s** işlevi gerçekleştiren değeri için doğrusal arama *anahtar* dizisindeki *numarası* öğeleri, her biri *genişliği* bayt. Farklı **bsearch_s**, **_lfind_s** sıralanacak dizi gerektirmez. *Temel* bağımsız değişkeni bir işaretçidir aranacağı dizinin tabanı. *Karşılaştırmak* bağımsız değişkeni bir işaretçidir iki dizi öğeleri karşılaştırır ve ilişkilerini belirten bir değer döndüren bir kullanıcı tarafından sağlanan yordam. **_lfind_s** çağrıları *karşılaştırmak* geçirme, arama sırasında rutin bir veya birden çok kez *bağlamı* işaretçi ve her çağrıda iki dizi öğeleri işaretçiler. *Karşılaştırmak* yordamı öğeleri karşılaştırın ardından (öğeleri farklı sıfır olmayan anlamına gelir) dönün veya 0 (öğeleri aynı olduğu anlamına gelir).

**_lfind_s** benzer **_lfind** eklenmesi dışında *bağlamı* işaretçi karşılaştırması işlevinin bağımsız değişkenleri ve işlev parametre listesi. *Bağlamı* işaretçi Aranan veri yapısı bir nesnenin parçası ise yararlı olabilir ve *karşılaştırmak* işlevi nesnenin üyelerine erişme gerekiyor. *Karşılaştırmak* işlevi uygun nesne türüne ve erişim üyeleri bu nesnenin void işaretçi çevirebilirsiniz. Eklenmesi *bağlamı* parametreyi yapar **_lfind_s** daha güvenli çünkü ek bağlam verileri kullanılabilir hale getirmek için statik değişkenler kullanımıyla ilişkili yeniden giriş hataları önlemek için kullanılabilir *karşılaştırmak* işlevi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lfind_s**|\<Search.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
