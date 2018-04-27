---
title: duration_values yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- chrono/std::chrono::duration_values
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
dev_langs:
- C++
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a2cba8fd6fe3e4763e05dc0cc897e8a0b968d611
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="durationvalues-structure"></a>duration_values Yapısı

Belirli değerleri sağlar [süresi](../standard-library/duration-class.md) şablon parametresi `Rep`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Rep>
struct duration_values;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[max](#max)|Statik. Türünde bir değer üst sınırını belirtir `Rep`.|
|[Min](#min)|Statik. Türünde bir değer alt sınırı belirtir `Rep`.|
|[Sıfır](#zero)|Statik. Döndürür `Rep(0)`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono >

**Namespace:** std::chrono

## <a name="max"></a>  duration_values::Max

Türü değerleri için üst sınır döndüren statik yöntem `Ref`.

```cpp
static constexpr Rep max();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamada döndürür `numeric_limits<Rep>::max()`.

### <a name="remarks"></a>Açıklamalar

Zaman `Rep` bir kullanıcı tanımlı tür dönüş değeri büyük olmalı [duration_values::zero](#zero).

## <a name="min"></a>  duration_values::Min

Alt sınır türü değerleri için döndüren statik yöntem `Ref`.

```cpp
static constexpr Rep min();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamada döndürür `numeric_limits<Rep>::lowest()`.

### <a name="remarks"></a>Açıklamalar

Zaman `Rep` bir kullanıcı tanımlı tür dönüş değeri küçük veya eşit olmalıdır [duration_values::zero](#zero).

## <a name="zero"></a>  duration_values::Zero

Döndürür `Rep(0)`.

```cpp
static constexpr Rep zero();
```

### <a name="remarks"></a>Açıklamalar

Zaman `Rep` bir kullanıcı tanımlı tür eklenebilir sonsuz dönüş değerini temsil etmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono >](../standard-library/chrono.md)<br/>
