---
title: duration_values Yapısı
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::duration_values
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
ms.openlocfilehash: ba4b202a5c8c6da742ac884bf58a5b8c55373d14
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454296"
---
# <a name="durationvalues-structure"></a>duration_values Yapısı

[Süre](../standard-library/duration-class.md) şablon parametresi `Rep`için belirli değerler sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Rep>
struct duration_values;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[max](#max)|Se. Türünde `Rep`bir değer için üst sınırı belirtir.|
|[min](#min)|Se. Türünde `Rep`bir değer için alt sınırı belirtir.|
|[sıfırlama](#zero)|Se. Döndürür `Rep(0)`.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<> hatası

**Ad alanı:** std:: hatası

## <a name="max"></a>duration_values:: Max

Türündeki `Ref`değerler için üst sınırı döndüren statik yöntem.

```cpp
static constexpr Rep max();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döndürür `numeric_limits<Rep>::max()`.

### <a name="remarks"></a>Açıklamalar

Kullanıcı `Rep` tanımlı bir tür olduğunda, dönüş değeri [duration_values:: Zero](#zero)değerinden büyük olmalıdır.

## <a name="min"></a>duration_values:: min

Türündeki `Ref`değerler için alt sınır döndüren statik yöntem.

```cpp
static constexpr Rep min();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döndürür `numeric_limits<Rep>::lowest()`.

### <a name="remarks"></a>Açıklamalar

Kullanıcı `Rep` tanımlı bir tür olduğunda, dönüş değeri [duration_values:: Zero](#zero)değerinden küçük veya buna eşit olmalıdır.

## <a name="zero"></a>duration_values:: Zero

Döndürür `Rep(0)`.

```cpp
static constexpr Rep zero();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı `Rep` tanımlı bir tür olduğunda, dönüş değeri, eklenebilir sonsuzu temsil etmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<> hatası](../standard-library/chrono.md)
