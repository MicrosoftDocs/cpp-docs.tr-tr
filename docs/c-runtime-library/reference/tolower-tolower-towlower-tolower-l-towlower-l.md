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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: c8b27c4cc618d34d9da9b5884c6db2f525fd2388
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910005"
---
# <a name="tolower-_tolower-towlower-_tolower_l-_towlower_l"></a>tolower, _tolower, towlower, _tolower_l, _towlower_l

Karakteri küçük harfe dönüştürür.

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

*,*<br/>
Dönüştürülecek karakter.

*locale*<br/>
Yerel ayara özgü çeviri için kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri, dönüştürme mümkün olduğunda *c* 'nin bir kopyasını küçük harfe dönüştürür ve sonucu döndürür. Bir hatayı göstermek için ayrılmış dönüş değeri yok.

## <a name="remarks"></a>Açıklamalar

Bu yordamların her biri, belirli bir büyük harfi mümkünse küçük harfe dönüştürür ve uygunsa. **Kasadan düşük** durum dönüştürmesi, yerel ayara özgüdür. Durum durumunda yalnızca geçerli yerel ayara uygun karakterler değişir. **_L** soneki olmayan işlevler şu anda ayarlanmış yerel ayarı kullanır. **_L** sonekine sahip bu işlevlerin sürümleri, yerel ayarı bir parametre olarak alır ve şu anda ayarlanmış yerel ayar yerine bunu kullanır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

**_Tolower** beklenen sonuçlara izin vermek için, [__isascii](isascii-isascii-iswascii.md) ve [ıupper](isupper-isupper-l-iswupper-iswupper-l.md) öğelerinin ikisi de sıfır dışında döndürülmelidir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totlower**|**ToLower**|**_mbctolower**|**kasadan düşük**|
|**_totlower_l**|**_tolower_l**|**_mbctolower_l**|**_towlower_l**|

> [!NOTE]
> **_tolower_l** ve **_towlower_l** yerel ayar bağımlılığını yoktur ve doğrudan çağrılması için tasarlanmamıştır. **_Totlower_l**tarafından iç kullanım için sağlanır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ToLower**|\<CType. h>|
|**_tolower**|\<CType. h>|
|**kasadan düşük**|\<CType. h> veya \<wchar. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bkz. [işlevleri](../../c-runtime-library/to-functions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[, isw yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[to İşlevleri](../../c-runtime-library/to-functions.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
