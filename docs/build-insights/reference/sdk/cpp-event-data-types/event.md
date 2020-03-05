---
title: Event sınıfı
description: C++ Build Insights SDK 'sı olay sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Event
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 205a4e0ca9dd9449933f38f02d4ceafd5df8ead2
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333400"
---
# <a name="event-class"></a>Event sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`Event` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Herhangi bir olayla eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class Event
{
public:
    Event(const RawEvent& event);

    const unsigned short&        EventId() const;
    const unsigned long long&    EventInstanceId() const;
    const long long&             TickFrequency() const;
    const long long&             Timestamp() const;
    const unsigned long&         ProcessId() const;
    const unsigned long&         ThreadId() const;
    const unsigned short&        ProcessorIndex() const;
    const char*                  EventName() const;
    const wchar_t*               EventWideName() const;
};
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

[Olay](#entity)

### <a name="functions"></a>İşlevler

[Veri](#data)
[EventID](#event-id)\
[Eventınstanceıd](#event-instance-id)\
[EventName](#event-name)\
[EventWideName](#event-wide-name)\
[İşlemkimliği](#process-id)\
[Processorındex](#processor-index)\
[ThreadID](#thread-id)\
[TickFrequency](#tick-frequency)\
[İlişkin](#timestamp)

## <a name="entity"></a>Olay

```cpp
Event(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
Herhangi bir olay.

## <a name="data"></a>Verileri

```cpp
const void* Data() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu olayda bulunan ek verilere yönelik bir işaretçi. Bu alanı yorumlama hakkında daha fazla bilgi için bkz. [EVENT_DATA](../c-event-data-types/event-data-struct.md).

## <a name="event-id"></a>Even

```cpp
const unsigned short& EventId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olay türünü tanımlayan bir sayı. Olay tanımlayıcılarının listesi için bkz. [EVENT_ID](../c-event-data-types/event-id-enum.md).

## <a name="event-instance-id"></a>Eventınstanceıd

```cpp
const unsigned long long& EventInstanceId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayı bir izleme içinde benzersiz bir şekilde tanımlayan bir sayı. Bu değer, aynı izlemeyi birden çok kez analiz veya yeniden günlüğe kaydetme sırasında değişmez. Aynı olayı birden çok çözümlemede veya yeniden günlüğe kaydetmenin aynı izleme üzerinden tanımlamak için bu değeri kullanın.

## <a name="event-name"></a>EventName

```cpp
const char* EventName() const;
```

### <a name="return-value"></a>Dönüş Değeri

[EventID](#event-id)tarafından tanımlanan olay türünün adını IÇEREN bir ANSI dizesi.

## <a name="event-wide-name"></a>EventWideName

```cpp
const wchar_t* EventWideName() const;
```

### <a name="return-value"></a>Dönüş Değeri

[EventID](#event-id)tarafından tanımlanan olayın adını içeren geniş bir dize.

## <a name="process-id"></a>Işlem

```cpp
const unsigned long& ProcessId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayın gerçekleştiği işlemin tanımlayıcısı.

## <a name="processor-index"></a>Processorındex

```cpp
const unsigned short& ProcessorIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayın gerçekleştiği mantıksal işlemcinin sıfır tabanlı dizini.

## <a name="thread-id"></a>ThreadID

```cpp
const unsigned long& ThreadId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayın gerçekleştiği iş parçacığının tanımlayıcısı.

## <a name="tick-frequency"></a>TickFrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu olay için zaman işaretleri cinsinden ölçülen bir süre değerlendirilirken kullanılacak saniye başına saat sayısı.

## <a name="timestamp"></a>İlişkin

```cpp
const long long& Timestamp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olay bir etkinlikse, bu işlev etkinliğin başlatıldığı zamanda yakalanan bir değer değeri döndürür. Basit bir olay için bu işlev, olay gerçekleştiği sırada yakalanan bir değer değeri döndürür.

::: moniker-end
