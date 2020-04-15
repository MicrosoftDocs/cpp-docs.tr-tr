---
title: tolower, _tolower, towlower, _tolower_l, _towlower_l
ms.date: 4/2/2020
api_name:
- _tolower_l
- towlower
- tolower
- _tolower
- _towlower_l
- _o__tolower
- _o__tolower_l
- _o__towlower_l
- _o_tolower
- _o_towlower
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _totlower
- tolower
- _tolower
- towlower
helpviewer_keywords:
- tolower_l function
- _tolower_l function
- totlower function
- string conversion, to different characters
- lowercase, converting to
- tolower function
- string conversion, case
- towlower function
- _tolower function
- _totlower function
- towlower_l function
- case, converting
- characters, converting
- _towlower_l function
ms.assetid: 86e0fc02-94ae-4472-9631-bf8e96f67b92
ms.openlocfilehash: 560fde4ae2167256acd54856fced15bc6ccecae6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362354"
---
# <a name="tolower-_tolower-towlower-_tolower_l-_towlower_l"></a>tolower, _tolower, towlower, _tolower_l, _towlower_l

Bir karakteri küçük harfe dönüştürür.

## <a name="syntax"></a>Sözdizimi

```C
int tolower(
   int c
);
int _tolower(
   int c
);
int towlower(
   wint_t c
);
int _tolower_l(
   int c,
   _locale_t locale
);
int _towlower_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*C*<br/>
Karakter dönüştürmek için.

*Yerel ayar*<br/>
Yerel çeviri için kullanılacak yerel.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri, dönüştürme mümkünse *c'nin* bir kopyasını küçük harfe dönüştürür ve sonucu döndürür. Bir hatayı belirtmek için ayrılmış bir iade değeri yoktur.

## <a name="remarks"></a>Açıklamalar

Bu yordamların her biri, mümkün ve ilgili yse, belirli bir büyük harfi küçük harfe dönüştürür. Çekicinin **büyük/küçük** harf dönüşümü yerele özgüdür. Duruma göre yalnızca geçerli yerel eşle ilgili karakterler değiştirilir. **_l** sonek olmayan işlevler, şu anda ayarlanmış yerel ayaryı kullanır. **_l** sonek olan bu işlevlerin sürümleri, yerel alanı bir parametre olarak alır ve şu anda ayarlanmış yerel ayar yerine bunu kullanır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

**_tolower** beklenen sonuçları verebilmek [için, __isascii](isascii-isascii-iswascii.md) ve [isupper'ın](isupper-isupper-l-iswupper-iswupper-l.md) her ikisinin de sıfırsız dönmesi gerekir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totlower**|**Tolower**|**_mbctolower**|**çekici**|
|**_totlower_l**|**_tolower_l**|**_mbctolower_l**|**_towlower_l**|

> [!NOTE]
> **_tolower_l** ve **_towlower_l** yerel bağımlılık yoktur ve doğrudan çağrılmamalıdır. **Onlar _totlower_l**tarafından iç kullanım için sağlanmaktadır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Tolower**|\<ctype.h>|
|**_tolower**|\<ctype.h>|
|**çekici**|\<ctype.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[İşlevler'deki](../../c-runtime-library/to-functions.md)örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[olduğunu, isw Rutinleri](../../c-runtime-library/is-isw-routines.md)<br/>
[to İşlevleri](../../c-runtime-library/to-functions.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
