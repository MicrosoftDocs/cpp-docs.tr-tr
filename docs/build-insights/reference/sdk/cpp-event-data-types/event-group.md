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
ms.openlocfilehash: 57cbc7a053132909149aee182b9560e2ee33c161
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923311"
---
# <a name="eventgroup-class"></a>EventGroup sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`EventGroup`Sınıf şablonu, tüm Grup yakalama sınıfları için temel sınıftır.

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

[Geri](#back) 
 [Başlangıç](#begin) 
 [son](#end) 
 [Ön](#front) 
 [operator []](#subscript-operator) 
 [Boyut](#size)

## <a name="back"></a><a name="back"></a> Geri

```cpp
const TActivity& Back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gruptaki son etkinlik olayına bir başvuru.

## <a name="begin"></a><a name="begin"></a> başladı

```cpp
std::deque<TActivity>::const_iterator begin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinlik olay grubunun başlangıcına işaret eden bir yineleyici.

## <a name="end"></a><a name="end"></a> erer

```cpp
std::deque<TActivity>::const_iterator end() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinlik olay grubu sonunun ötesinde bir konum gösteren bir yineleyici.

## <a name="front"></a><a name="front"></a> Yapılan

```cpp
const TActivity& Front() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gruptaki ilk etkinlik olayına bir başvuru.

## <a name="operator"></a><a name="subscript-operator"></a> operator []

```cpp
const TActivity& operator[](size_t index) const;
```

### <a name="parameters"></a>Parametreler

*indeks*\
Etkinlik olay grubuna erişmek için öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

*Dizin* tarafından belirtilen konumda depolanan olay yığınından olay.

## <a name="size"></a><a name="size"></a> Boyutla

```cpp
size_t Size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olay grubunun boyutu.

::: moniker-end
