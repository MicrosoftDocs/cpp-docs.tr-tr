---
description: 'Hakkında daha fazla bilgi edinin: qsort_s'
title: qsort_s
ms.date: 4/2/2020
api_name:
- qsort_s
- _o_qsort_s
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- qsort_s
helpviewer_keywords:
- arrays [C++], sorting
- quick-sort algorithm
- qsort_s function
- sorting arrays
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
ms.openlocfilehash: 0f0132cbb1210d6289f676f3474683803b58a5a6
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514479"
---
# <a name="qsort_s"></a>qsort_s

Hızlı bir sıralama gerçekleştirir. [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [qsort](qsort.md) sürümü.

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
Hedef dizinin başlangıcı.

*sayısından*<br/>
Öğelerde dizi boyutu.

*width*<br/>
Bayt cinsinden öğe boyutu.

*Karşılaştır*<br/>
Karşılaştırma işlevi. İlk bağımsız değişken *bağlam* işaretçisidir. İkinci bağımsız değişken, arama için *anahtarın* bir işaretçisidir. Üçüncü bağımsız değişken, *anahtar* ile Karşılaştırılacak dizi öğesine yönelik bir işaretçidir.

*bağlam*<br/>
*Karşılaştırma* yordamının erişmesi gereken herhangi bir nesne olabilen bir bağlam işaretçisi.

## <a name="remarks"></a>Açıklamalar

**Qsort_s** işlevi, her *Genişlik* baytından oluşan bir dizi *sayı* öğesi sıralamak için hızlı bir sıralama algoritması uygular. Bağımsız değişken *tabanı* , sıralanacak dizinin temelini gösteren bir işaretçidir. **qsort_s** sıralanmış öğelerle bu dizinin üzerine yazar. Bağımsız değişken *karşılaştırma* , iki dizi öğesini karşılaştıran ve ilişkilerini belirten bir değer döndüren kullanıcı tarafından sağlanan yordamın bir işaretçisidir. **qsort_s** sıralama sırasında *karşılaştırma* yordamını bir veya daha fazla kez çağırır, her çağrıda iki dizi öğesine işaretçiler geçiyor:

```C
compare( context, (void *) & elem1, (void *) & elem2 );
```

Yordam, öğeleri karşılaştırmalıdır ve sonra aşağıdaki değerlerden birini döndürür:

|Döndürülen değer|Açıklama|
|------------------|-----------------|
|< 0|**elem1** küçüktür **elem2**|
|0|**elem1** eşdeğeri **elem2**|
|> 0|**elem1** daha büyük **elem2**|

Dizi, karşılaştırma işlevi tarafından tanımlanan şekilde artan sırada sıralanır. Bir diziyi azalan sırada sıralamak için karşılaştırma işlevindeki "büyüktür" ve "küçüktür" durumunu ters çevirin.

İşleve geçersiz parametreler geçirilmemişse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlev döndürür ve **errno** , **EINVAL** olarak ayarlanır. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="error-conditions"></a>Hata koşulları

|anahtar|base|compare|sayı|genişlik|errno|
|---------|----------|-------------|---------|-----------|-----------|
|**DEĞER**|herhangi biri|herhangi biri|herhangi biri|herhangi biri|**EıNVAL**|
|herhangi biri|**DEĞER**|herhangi biri|! = 0|herhangi biri|**EıNVAL**|
|herhangi biri|herhangi biri|herhangi biri|herhangi biri|<= 0|**EıNVAL**|
|herhangi biri|herhangi biri|**DEĞER**|herhangi biri|herhangi biri|**EıNVAL**|

**qsort_s** **qsort** ile aynı davranışa sahiptir, ancak *bağlam* parametresine sahiptir ve **errno**'ı ayarlar. Bir *bağlam* parametresi geçirerek karşılaştırma işlevleri, nesne işlevselliğine veya bir öğe işaretçisi aracılığıyla erişilemeyen diğer bilgilere erişmek için bir nesne işaretçisi kullanabilir. *Bağlam parametresinin eklenmesi* , paylaşılan bilgileri *karşılaştırma* işlevine kullanılabilir hale getirmek  üzere statik değişkenler kullanarak ortaya çıkan hataların yeniden giriş yapmasını önlemek için **qsort_s** daha güvenli hale getirir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**qsort_s**|\<stdlib.h> ve \<search.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

Aşağıdaki örnek, **qsort_s** işlevindeki *bağlam* parametresinin nasıl kullanılacağını göstermektedir. *Bağlam* parametresi, iş parçacığı güvenli sıralamalar gerçekleştirmeyi kolaylaştırır. İş parçacığı güvenliğini sağlamak için eşitlenmesi gereken statik değişkenleri kullanmak yerine, her bir sıralamaya farklı bir *bağlam* parametresi geçirin. Bu örnekte, bir yerel ayar nesnesi *bağlam* parametresi olarak kullanılır.

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

[Arama ve sıralama](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort](qsort.md)<br/>
