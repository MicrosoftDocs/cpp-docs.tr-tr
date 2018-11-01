---
title: qsort_s
ms.date: 11/04/2016
apiname:
- qsort_s
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
- qsort_s
helpviewer_keywords:
- arrays [C++], sorting
- quick-sort algorithm
- qsort_s function
- sorting arrays
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
ms.openlocfilehash: 1f0064fd9cf0a3c52456197568adf693fcdaa9a0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581876"
---
# <a name="qsorts"></a>qsort_s

Hızlı sıralama gerçekleştirir. Bir sürümünü [qsort](qsort.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
void qsort_s(
   void *base,
   size_t num,
   size_t width,
   int (__cdecl *compare )(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>Parametreler

*base*<br/>
Hedef dizi başlangıcı.

*Sayı*<br/>
Öğeleri dizi boyutu.

*Genişlik*<br/>
Öğe boyutunu bayt cinsinden.

*Karşılaştırma*<br/>
Karşılaştırma işlevi. İlk bağımsız değişken *bağlam* işaretçi. İkinci bağımsız değişkeni bir işaretçisidir *anahtar* arama. Üçüncü bağımsız değişkeni ile Karşılaştırılacak dizi öğesinin işaretçisidir *anahtar*.

*Bağlam*<br/>
Bir işaretçi herhangi bir bağlam nesnesi *karşılaştırma* yordamı erişim gerekir.

## <a name="remarks"></a>Açıklamalar

**Qsort_s** işlevi uygulayan bir dizi sıralamak için hızlı Sıralama algoritması *numarası* öğeleri, her biri *genişliği* bayt. Bağımsız değişken *temel* sıralanacak dizinin temel bir işaretçisidir. **qsort_s** sıralanmış öğelerle bu dizinin üzerine yazar. Bağımsız değişken *karşılaştırma* kullanıcı tarafından sağlanan iki diziyi öğe karşılaştırır ve bunların belirten bir değeri döndüren bir yordam bir işaretçisidir. **qsort_s** çağrıları *karşılaştırma* rutin bir veya daha fazla kez işaretçileri iki dizi öğelerine her çağrıda geçirme sıralama sırasında:

```C
compare( context, (void *) & elem1, (void *) & elem2 );
```

Yordam, öğeleri karşılaştırın ve aşağıdaki değerlerden birini döndürür:

|Dönüş değeri|Açıklama|
|------------------|-----------------|
|< 0|**elem1** küçüktür **elem2**|
|0|**elem1** eşdeğer **elem2**|
|> 0|**elem1** büyüktür **elem2**|

Dizi karşılaştırma işlevi tarafından tanımlandığı şekilde, artan düzende sıralanır. Azalan olarak bir diziyi sıralamak için "büyüktür" ve "az" karşılaştırma işlevde anlamı ters çevir.

Geçersiz parametreler bir işleve geçirilirse geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilir sonra işlevi döndürür ve **errno** ayarlanır **EINVAL**. Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Hata koşulları

|anahtar|taban|compare|sayı|genişlik|errno|
|---------|----------|-------------|---------|-----------|-----------|
|**NULL**|Tüm|Tüm|Tüm|Tüm|**EINVAL**|
|Tüm|**NULL**|Tüm|!= 0|Tüm|**EINVAL**|
|Tüm|Tüm|Tüm|Tüm|<= 0|**EINVAL**|
|Tüm|Tüm|**NULL**|Tüm|Tüm|**EINVAL**|

**qsort_s** aynı davranışı sahiptir **qsort** ancak *bağlam* parametresi ve kümelerini **errno**. Geçirerek bir *bağlam* parametresi, karşılaştırma işlevleri nesne işaretçisi nesne işlevselliği veya diğer bilgileri erişilebilir değil, bir öğe işaretçisi erişmek için kullanabilirsiniz. Ek *bağlam* parametreyi yapar **qsort_s** olduğundan daha güvenli *bağlam* yapmak için statik değişkenlerini kullanarak sunulan yeniden giriş hataları önlemek için kullanılabilir Mevcut bilgilere paylaşılan *karşılaştırma* işlevi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**qsort_s**|\<stdlib.h > ve \<search.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** tüm sürümlerini [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir *bağlam* parametresinde **qsort_s** işlevi. *Bağlam* parametre iş parçacığı açısından güvenli sıralar gerçekleştirmeyi kolaylaştırır. İş parçacığı güvenliği sağlamak için eşitlenmesi gereken statik değişkenler kullanmak yerine, farklı bir geçirmek *bağlam* her sıralama parametresi. Bu örnekte, bir yerel ayar nesnesi olarak kullanılan *bağlam* parametresi.

```cpp
// crt_qsort_s.cpp
// compile with: /EHsc /MT
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
// so \x00e1 is the German Sharp S in that codepage and \x00a4
// is the n tilde.

char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };
char *array2[] = { "Espa\x00a4ol", "Espa\x00a4" "a", "espantado" };
char *array3[] = { "table", "tableux", "tablet" };

#define GERMAN_LOCALE "German_Germany.850"
#define SPANISH_LOCALE "Spanish_Spain.850"
#define ENGLISH_LOCALE "English_US.850"

#endif

#ifdef CODEPAGE_1252
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df
   // for the German Sharp S and \x001f for the n tilde.
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };
char *array2[] = { "Espa\x00f1ol", "Espa\x00f1" "a", "espantado" };
char *array3[] = { "table", "tableux", "tablet" };

#define GERMAN_LOCALE "German_Germany.1252"
#define SPANISH_LOCALE "Spanish_Spain.1252"
#define ENGLISH_LOCALE "English_US.1252"

#endif

// The context parameter lets you create a more generic compare.
// Without this parameter, you would have stored the locale in a
// static variable, thus making sort_array vulnerable to thread
// conflicts.

int compare( void *pvlocale, const void *str1, const void *str2)
{
    char s1[256];
    char s2[256];
    strcpy_s(s1, 256, *(char**)str1);
    strcpy_s(s2, 256, *(char**)str2);
    _strlwr_s( s1, sizeof(s1) );
    _strlwr_s( s2, sizeof(s2) );

    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));

    return use_facet< collate<char> >(loc).compare(s1,
       &s1[strlen(s1)], s2, &s2[strlen(s2)]);

}

void sort_array(char *array[], int num, locale &loc)
{
    qsort_s(array, num, sizeof(char*), compare, &loc);
}

void print_array(char *a[], int c)
{
   for (int i = 0; i < c; i++)
      printf("%s ", a[i]);
   printf("\n");

}

void sort_german(void * Dummy)
{
   sort_array(array1, 6, locale(GERMAN_LOCALE));
}

void sort_spanish(void * Dummy)
{
   sort_array(array2, 3, locale(SPANISH_LOCALE));
}

void sort_english(void * Dummy)
{
   sort_array(array3, 3, locale(ENGLISH_LOCALE));
}

int main( )
{
   int i;
   HANDLE threads[3];

   printf("Unsorted input:\n");
   print_array(array1, 6);
   print_array(array2, 3);
   print_array(array3, 3);

   // Create several threads that perform sorts in different
   // languages at the same time.

   threads[0] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_german , 0, NULL));
   threads[1] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_spanish, 0, NULL));
   threads[2] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_english, 0, NULL));

   for (i = 0; i < 3; i++)
   {
      if (threads[i] == reinterpret_cast<HANDLE>(-1))
      {
         printf("Error creating threads.\n");
         exit(1);
      }
   }

   // Wait until all threads have terminated.
   WaitForMultipleObjects(3, threads, true, INFINITE);

   printf("Sorted output: \n");

   print_array(array1, 6);
   print_array(array2, 3);
   print_array(array3, 3);
}
```

### <a name="sample-output"></a>Örnek Çıktı

```Output
Unsorted input:
weiß weis annehmen weizen Zeit weit
Español España espantado
table tableux tablet
Sorted output:
annehmen weiß weis weit weizen Zeit
España Español espantado
table tablet tableux
```

## <a name="see-also"></a>Ayrıca bkz.

[Arama ve Sıralama](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort](qsort.md)<br/>
