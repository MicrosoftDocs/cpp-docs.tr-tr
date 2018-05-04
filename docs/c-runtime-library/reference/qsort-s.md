---
title: qsort_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- arrays [C++], sorting
- quick-sort algorithm
- qsort_s function
- sorting arrays
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4aad6fdd96df22375e93207e70dfd0f7cf1f44c4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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

*temel* hedef dizi başlangıcı.

*sayı* dizi öğeleri boyutu.

*Genişlik* öğesi boyutunu bayt cinsinden.

*Karşılaştırma* karşılaştırma işlevi. İlk bağımsız değişken *bağlamı* işaretçi. İkinci bağımsız değişkeni gösteren bir işaretçidir *anahtar* arama için. Üçüncü bağımsız değişkeni bir dizi öğesi ile Karşılaştırılacak işaretçidir *anahtar*.

*bağlam* herhangi bir bağlam için bir işaretçi nesne *karşılaştırmak* yordamı erişim gerekir.

## <a name="remarks"></a>Açıklamalar

**Qsort_s** işlevi bir dizi sıralamak için hızlı Sıralama algoritması uygulayan *numarası* öğeleri, her biri *genişliği* bayt sayısı. Bağımsız değişken *temel* sıralanacak dizisinin temel bir işaretçidir. **qsort_s** bu diziye sıralanmış öğeleriyle üzerine yazar. Bağımsız değişken *karşılaştırmak* iki dizi öğeleri karşılaştırır ve ilişkilerini belirten bir değer döndüren bir kullanıcı tarafından sağlanan yordam bir işaretçidir. **qsort_s** çağrıları *karşılaştırmak* rutin bir veya daha fazla kez işaretçileri iki dizi öğelerinin her çağrıda geçirme sıralama sırasında:

```C
compare( context, (void *) & elem1, (void *) & elem2 );
```

Yordam, öğeleri karşılaştırmak ve aşağıdaki değerlerden birini döndürür:

|Dönüş değeri|Açıklama|
|------------------|-----------------|
|< 0|**elem1** değerinden **elem2**|
|0|**elem1** eşdeğer **elem2**|
|> 0|**elem1** büyük **elem2**|

Dizi karşılaştırma işlevi tarafından tanımlandığı şekilde, artan düzende sıralanır. Azalan olarak bir dizi sıralamak için "büyüktür" ve "küçüktür" karşılaştırma işlevinde duygusu ters çevrilir.

İşlev için geçersiz parametreler aktarılırsa geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütme izin sonra işlevi döndürür ve **errno** ayarlanır **EINVAL**. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Hata koşulları

|anahtar|taban|compare|NUM|genişlik|errno|
|---------|----------|-------------|---------|-----------|-----------|
|**NULL**|tüm|tüm|tüm|tüm|**EINVAL**|
|tüm|**NULL**|tüm|!= 0|tüm|**EINVAL**|
|tüm|tüm|tüm|tüm|<= 0|**EINVAL**|
|tüm|tüm|**NULL**|tüm|tüm|**EINVAL**|

**qsort_s** aynı davranışı sahiptir **qsort** ancak *bağlamı* parametre ve kümelerini **errno**. Geçirerek bir *bağlamı* parametresi, karşılaştırma işlevleri bir nesne işaretçisi nesnesi işlevselliği veya diğer bilgileri erişilebilir bir öğesi işaretçisi erişmek için kullanabilirsiniz. Eklenmesi *bağlamı* parametreyi yapar **qsort_s** daha güvenli olduğundan *bağlamı* yapmak için statik değişkenler kullanarak sunulan yeniden giriş hataları önlemek için kullanılabilir Mevcut bilgilere paylaşılan *karşılaştırmak* işlevi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**qsort_s**|\<stdlib.h > ve \<search.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** tüm sürümlerini [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

Aşağıdaki örnekte nasıl kullanılacağı ortaya *bağlamı* parametresinde **qsort_s** işlevi. *Bağlamı* parametre iş parçacığı sıralar yapılacağı kolaylaştırır. İş parçacığı güvenliği sağlamak için eşitlenmesi gereken statik değişkenler kullanmak yerine, farklı bir geçirmek *bağlamı* her sıralama parametresi. Bu örnekte, bir yerel ayar nesnesi olarak kullanılan *bağlamı* parametresi.

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
