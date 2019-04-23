---
title: _udiv64
ms.date: 04/17/2019
f1_keywords:
- _udiv64
helpviewer_keywords:
- _udiv64 intrinsic
ms.openlocfilehash: 73a29b180eeda49a9a25e9e568d25c7563234fad
ms.sourcegitcommit: 2ce88de75e7681220ae09a0ab13056f22f357a46
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59983115"
---
# <a name="udiv64"></a>_udiv64

`_udiv64` İç bir 64-bit işaretsiz tamsayıyı 32-bit işaretsiz tamsayı ile böler. Sayının dönüş değerine ve iç işaretçi parametresi üzerinden kalanı döndürür. `_udiv64` olan **Microsoft'a özgü**.

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _udiv64(
   unsigned __int64 dividend,
   unsigned int divisor,
   unsigned int* remainder
);
```

### <a name="parameters"></a>Parametreler

*Bölünen*<br/>
[in] Bölmek için 64-bit işaretsiz tamsayı.

*bölen*<br/>
[in] Bölen 32-bit işaretsiz tamsayı.

*Kalan*<br/>
[out] Geri kalan 32-bit işaretsiz tamsayı.

## <a name="return-value"></a>Dönüş değeri

Sayının 32 bit.

## <a name="remarks"></a>Açıklamalar

`_udiv64` İç böler *bölünen* tarafından *bölen*. İşaret ettiği 32-bit işaretsiz tamsayı içinde kalan depolar *kalan*ve 32 bit sayının döndürür.

`_udiv64` İç Visual Studio 2019 için RTM'de mevcut başlatılıyor.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_udiv64`|x86, x64|\<immintrin.h >|

## <a name="see-also"></a>Ayrıca bkz.

[_div64](div64.md) \
[Derleyici iç bilgileri](compiler-intrinsics.md)
