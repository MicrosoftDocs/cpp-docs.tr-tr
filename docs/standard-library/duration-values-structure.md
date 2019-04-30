---
title: duration_values Yapısı
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::duration_values
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
ms.openlocfilehash: bc382bbc408b11cbc18210f3ab944dda39adc8f2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413781"
---
# <a name="durationvalues-structure"></a>duration_values Yapısı

İçin belirli değerler sağlar [süresi](../standard-library/duration-class.md) şablon parametresi `Rep`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Rep>
struct duration_values;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[en fazla](#max)|Statik. Türünde bir değer üst sınırını belirtir `Rep`.|
|[Min](#min)|Statik. Türündeki bir değerin alt sınırını belirtir `Rep`.|
|[Sıfır](#zero)|Statik. Döndürür `Rep(0)`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono >

**Namespace:** std::chrono

## <a name="max"></a>  duration_values::Max

Türündeki değerlerin üst sınırını döndüren statik yöntem `Ref`.

```cpp
static constexpr Rep max();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında döndürür `numeric_limits<Rep>::max()`.

### <a name="remarks"></a>Açıklamalar

Zaman `Rep` bir kullanıcı tanımlı tür olduğunda döndürülen değer değerinden büyük olmalıdır [duration_values::zero](#zero).

## <a name="min"></a>  duration_values::Min

Türündeki değerlerin alt sınırını döndüren statik yöntem `Ref`.

```cpp
static constexpr Rep min();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında döndürür `numeric_limits<Rep>::lowest()`.

### <a name="remarks"></a>Açıklamalar

Zaman `Rep` bir kullanıcı tanımlı tür olduğunda döndürülen değer veya buna eşit olmalıdır [duration_values::zero](#zero).

## <a name="zero"></a>  duration_values::Zero

Döndürür `Rep(0)`.

```cpp
static constexpr Rep zero();
```

### <a name="remarks"></a>Açıklamalar

Zaman `Rep` bir kullanıcı tanımlı tür olduğunda döndürülen değer artırıcı sonsuzu göstermelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono >](../standard-library/chrono.md)<br/>
