---
title: _lsearch
ms.date: 4/2/2020
api_name:
- _lsearch
- _o__lsearch
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
- _lsearch
helpviewer_keywords:
- _lsearch function
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- linear searches
- searching, linear
- lsearch function
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
ms.openlocfilehash: a6ef3d86ffe8f03da34d4a374bddda1452815672
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341644"
---
# <a name="_lsearch"></a>_lsearch

Bir değer için doğrusal arama yapar; bulunamazsa listenin sonuna eklenir. Bu işlevin daha güvenli bir sürümü mevcuttur; [bkz _lsearch_s](lsearch-s.md).

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
Aranacak dizi tabanına işaretçi.

*number*<br/>
Öğe sayısı.

*genişlik*<br/>
Her dizi öğesinin genişliği.

*Karşılaştırmak*<br/>
Karşılaştırma yordamını işaretçi. İlk parametre arama için anahtar için bir işaretçidir. İkinci parametre, anahtarla karşılaştırılması gereken bir dizi öğesiiçin bir işaretçidir.

## <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa, **_lsearch** *anahtarla*eşleşen *tabandaki* dizi öğesine bir işaretçi döndürür. Anahtar bulunamazsa, **_lsearch** dizinin sonunda yeni eklenen öğeye bir işaretçi döndürür.

## <a name="remarks"></a>Açıklamalar

**_lsearch** işlevi, *her genişlik* baytı olan *bir dizi sayı* öğesindeki değer *anahtarı* için doğrusal bir arama gerçekleştirir. **bsearch**aksine, **_lsearch** dizi sıralanmış gerektirmez. *Anahtar* bulunamazsa, **_lsearch** dizi nin sonuna ekler ve *artışsayısı.*

*Karşılaştırma* bağımsız değişkeni, iki dizi öğesini karşılaştıran ve ilişkilerini belirten bir değer döndüren, kullanıcı tarafından sağlanan bir yordamın işaretçisidir. **_lsearch,** her aramada işaretçileri iki dizi öğesine geçirerek, arama sırasında *karşılaştırma* yordamını bir veya daha fazla kez çağırır. *karşılaştırmak* öğeleri karşılaştırmak ve sıfır sız (yani öğeler farklı) veya 0 (yani öğeler aynı) dönmek gerekir.

Bu işlev parametrelerini doğrular. *Karşılaştırın*, *anahtar* veya *sayı* **NULL**ise veya *temel* **NULL** ise ve *sayı* sıfırsızsa veya *genişlik* sıfırdan küçükse, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlev **NULL**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lsearch**|\<search.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
