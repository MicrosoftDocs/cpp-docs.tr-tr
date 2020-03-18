---
title: _lsearch
ms.date: 11/04/2016
api_name:
- _lsearch
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
ms.openlocfilehash: 6dc610c4ab120d81bfb2b3b5e64a54a104bea97f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438149"
---
# <a name="_lsearch"></a>_lsearch

Bir değer için doğrusal bir arama gerçekleştirir; bulunmazsa listenin sonuna ekler. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz. [_lsearch_s](lsearch-s.md).

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
Aranacak dizinin tabanına yönelik işaretçi.

*sayısından*<br/>
Öğe sayısı.

*Genişlik*<br/>
Her bir dizi öğesinin genişliği.

*Karşılaştır*<br/>
Karşılaştırma yordamının işaretçisi. İlk parametre, arama için anahtarın bir işaretçisidir. İkinci parametre, anahtar ile Karşılaştırılacak dizi öğesine yönelik bir işaretçidir.

## <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa **_lsearch** , *tabanında* eşleşen dizinin öğesine bir işaretçi *döndürür.* Anahtar bulunamazsa, **_lsearch** dizinin sonunda yeni eklenen öğeye bir işaretçi döndürür.

## <a name="remarks"></a>Açıklamalar

**_Lsearch** işlevi, her *Genişlik* baytından oluşan *sayı* öğeleri dizisindeki değer *anahtarı* için doğrusal bir arama gerçekleştirir. **Bsearch**'ten farklı olarak **_lsearch** , dizinin sıralanmasını gerektirmez. *Anahtar* bulunmazsa **_lsearch** dizi sonuna ekler ve *sayı*artar.

*Compare* bağımsız değişkeni, iki dizi öğesini karşılaştıran ve ilişkilerini belirten bir değer döndüren kullanıcı tarafından sağlanan yordamın bir işaretçisidir. **_lsearch** , arama sırasında *karşılaştırma* yordamını bir veya daha fazla kez çağırarak her çağrıda iki dizi öğesine işaretçiler geçer. *Compare* öğeleri karşılaştırmalıdır ve sıfır dışında bir değere (öğelerin farklı olduğu anlamına gelir) veya 0 (öğeler özdeş) döndürmelidir.

Bu işlev, parametrelerini doğrular. *Compare*, *Key* veya *Number* değeri **null**ise ya da *taban* **null** ve *sayı* sıfır değilse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı *width* gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **null**değerini döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lsearch**|\<Search. h >|

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
