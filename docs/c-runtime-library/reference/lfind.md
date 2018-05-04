---
title: _lfind | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f60ea8dd05f9dffd6778c001e3f150f95744ae2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="lfind"></a>_lfind

Belirtilen anahtar için doğrusal arama gerçekleştirir. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [_lfind_s](lfind-s.md).

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

*Anahtarı*<br/>
Aranacak nesne.

*base*<br/>
Arama veri tabanı işaretçi.

*Sayı*<br/>
Dizi öğe sayısı.

*Genişlik*<br/>
Dizi öğeleri kalınlığı.

*Karşılaştırma*<br/>
İşaretçi karşılaştırması yordama. İlk parametre arama için anahtar bir işaretçidir. İkinci parametre anahtarı ile Karşılaştırılacak dizi öğesi bir işaretçidir.

## <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa, **_lfind** dizisi öğesine bir işaretçi döndüren *temel* eşleşen *anahtar*. Anahtar bulunamazsa **_lfind** döndürür **NULL**.

## <a name="remarks"></a>Açıklamalar

**_Lfind** işlevi gerçekleştiren değeri için doğrusal arama *anahtar* dizisindeki *numarası* öğeleri, her biri *genişliği* bayt. Farklı **bsearch**, **_lfind** sıralanacak dizi gerektirmez. *Temel* bağımsız değişkeni bir işaretçidir aranacağı dizinin tabanı. *Karşılaştırmak* bağımsız değişkeni bir işaretçidir iki dizi öğeleri karşılaştırır ve ilişkilerini belirten bir değer döndüren bir kullanıcı tarafından sağlanan yordam. **_lfind** çağrıları *karşılaştırmak* işaretçileri iki dizi öğelerinin her çağrıda geçirme, arama sırasında rutin bir veya birden çok kez. *Karşılaştırmak* yordamı öğeleri karşılaştırır ve (öğeleri farklı olduğu anlamına gelir) sıfır olmayan bir değer döndürür veya 0 (öğeleri aynı olduğu anlamına gelir).

Bu işlev parametrelerini doğrular. Varsa *karşılaştırmak*, *anahtar* veya *numarası* olan **NULL**, veya *temel* null ve **numarası*  sıfır olmayan, olduğundan veya *genişliği* küçük sıfırdan, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve işlevi döndürür **NULL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lfind**|\<Search.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
