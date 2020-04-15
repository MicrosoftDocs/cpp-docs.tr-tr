---
title: EventGroup sınıfı
description: C++ Build Insights SDK EventGroup sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 596c18ca0e9b4d7b26c4ed5209b16871952c4af2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324996"
---
# <a name="eventgroup-class"></a>EventGroup sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `EventGroup` şablonu, tüm grup yakalama sınıfları için taban sınıftır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename TActivity>
class EventGroup;
{
public:
    size_t Size() const;

    const TActivity& operator[](size_t index) const;
    const TActivity& Front() const;
    const TActivity& Back() const;

    std::deque<TActivity>::const_iterator begin() const;
    std::deque<TActivity>::const_iterator end() const;
};
```

### <a name="parameters"></a>Parametreler

*Taktivite* Grupta bulunan etkinlik türü.

## <a name="members"></a>Üyeler

### <a name="functions"></a>İşlevler

[Geri](#back)
[başlatma](#begin)
[sonu](#end)
[Ön](#front)
[işleç[]](#subscript-operator)
[Boyut](#size)

## <a name="back"></a><a name="back"></a>Geri

```cpp
const TActivity& Back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gruptaki son etkinlik olayına bir başvuru.

## <a name="begin"></a><a name="begin"></a>Başlamak

```cpp
std::deque<TActivity>::const_iterator begin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinlik olay grubunun başına işaret eden bir yineleyici.

## <a name="end"></a><a name="end"></a>Son -unda

```cpp
std::deque<TActivity>::const_iterator end() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinlik olay grubunun sonuna doğru bir pozisyonu gösteren bir yineleyici.

## <a name="front"></a><a name="front"></a>Ön

```cpp
const TActivity& Front() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gruptaki ilk etkinlik olayına bir başvuru.

## <a name="operator"></a><a name="subscript-operator"></a>işleç[]

```cpp
const TActivity& operator[](size_t index) const;
```

### <a name="parameters"></a>Parametreler

*Dizin*\
Etkinlik olay grubunda erişilen öğenin dizin.

### <a name="return-value"></a>Dönüş Değeri

*Dizin tarafından*belirtilen konumda depolanan olay yığınından olay.

## <a name="size"></a><a name="size"></a>Boyutu

```cpp
size_t Size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olay grubunun boyutu.

::: moniker-end
