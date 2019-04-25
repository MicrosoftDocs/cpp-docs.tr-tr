---
title: _lsearch
ms.date: 11/04/2016
apiname:
- _lsearch
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
- _lsearch
- lsearch
helpviewer_keywords:
- _lsearch function
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- linear searches
- searching, linear
- lsearch function
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
ms.openlocfilehash: 340e8ac382972b15acc52013d5d6a51352db969c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285662"
---
# <a name="lsearch"></a>_lsearch

Bir değer için doğrusal bir arama gerçekleştirir; bulunan değilse listesinin sonuna ekler. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz: [_lsearch_s](lsearch-s.md).

## <a name="syntax"></a>Sözdizimi

```C
void *_lsearch(
   const void *key,
   void *base,
   unsigned int *num,
   unsigned int width,
   int (__cdecl *compare)(const void *, const void *)
);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak nesne.

*base*<br/>
Temel arama yapılacak dizinin işaretçisi.

*Sayı*<br/>
Öğe sayısı.

*Genişlik*<br/>
Her dizi öğe genişliği.

*Karşılaştırma*<br/>
Karşılaştırma yordamı işaretçisi. İlk parametre, arama anahtarı için bir işaretçidir. İkinci parametre, anahtarı ile karşılaştırılacak bir dizi öğesinin işaretçisidir.

## <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa **_lsearch** dizisi öğeye bir işaretçi döndürür *temel* eşleşen *anahtar*. Anahtar bulunamazsa **_lsearch** dizinin sonuna yeni eklenen öğeye bir işaretçi döndürür.

## <a name="remarks"></a>Açıklamalar

**_Lsearch** işlevi, doğrusal bir arama değeri gerçekleştirir *anahtarı* bir dizide *numarası* öğeleri, her biri *genişliği* bayt. Farklı **bsearch**, **_lsearch** sıralanacak dizi gerektirmez. Varsa *anahtarı* bulunamazsa **_lsearch** artırır ve dizi sonuna ekler *numarası*.

*Karşılaştırma* bağımsız kullanıcı tarafından sağlanan iki diziyi öğe karşılaştırır ve bunların belirten bir değeri döndüren bir yordam işaretçidir. **_lsearch** çağrıları *karşılaştırma* işaretçileri iki dizi öğelerine her çağrıda geçirme, arama sırasında rutin bir veya daha fazla kez. *Karşılaştırma* gerekir ve öğeleri karşılaştırma ya da dönüş sıfır olmayan (öğeleri farklı olduğu anlamına gelir) veya 0 (öğeleri aynı olduğu anlamına gelir).

Bu işlev, parametrelerini doğrular. Varsa *karşılaştırma*, *anahtarı* veya *numarası* olduğu **NULL**, veya *temel* olduğu **NULL**ve *numarası* sıfır değilse, ya da Eğer *genişliği* küçük sıfırdan, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev döndürür **NULL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lsearch**|\<Search.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_lsearch.c
#include <search.h>
#include <string.h>
#include <stdio.h>

int compare( const void *arg1, const void *arg2 );

int main(void)
{
   char * wordlist[4] = { "hello", "thanks", "bye" };
                            // leave room to grow...
   int n = 3;
   char **result;
   char *key = "extra";
   int i;

   printf( "wordlist before _lsearch:" );
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );
   printf( "\n" );

   result = (char **)_lsearch( &key, wordlist,
                      &n, sizeof(char *), compare );

   printf( "wordlist after _lsearch:" );
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );
   printf( "\n" );
}

int compare(const void *arg1, const void *arg2 )
{
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );
}
```

```Output
wordlist before _lsearch: hello thanks bye
wordlist after _lsearch: hello thanks bye extra
```

## <a name="see-also"></a>Ayrıca bkz.

[Arama ve Sıralama](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch](bsearch.md)<br/>
[_lfind](lfind.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
