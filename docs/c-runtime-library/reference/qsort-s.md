---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 6013098199e1b69d03dc9cf2780cbf4376abcc0d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332970"
---
# <a name="qsort_s"></a>qsort_s

Hızlı bir sıralama gerçekleştirir. [CRT](../../c-runtime-library/security-features-in-the-crt.md)Güvenlik Özellikleri açıklandığı gibi güvenlik geliştirmeleri ile [qsort](qsort.md) bir sürümü.

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

*number*<br/>
Öğelerdeki dizi boyutu.

*genişlik*<br/>
Baytlarda eleman boyutu.

*Karşılaştırmak*<br/>
Karşılaştırma işlevi. İlk bağımsız değişken *bağlam* işaretçisidir. İkinci bağımsız değişken, arama *anahtarına* işaretçidir. Üçüncü bağımsız *değişken, anahtarla*karşılaştırılması gereken dizi öğesine işaretçidir.

*Bağlam*<br/>
*Karşılaştırma* yordamı erişmek için gereken herhangi bir nesne olabilir bir bağlam için bir işaretçi.

## <a name="remarks"></a>Açıklamalar

**qsort_s** işlevi, *her genişlik* baytı olan *bir dizi sayı* öğesini sıralamak için hızlı sıralama algoritması uygular. Bağımsız değişken *tabanı,* sıralanacak dizi tabanına işaretçidir. **qsort_s** bu diziyi sıralanmış öğelerle birlikte yazar. Bağımsız değişken *karşılaştırması,* iki dizi öğesini karşılaştıran ve ilişkilerini belirten bir değer döndüren, kullanıcı tarafından sağlanan bir yordamın işaretçisidir. **qsort_s** sıralama sırasında *karşılaştırma* yordamını bir veya daha fazla kez çağırır ve işaretçileri her çağrıda iki dizi öğesine aktarın:

```C
compare( context, (void *) & elem1, (void *) & elem2 );
```

Yordam öğeleri karşılaştırmak ve sonra aşağıdaki değerlerden birini döndürmelidir:

|Döndürülen değer|Açıklama|
|------------------|-----------------|
|< 0|**elem1** **elem2** daha az|
|0|**elem1** **elem2** eşdeğeri|
|> 0|**elem1** **elem2'den** büyük|

Dizi, karşılaştırma işlevi tarafından tanımlandığı gibi, artan sırada sıralanır. Bir diziyi azalan sırada sıralamak için, karşılaştırma işlevindeki "büyükten büyük" ve "küçük" sözcük lerini tersine çevirin.

Geçersiz parametreler işleve aktarılırsa, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütme devam etmesine izin verilirse, o zaman işlev döndürür ve **errno** **EINVAL**olarak ayarlanır. Daha fazla bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="error-conditions"></a>Hata Koşulları

|anahtar|base|compare|sayı|genişlik|Errno|
|---------|----------|-------------|---------|-----------|-----------|
|**Null**|herhangi bir|herhangi bir|herhangi bir|herhangi bir|**Eınval**|
|herhangi bir|**Null**|herhangi bir|!= 0|herhangi bir|**Eınval**|
|herhangi bir|herhangi bir|herhangi bir|herhangi bir|<= 0|**Eınval**|
|herhangi bir|herhangi bir|**Null**|herhangi bir|herhangi bir|**Eınval**|

**qsort_s** **qsort** olarak aynı davranışa sahiptir ama *bağlam* parametresi ve **errno**ayarlar . *Bir bağlam* parametresi geçerek, karşılaştırma işlevleri nesne işlevselliği veya bir öğe işaretçisi aracılığıyla erişilemeyen diğer bilgilere erişmek için bir nesne işaretçisi kullanabilirsiniz. *Bağlam* parametresinin **eklenmesi,** paylaşılan bilgileri *context* *karşılaştırma* işlevine kullanılabilir hale getirmek için statik değişkenler kullanılarak tanıtılan yeniden canlandırma hatalarını önlemek için kullanılabildiği için qsort_s daha güvenli hale getirir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**qsort_s**|\<stdlib.h> \<ve search.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

**Kütüphaneler:** [CRT Kitaplık Özellikleri'nin](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

Aşağıdaki örnek, **qsort_s** işlevinde *bağlam* parametresinin nasıl kullanılacağını gösterir. *Bağlam* parametresi iş parçacığı güvenli sıralamaları gerçekleştirmeyi kolaylaştırır. İş parçacığı güvenliğini sağlamak için eşitlenmiş olması gereken statik değişkenler kullanmak yerine, her türde farklı bir *bağlam* parametresi geçirin. Bu örnekte, *bağlam* parametresi olarak bir yerel nesne kullanılır.

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
