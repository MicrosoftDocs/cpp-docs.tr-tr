---
title: EventGroup sınıfı
description: C++ Build Insights SDK 'Sı EventGroup sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ac8ac70f3fc160714b86dd0c483808a4d06e7699
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333435"
---
# <a name="eventgroup-class"></a>EventGroup sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`EventGroup` sınıf şablonu, tüm Grup yakalama sınıfları için temel sınıftır.

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

*TActivity* Grupta yer alan etkinlik türü.

## <a name="members"></a>Üyeler

### <a name="functions"></a>İşlevler

[Back](#back)
[end](#end)
[ön](#front)
[operator []](#subscript-operator)
[Boyut](#size)
[başla](#begin)

## <a name="back"></a>Geri

```cpp
const TActivity& Back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gruptaki son etkinlik olayına bir başvuru.

## <a name="begin"></a>başladı

```cpp
std::deque<TActivity>::const_iterator begin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinlik olay grubunun başlangıcına işaret eden bir yineleyici.

## <a name="end"></a>erer

```cpp
std::deque<TActivity>::const_iterator end() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinlik olay grubu sonunun ötesinde bir konum gösteren bir yineleyici.

## <a name="front"></a>Yapılan

```cpp
const TActivity& Front() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gruptaki ilk etkinlik olayına bir başvuru.

## <a name="subscript-operator"></a>operator []

```cpp
const TActivity& operator[](size_t index) const;
```

### <a name="parameters"></a>Parametreler

*dizin*\
Etkinlik olay grubuna erişmek için öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

*Dizin*tarafından belirtilen konumda depolanan olay yığınından olay.

## <a name="size"></a>Boyutla

```cpp
size_t Size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olay grubunun boyutu.

::: moniker-end
