---
title: _lsearch | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _lsearch function
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- linear searches
- searching, linear
- lsearch function
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5f38dd8a23cce652b93794f62c775962482fe159
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="lsearch"></a>_lsearch

Bir değer için doğrusal arama yapar; listenin sonuna ekler bulunamazsa. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [_lsearch_s](lsearch-s.md).

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

*Anahtarı*<br/>
Aranacak nesne.

*base*<br/>
Aranacak dizi tabanı işaretçi.

*Sayı*<br/>
Öğe sayısı.

*Genişlik*<br/>
Her dizi öğesi genişliği.

*Karşılaştırma*<br/>
İşaretçi karşılaştırması yordama. İlk parametre anahtar arama için bir işaretçidir. İkinci parametre anahtarla karşılaştırılması gereken bir dizi öğesine bir işaretçidir.

## <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa, **_lsearch** dizisi öğesine bir işaretçi döndüren *temel* eşleşen *anahtar*. Anahtar bulunamazsa **_lsearch** dizinin sonuna en yeni eklenen öğesine bir işaretçi döndürür.

## <a name="remarks"></a>Açıklamalar

**_Lsearch** işlevi gerçekleştiren değeri için doğrusal arama *anahtar* dizisindeki *numarası* öğeleri, her biri *genişliği* bayt. Farklı **bsearch**, **_lsearch** sıralanacak dizi gerektirmez. Varsa *anahtar* bulunamadı, **_lsearch** artırır ve dizinin sonuna ekler *numarası*.

*Karşılaştırmak* bağımsız değişkeni, iki dizi öğeleri karşılaştırır ve ilişkilerini belirten bir değer döndürür ve kullanıcı tarafından sağlanan bir yordama bir işaretçidir. **_lsearch** çağrıları *karşılaştırmak* işaretçileri iki dizi öğelerinin her çağrıda geçirme, arama sırasında rutin bir veya birden çok kez. *Karşılaştırma* gerekir ve öğeleri karşılaştırma ya da dönüş sıfır olmayan (öğeleri farklı olduğu anlamına gelir) veya 0 (öğeleri aynı olduğu anlamına gelir).

Bu işlev parametrelerini doğrular. Varsa *karşılaştırmak*, *anahtar* veya *numarası* olan **NULL**, veya *temel* null ve **numarası*  sıfır olmayan, olduğundan veya *genişliği* küçük sıfırdan, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve işlevi döndürür **NULL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lsearch**|\<Search.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
