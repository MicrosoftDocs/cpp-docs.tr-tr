---
title: _lfind
ms.date: 4/2/2020
api_name:
- _lfind
- _o__lfind
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
- _lfind
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
ms.openlocfilehash: 287cbd8bc9cc567a4a0d5b9505d57098197bc545
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342169"
---
# <a name="_lfind"></a>_lfind

Belirtilen anahtar için doğrusal arama yapar. Bu işlevin daha güvenli bir sürümü mevcuttur; [bkz. _lfind_s](lfind-s.md).

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
Arama verilerinin tabanına işaretçi.

*number*<br/>
Dizi öğelerinin sayısı.

*genişlik*<br/>
Dizi elemanlarının genişliği.

*Karşılaştırmak*<br/>
Karşılaştırma yordamı için işaretçi. İlk parametre arama için anahtar için bir işaretçidir. İkinci parametre, anahtarla karşılaştırılması için dizi öğesiiçin bir işaretçidir.

## <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa, **_lfind** *anahtarla*eşleşen *tabandaki* dizi öğesine bir işaretçi döndürür. Anahtar bulunamazsa, **_lfind** **NULL döndürür.**

## <a name="remarks"></a>Açıklamalar

**_lfind** işlevi, *her genişlik* baytı olan *bir dizi sayı* öğesindeki değer *anahtarı* için doğrusal bir arama gerçekleştirir. **bsearch**aksine, **_lfind** dizi sıralanmış gerektirmez. *Temel* bağımsız değişken, aranacak dizi tabanına işaretçidir. *Karşılaştırma* bağımsız değişkeni, iki dizi öğesini karşılaştıran ve sonra ilişkilerini belirten bir değer döndüren, kullanıcı tarafından sağlanan bir yordamın işaretçisidir. **_lfind,** her aramada işaretçileri iki dizi öğesine geçirerek, arama sırasında *karşılaştırma* yordamını bir veya daha fazla kez çağırır. *Karşılaştırma* yordamı öğeleri karşılaştırmak ve daha sonra sıfırsız (yani öğeler farklı) veya 0 (yani öğeler aynı) döndürmelidir.

Bu işlev parametrelerini doğrular. *Karşılaştırın*, *anahtar* veya *sayı* **NULL**ise veya *temel* **NULL** ise ve *sayı* sıfırsızsa veya *genişlik* sıfırdan küçükse, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlev **NULL**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lfind**|\<search.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
