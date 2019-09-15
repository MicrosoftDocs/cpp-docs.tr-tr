---
title: toupper, _toupper, towupper, _toupper_l, _towupper_l
ms.date: 11/04/2016
api_name:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
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
ms.openlocfilehash: e17f139789b2c37292764f2e4508b59cddd2c03e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957912"
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

*c*<br/>
Dönüştürülecek karakter.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri, mümkünse *c*'nin bir kopyasını dönüştürür ve sonucu döndürür.

*C* , **ıswlower** 'in sıfır dışında olduğu geniş bir karakter ise ve [ıswupper](isupper-isupper-l-iswupper-iswupper-l.md) 'in sıfır dışında olduğu bir geniş karakter varsa, **towupper** karşılık gelen geniş karakteri döndürür; Aksi takdirde, **towupper** *c* değerini değiştirmez.

Bir hatayı göstermek için ayrılmış dönüş değeri yok.

**ToUpper** 'in beklenen sonuçlara izin vermesi için [__isascıı](isascii-isascii-iswascii.md) ve [ılower](islower-iswlower-islower-l-iswlower-l.md) öğelerinin ikisi de sıfır dışında döndürülmelidir.

## <a name="remarks"></a>Açıklamalar

Bu yordamların her biri, mümkün olan ve uygunsa, belirli bir küçük harfi büyük harfe dönüştürür. **Kasasının** büyük/küçük harf dönüştürmesi yerel ayara özgüdür. Durum durumunda yalnızca geçerli yerel ayara uygun karakterler değişir. **_L** soneki olmayan işlevler şu anda ayarlanmış yerel ayarı kullanır. **_L** sonekine sahip bu işlevlerin sürümleri, yerel ayarı bir parametre olarak alır ve şu anda ayarlanmış yerel ayar yerine bunu kullanır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

**ToUpper** 'in beklenen sonuçlara izin vermesi için [__isascıı](isascii-isascii-iswascii.md) ve [ıupper](isupper-isupper-l-iswupper-iswupper-l.md) öğelerinin ikisi de sıfır dışında döndürülmelidir.

[Veri dönüştürme yordamları](../../c-runtime-library/data-conversion.md)

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_totupper**|**ToUpper**|**_mbctoupper**|**kasaüstü**|
|**_totupper_l**|**_toüste_l**|**_mbctoupper_l**|**_towüste_l**|

> [!NOTE]
> **_toüste_l** ve **_towüste_l** yerel ayar bağımlılığını içermez ve doğrudan çağrılmamalıdır. **_Totupper_l**tarafından iç kullanım için sağlanır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ToUpper**|\<CType. h >|
|**_toupper**|\<CType. h >|
|**kasaüstü**|\<CType. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bkz. [işlevleri](../../c-runtime-library/to-functions.md).

## <a name="see-also"></a>Ayrıca bkz.

[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[to İşlevleri](../../c-runtime-library/to-functions.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
