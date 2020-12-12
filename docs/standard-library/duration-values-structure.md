---
description: 'Daha fazla bilgi edinin: duration_values yapısı'
title: duration_values Yapısı
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::duration_values
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
ms.openlocfilehash: 9bf784b0976a06c6d395498084508251d9ebd4bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324481"
---
# <a name="duration_values-structure"></a>duration_values Yapısı

[Süre](../standard-library/duration-class.md) şablon parametresi için belirli değerler sağlar `Rep` .

## <a name="syntax"></a>Syntax

```cpp
template <class Rep>
struct duration_values;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Biçimlendir](#max)|Statik. Türünde bir değer için üst sınırı belirtir `Rep` .|
|[Min](#min)|Statik. Türünde bir değer için alt sınırı belirtir `Rep` .|
|[sıfırlama](#zero)|Statik. `Rep(0)` döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<chrono>

**Ad alanı:** std:: hatası

## <a name="duration_valuesmax"></a><a name="max"></a> duration_values:: Max

Türündeki değerler için üst sınırı döndüren statik yöntem `Ref` .

```cpp
static constexpr Rep max();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döndürür `numeric_limits<Rep>::max()` .

### <a name="remarks"></a>Açıklamalar

`Rep`Kullanıcı tanımlı bir tür olduğunda, dönüş değeri [duration_values:: Zero](#zero)değerinden büyük olmalıdır.

## <a name="duration_valuesmin"></a><a name="min"></a> duration_values:: min

Türündeki değerler için alt sınır döndüren statik yöntem `Ref` .

```cpp
static constexpr Rep min();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döndürür `numeric_limits<Rep>::lowest()` .

### <a name="remarks"></a>Açıklamalar

`Rep`Kullanıcı tanımlı bir tür olduğunda, dönüş değeri [duration_values:: Zero](#zero)değerinden küçük veya buna eşit olmalıdır.

## <a name="duration_valueszero"></a><a name="zero"></a> duration_values:: sıfır

`Rep(0)` döndürür.

```cpp
static constexpr Rep zero();
```

### <a name="remarks"></a>Açıklamalar

`Rep`Kullanıcı tanımlı bir tür olduğunda, dönüş değeri, eklenebilir sonsuzu temsil etmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)
