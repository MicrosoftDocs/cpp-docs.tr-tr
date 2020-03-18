---
title: _lfind
ms.date: 11/04/2016
api_name:
- _lfind
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _lfind
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
ms.openlocfilehash: ec59340433b92334effa8004720e4f0756085670
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442926"
---
# <a name="_lfind"></a>_lfind

Belirtilen anahtar için doğrusal bir arama gerçekleştirir. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz. [_lfind_s](lfind-s.md).

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
Arama verileri tabanı işaretçisi.

*sayısından*<br/>
Dizi öğelerinin sayısı.

*Genişlik*<br/>
Dizi öğelerinin genişliği.

*Karşılaştır*<br/>
Karşılaştırma yordamının işaretçisi. İlk parametre, arama için bir tuşa işaretçidir. İkinci parametre, anahtar ile Karşılaştırılacak dizi öğesine yönelik bir işaretçidir.

## <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa **_lfind** , *tabanında* eşleşen dizinin öğesine bir işaretçi *döndürür.* Anahtar bulunamazsa, **_Lfind** **null**döndürür.

## <a name="remarks"></a>Açıklamalar

**_Lfind** işlevi, her *Genişlik* baytından oluşan *sayı* öğeleri dizisindeki değer *anahtarı* için doğrusal bir arama gerçekleştirir. **Bsearch**'ten farklı olarak **_lfind** , dizinin sıralanmasını gerektirmez. *Taban* bağımsız değişkeni, aranacak dizinin temelini gösteren bir işaretçidir. *Compare* bağımsız değişkeni, iki dizi öğesini karşılaştıran ve ilişkilerini belirten bir değer döndüren kullanıcı tarafından sağlanan yordamın bir işaretçisidir. **_lfind** , arama sırasında *karşılaştırma* yordamını bir veya daha fazla kez çağırarak her çağrıda iki dizi öğesine işaretçiler geçer. *Compare* yordamı, öğeleri karşılaştırmalıdır ve sıfır dışında bir değere (öğelerin farklı olduğu anlamına gelir) ya da 0 (öğeler özdeş) döndürmelidir.

Bu işlev, parametrelerini doğrular. *Compare*, *Key* veya *Number* değeri **null**ise ya da *taban* **null** ve *sayı* sıfır değilse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı *width* gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **null**değerini döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lfind**|\<Search. h >|

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
