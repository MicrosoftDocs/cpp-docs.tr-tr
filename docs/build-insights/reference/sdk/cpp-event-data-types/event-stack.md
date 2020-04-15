---
title: EventStack sınıfı
description: C++ Build Insights SDK EventStack sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: eaaaedcbf57fdaf8e437a80a7823488febac3e1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324977"
---
# <a name="eventstack-class"></a>EventStack sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `EventStack` [Olay](event.md) nesneleri topluluğudur. C++ Build Insights SDK'dan alınan tüm olaylar `EventStack` nesne biçiminde gelir. Bu yığındaki son giriş, şu anda işlenen olaydır. Son girişten önce gelen girişler geçerli olayın üst hiyerarşisidir. C++ Build Insights'ta kullanılan olay modeli hakkında daha fazla bilgi için [olay tablosuna](../event-table.md)bakın.

## <a name="syntax"></a>Sözdizimi

```cpp
class EventStack
{
public:
    EventStack(const EVENT_COLLECTION_DATA& data);

    size_t      Size() const;
    RawEvent    Back() const;
    RawEvent    operator[] (size_t index) const;
};
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

[EventStack](#event-stack)

### <a name="functions"></a>İşlevler

[Geri](#back)
[operatör[]](#subscript-operator)
[Boyut](#size)

## <a name="back"></a><a name="back"></a>Geri

```cpp
RawEvent Back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yığındaki son girişi temsil eden bir [RawEvent](raw-event.md) nesnesi. Olay yığınındaki son giriş tetiklenen olaydır.

## <a name="eventstack"></a><a name="event-stack"></a>EventStack

```cpp
EventStack(const EVENT_COLLECTION_DATA& data);
```

### <a name="parameters"></a>Parametreler

*Veri*\
Üretilen ham veriler. `EventStack`

### <a name="remarks"></a>Açıklamalar

Genellikle nesneleri kendiniz oluşturmanız `EventStack` gerekmez. Olaylar bir analiz veya yeniden kaydetme oturumu sırasında işlenirken C++ Build Insights SDK tarafından sağlanır.

## <a name="operator"></a><a name="subscript-operator"></a>işleç[]

```cpp
RawEvent operator[] (size_t index) const;
```

### <a name="parameters"></a>Parametreler

*Dizin*\
Olay yığınına erişecek öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Olay yığınında *dizin* tarafından gösterilen konumda depolanan olayı temsil eden bir [RawEvent](raw-event.md) nesnesi.

## <a name="size"></a><a name="size"></a>Boyutu

```cpp
size_t Size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olay yığınının boyutu.

::: moniker-end
