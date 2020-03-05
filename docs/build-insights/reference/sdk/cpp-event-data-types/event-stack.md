---
title: EventStack sınıfı
description: C++ Build Insights SDK 'Sı eventstack sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6da2fd25082399b82d788c5d119a39e2f7388714
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333407"
---
# <a name="eventstack-class"></a>EventStack sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`EventStack` sınıfı, [olay](event.md) nesneleri koleksiyonudur. C++ BUILD Insights SDK 'sından alınan tüm olaylar `EventStack` nesne biçiminde gelir. Bu yığındaki son giriş, şu anda işlenmekte olan olaydır. Son girdiden önce gelen girişler geçerli etkinliğin ana hiyerarşisidir. Build Insights 'ta C++ kullanılan olay modeli hakkında daha fazla bilgi için bkz. [Event Table](../event-table.md).

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

[Back](#back)
[operator []](#subscript-operator)
[boyutu](#size)

## <a name="back"></a>Geri

```cpp
RawEvent Back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yığındaki son girişi temsil eden bir [Rawevent](raw-event.md) nesnesi. Olay yığınındaki son giriş, tetiklenen olaydır.

## <a name="event-stack"></a>EventStack

```cpp
EventStack(const EVENT_COLLECTION_DATA& data);
```

### <a name="parameters"></a>Parametreler

*veri*\
`EventStack` oluşturulduğu ham veriler.

### <a name="remarks"></a>Açıklamalar

Genellikle `EventStack` nesneleri oluşturmanız gerekmez. Bunlar, analiz veya yeniden günlüğe kaydetme C++ oturumu sırasında olaylar Işlendiğinde Build Insights SDK 'sı tarafından size sağlanır.

## <a name="subscript-operator"></a>operator []

```cpp
RawEvent operator[] (size_t index) const;
```

### <a name="parameters"></a>Parametreler

*dizin*\
Olay yığınında erişmek için öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Olay yığınındaki *Dizin* tarafından belirtilen konumda depolanan olayı temsil eden bir [rawevent](raw-event.md) nesnesi.

## <a name="size"></a>Boyutla

```cpp
size_t Size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olay yığınının boyutu.

::: moniker-end
