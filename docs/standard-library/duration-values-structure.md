---
title: duration_values Yapısı
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::duration_values
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
ms.openlocfilehash: e2c03b4540ea5f89843562d1310b71635b3bc259
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368741"
---
# <a name="duration_values-structure"></a>duration_values Yapısı

[Süre](../standard-library/duration-class.md) şablonu parametresi `Rep`için belirli değerler sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Rep>
struct duration_values;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Max](#max)|Statik. Bir tür `Rep`değeri için üst sınırı belirtir.|
|[Dk](#min)|Statik. Bir tür `Rep`değeri için alt sınırı belirtir.|
|[sıfır](#zero)|Statik. `Rep(0)` döndürür.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono>

**Ad alanı:** std::chrono

## <a name="duration_valuesmax"></a><a name="max"></a>duration_values::max

Tür `Ref`değerleri için üst sınırı döndüren statik yöntem.

```cpp
static constexpr Rep max();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döner. `numeric_limits<Rep>::max()`

### <a name="remarks"></a>Açıklamalar

Kullanıcı `Rep` tanımlı bir tür olduğunda, iade değeri duration_values büyük [olmalıdır::sıfır](#zero).

## <a name="duration_valuesmin"></a><a name="min"></a>duration_values::dk

Tür `Ref`değerleri için alt sınırı döndüren statik yöntem.

```cpp
static constexpr Rep min();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döner. `numeric_limits<Rep>::lowest()`

### <a name="remarks"></a>Açıklamalar

Kullanıcı `Rep` tanımlı bir tür olduğunda, iade değeri duration_values'dan küçük veya eşit [olmalıdır:sıfır.](#zero)

## <a name="duration_valueszero"></a><a name="zero"></a>duration_values::sıfır

`Rep(0)` döndürür.

```cpp
static constexpr Rep zero();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı `Rep` tanımlı bir tür olduğunda, iade değeri katkı sonsuzluğu temsil etmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)
