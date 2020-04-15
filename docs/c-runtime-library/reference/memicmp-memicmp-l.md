---
title: _memicmp, _memicmp_l
ms.date: 4/2/2020
api_name:
- _memicmp_l
- _memicmp
- _o__memicmp
- _o__memicmp_l
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
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _memicmp
- memicmp_l
- _memicmp_l
helpviewer_keywords:
- memicmp function
- _memicmp function
- memicmp_l function
- _memicmp_l function
ms.assetid: 0a6eb945-4077-4f84-935d-1aaebe8db8cb
ms.openlocfilehash: 5ad22f2107695b14d4a8361d4532d6e250b5af6f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333233"
---
# <a name="_memicmp-_memicmp_l"></a>_memicmp, _memicmp_l

İki arabellekteki karakterleri karşılaştırır (büyük/küçük harf duyarsız).

## <a name="syntax"></a>Sözdizimi

```C
int _memicmp(
   const void *buffer1,
   const void *buffer2,
   size_t count
);
int _memicmp_l(
   const void *buffer1,
   const void *buffer2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*arabellek1*<br/>
İlk arabellek.

*arabellek2*<br/>
İkinci tampon.

*Sayısı*<br/>
Karakter sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

İade değeri arabellekler arasındaki ilişkiyi gösterir.

|Döndürülen değer|Buf1 ve buf2'nin ilk sayım baytlarının ilişkisi|
|------------------|--------------------------------------------------------|
|< 0|*arabellek1* daha az *arabellek2*.|
|0|*arabellek1* *arabellek2*ile aynıdır.|
|> 0|*arabellek1* *tampon2*daha büyük .|
|**_NLSCMPERROR**|Bir hata oluşmuştur.|

## <a name="remarks"></a>Açıklamalar

**_memicmp** işlevi, iki arabellek *arabelleği1* ve *arabellek2* bayt tarafından ilk *sayma* karakterleri karşılaştırır. Karşılaştırma büyük/küçük harf duyarlı değildir.

*Arabellek1* veya *arabellek2* null işaretçisi ise, bu işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre işleyicisi çağırır. Yürütmedevam etmesine izin verilirse, işlev **_NLSCMPERROR** döndürür ve **EINVAL** **için errno** ayarlar.

**_memicmp,** yerele bağımlı davranış için geçerli yerel durumu kullanır; **_memicmp_l,** bunun yerine geçirilen yerel alanı kullanması dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_memicmp**|\<memory.h> \<veya string.h>|
|**_memicmp_l**|\<memory.h> \<veya string.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_memicmp.c
// This program uses _memicmp to compare
// the first 29 letters of the strings named first and
// second without regard to the case of the letters.

#include <memory.h>
#include <stdio.h>
#include <string.h>

int main( void )
{
   int result;
   char first[] = "Those Who Will Not Learn from History";
   char second[] = "THOSE WHO WILL NOT LEARN FROM their mistakes";
   // Note that the 29th character is right here ^

   printf( "Compare '%.29s' to '%.29s'\n", first, second );
   result = _memicmp( first, second, 29 );
   if( result < 0 )
      printf( "First is less than second.\n" );
   else if( result == 0 )
      printf( "First is equal to second.\n" );
   else if( result > 0 )
      printf( "First is greater than second.\n" );
}
```

```Output
Compare 'Those Who Will Not Learn from' to 'THOSE WHO WILL NOT LEARN FROM'
First is equal to second.
```

## <a name="see-also"></a>Ayrıca bkz.

[Arabellek Manipülasyonu](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
