---
description: 'Hakkında daha fazla bilgi edinin: ToUpper, _toupper, kasaüstü, _toupper_l, _towupper_l'
title: toupper, _toupper, towupper, _toupper_l, _towupper_l
ms.date: 4/2/2020
api_name:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
- _o__toupper
- _o__toupper_l
- _o__towupper_l
- _o_toupper
- _o_towupper
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- towupper
- _toupper
- _totupper
- toupper
helpviewer_keywords:
- _toupper function
- towupper function
- uppercase, converting strings to
- totupper function
- string conversion, to different characters
- towupper_l function
- toupper_l function
- string conversion, case
- _toupper_l function
- _towupper_l function
- _totupper function
- case, converting
- characters, converting
- toupper function
ms.assetid: cdef1b0f-b19c-4d11-b7d2-cf6334c9b6cc
ms.openlocfilehash: cb2a121d1fa96c0149a329520f5c71c1cc4f4d9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318318"
---
# <a name="toupper-_toupper-towupper-_toupper_l-_towupper_l"></a>toupper, _toupper, towupper, _toupper_l, _towupper_l

Karakteri büyük harfe Dönüştür.

## <a name="syntax"></a>Sözdizimi

```C
int toupper(
   int c
);
int _toupper(
   int c
);
int towupper(
   wint_t c
);
int _toupper_l(
   int c ,
   _locale_t locale
);
int _towupper_l(
   wint_t c ,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*,*<br/>
Dönüştürülecek karakter.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri, mümkünse *c*'nin bir kopyasını dönüştürür ve sonucu döndürür.

*C* , **ıswlower** 'in sıfır dışında olduğu geniş bir karakter ise ve [ıswupper](isupper-isupper-l-iswupper-iswupper-l.md) 'in sıfır dışında olduğu bir geniş karakter varsa, **towupper** karşılık gelen geniş karakteri döndürür; Aksi takdirde, **towupper** *c* değerini değiştirmez.

Bir hatayı göstermek için ayrılmış dönüş değeri yok.

**ToUpper** 'in beklenen sonuçlara izin vermesi için, [__isascii](isascii-isascii-iswascii.md) ve [ılower](islower-iswlower-islower-l-iswlower-l.md) öğelerinin her ikisi de sıfır dışında döndürülmelidir.

## <a name="remarks"></a>Açıklamalar

Bu yordamların her biri, mümkün olan ve uygunsa, belirli bir küçük harfi büyük harfe dönüştürür. **Kasasının** büyük/küçük harf dönüştürmesi yerel ayara özgüdür. Durum durumunda yalnızca geçerli yerel ayara uygun karakterler değişir. **_L** soneki olmayan işlevler şu anda ayarlanmış yerel ayarı kullanır. **_L** sonekine sahip bu işlevlerin sürümleri, yerel ayarı bir parametre olarak alır ve şu anda ayarlanmış yerel ayar yerine bunu kullanır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

**ToUpper** 'in beklenen sonuçlara izin vermesi için, [__isascii](isascii-isascii-iswascii.md) ve [ıupper](isupper-isupper-l-iswupper-iswupper-l.md) 'nin ikisi de sıfır dışında döndürmelidir.

[Veri dönüştürme yordamları](../../c-runtime-library/data-conversion.md)

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totupper**|**ToUpper**|**_mbctoupper**|**kasaüstü**|
|**_totupper_l**|**_toupper_l**|**_mbctoupper_l**|**_towupper_l**|

> [!NOTE]
> **_toupper_l** ve **_towupper_l** yerel ayar bağımlılığını yoktur ve doğrudan çağrılması için tasarlanmamıştır. **_Totupper_l** tarafından iç kullanım için sağlanır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ToUpper**|\<ctype.h>|
|**_toupper**|\<ctype.h>|
|**kasaüstü**|\<ctype.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bkz. [işlevleri](../../c-runtime-library/to-functions.md).

## <a name="see-also"></a>Ayrıca bkz.

[, isw yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[to Işlevleri](../../c-runtime-library/to-functions.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Multibyte-Character sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
