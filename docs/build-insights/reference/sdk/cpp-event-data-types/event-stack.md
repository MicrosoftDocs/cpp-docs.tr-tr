---
title: EventStack sınıfı
description: C++ Build Insights SDK 'Sı EventStack sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b4f1e92011acdf8272fe631843c03c2f960a1234
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920716"
---
# <a name="eventstack-class"></a>EventStack sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`EventStack`Sınıfı, bir [olay](event.md) nesneleri koleksiyonudur. C++ Build Insights SDK 'sından alınan tüm olaylar bir nesne biçiminde gelir `EventStack` . Bu yığındaki son giriş, şu anda işlenmekte olan olaydır. Son girdiden önce gelen girişler geçerli etkinliğin ana hiyerarşisidir. C++ Build Insights 'ta kullanılan olay modeli hakkında daha fazla bilgi için bkz. [Event Table](../event-table.md).

## <a name="syntax"></a>Syntax

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
 [operator []](#subscript-operator) 
 [Boyut](#size)

## <a name="back"></a><a name="back"></a> Geri

```cpp
RawEvent Back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yığındaki son girişi temsil eden bir [Rawevent](raw-event.md) nesnesi. Olay yığınındaki son giriş, tetiklenen olaydır.

## <a name="eventstack"></a><a name="event-stack"></a> EventStack

```cpp
EventStack(const EVENT_COLLECTION_DATA& data);
```

### <a name="parameters"></a>Parametreler

*verileri*\
Oluşturulan ham veri `EventStack` .

### <a name="remarks"></a>Açıklamalar

Genellikle `EventStack` nesneleri kendiniz oluşturmanız gerekmez. Bunlar, analiz veya yeniden günlüğe kaydetme oturumu sırasında olaylar işlendiğinde C++ Build Insights SDK 'Sı tarafından size sağlanır.

## <a name="operator"></a><a name="subscript-operator"></a> operator []

```cpp
RawEvent operator[] (size_t index) const;
```

### <a name="parameters"></a>Parametreler

*indeks*\
Olay yığınında erişmek için öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Olay yığınındaki *Dizin* tarafından belirtilen konumda depolanan olayı temsil eden bir [rawevent](raw-event.md) nesnesi.

## <a name="size"></a><a name="size"></a> Boyutla

```cpp
size_t Size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olay yığınının boyutu.

::: moniker-end
