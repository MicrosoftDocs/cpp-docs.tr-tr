---
title: _lfind
ms.date: 11/04/2016
apiname:
- _lfind
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
- lfind
- _lfind
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
ms.openlocfilehash: 1508d54d6b2f2566e4aee3afef02af45b28e4f48
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286498"
---
# <a name="lfind"></a>_lfind

Belirtilen anahtar için doğrusal bir arama gerçekleştirir. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz: [_lfind_s](lfind-s.md).

## <a name="syntax"></a>Sözdizimi

```C
void *_lfind(
   const void *key,
   const void *base,
   unsigned int *num,
   unsigned int width,
   int (__cdecl *compare)(const void *, const void *)
);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak nesne.

*base*<br/>
Arama veri tabanı için işaretçi.

*Sayı*<br/>
Dizi öğelerinin sayısı.

*Genişlik*<br/>
Dizi öğeleri genişliği.

*Karşılaştırma*<br/>
Karşılaştırma yordamı işaretçisi. İlk parametre bir arama için anahtar işaretçisidir. İkinci parametre bir anahtar ile Karşılaştırılacak dizi öğesinin işaretçisidir.

## <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa **_lfind** dizisi öğeye bir işaretçi döndürür *temel* eşleşen *anahtar*. Anahtar bulunamazsa **_lfind** döndürür **NULL**.

## <a name="remarks"></a>Açıklamalar

**_Lfind** işlevi, doğrusal bir arama değeri gerçekleştirir *anahtarı* bir dizide *numarası* öğeleri, her biri *genişliği* bayt. Farklı **bsearch**, **_lfind** sıralanacak dizi gerektirmez. *Temel* bağımsız değişken temel aranacak dizi işaretçidir. *Karşılaştırma* bağımsız kullanıcı tarafından sağlanan iki diziyi öğe karşılaştırır ve sonra bunların belirten bir değeri döndüren bir yordam işaretçidir. **_lfind** çağrıları *karşılaştırma* işaretçileri iki dizi öğelerine her çağrıda geçirme, arama sırasında rutin bir veya daha fazla kez. *Karşılaştırma* yordamı gerekir ve öğeleri karşılaştırma (öğeleri farklı olduğu anlamına gelir) sıfır olmayan dönün veya 0 (öğeleri aynı olduğu anlamına gelir).

Bu işlev, parametrelerini doğrular. Varsa *karşılaştırma*, *anahtarı* veya *numarası* olduğu **NULL**, veya *temel* olduğu **NULL**ve *numarası* sıfır değilse, ya da Eğer *genişliği* küçük sıfırdan, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev döndürür **NULL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lfind**|\<Search.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_lfind.c
// This program uses _lfind to search a string array
// for an occurrence of "hello".

#include <search.h>
#include <string.h>
#include <stdio.h>

int compare(const void *arg1, const void *arg2 )
{
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );
}

int main( )
{
   char *arr[] = {"Hi", "Hello", "Bye"};
   int n = sizeof(arr) / sizeof(char*);
   char **result;
   char *key = "hello";

   result = (char **)_lfind( &key, arr,
                      &n, sizeof(char *), compare );

   if( result )
      printf( "%s found\n", *result );
   else
      printf( "hello not found!\n" );
}
```

```Output
Hello found
```

## <a name="see-also"></a>Ayrıca bkz.

[Arama ve Sıralama](../../c-runtime-library/searching-and-sorting.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[bsearch](bsearch.md)<br/>
[_lsearch](lsearch.md)<br/>
[qsort](qsort.md)<br/>
