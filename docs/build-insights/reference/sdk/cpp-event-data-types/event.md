---
title: Etkinlik sınıfı
description: C++ Build Insights SDK Olay sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Event
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 25d58f642a1c314e48ddff62553394bcc65e4717
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324960"
---
# <a name="event-class"></a>Etkinlik sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf `Event` [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)ve [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) işlevleri ile kullanılır. Herhangi bir olay maç için kullanın.

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
[EventId](#event-id)\
[EventInstanceId](#event-instance-id)\
[Olay Adı](#event-name)\
[EventWideName](#event-wide-name)\
[Processıd](#process-id)\
[İşleme Dizini](#processor-index)\
[Threadıd](#thread-id)\
[Tickfrequency](#tick-frequency)\
[Zaman damgası](#timestamp)

## <a name="event"></a><a name="entity"></a>Olay

```cpp
Event(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*Olay*\
Herhangi bir olay.

## <a name="data"></a><a name="data"></a>Veri

```cpp
const void* Data() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu olayda bulunan ek veri için bir işaretçi. Bu alanın nasıl yorumlanacağı hakkında daha fazla bilgi için [EVENT_DATA.](../c-event-data-types/event-data-struct.md)

## <a name="eventid"></a><a name="event-id"></a>Eventıd

```cpp
const unsigned short& EventId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olay türünü tanımlayan bir sayı. Olay tanımlayıcılarının listesi için [bkz. EVENT_ID.](../c-event-data-types/event-id-enum.md)

## <a name="eventinstanceid"></a><a name="event-instance-id"></a>EventInstanceId

```cpp
const unsigned long long& EventInstanceId() const;
```

### <a name="return-value"></a>Dönüş Değeri

İziçindeki olayı benzersiz olarak tanımlayan bir sayı. Aynı izlemeyi birden çok kez analiz ederken veya yeniden günlüğe kaydederken bu değer değişmez. Aynı olayı birden çok çözümlemede veya aynı izleme üzerinde yeniden günlüğe kaydetme geçişlerinde tanımlamak için bu değeri kullanın.

## <a name="eventname"></a><a name="event-name"></a>Olay Adı

```cpp
const char* EventName() const;
```

### <a name="return-value"></a>Dönüş Değeri

[EventId](#event-id)tarafından tanımlanan olay türünün adını içeren bir ANSI dizesi.

## <a name="eventwidename"></a><a name="event-wide-name"></a>EventWideName

```cpp
const wchar_t* EventWideName() const;
```

### <a name="return-value"></a>Dönüş Değeri

[EventId](#event-id)tarafından tanımlanan olayın adını içeren geniş bir dize.

## <a name="processid"></a><a name="process-id"></a>Processıd

```cpp
const unsigned long& ProcessId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayın oluştuğu işlemin tanımlayıcısı.

## <a name="processorindex"></a><a name="processor-index"></a>İşleme Dizini

```cpp
const unsigned short& ProcessorIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayın oluştuğu mantıksal işlemcinin sıfır tabanlı dizini.

## <a name="threadid"></a><a name="thread-id"></a>Threadıd

```cpp
const unsigned long& ThreadId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayın oluştuğu iş parçacığı için tanımlayıcı.

## <a name="tickfrequency"></a><a name="tick-frequency"></a>Tickfrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu olay için kene cinsinden ölçülen bir süreyi değerlendirirken kullanılacak saniye başına keneler sayısı.

## <a name="timestamp"></a><a name="timestamp"></a>Zaman damgası

```cpp
const long long& Timestamp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olay bir etkinlikse, bu işlev, etkinliğin başlatıldıkı anda yakalanan bir onay değeri döndürür. Basit bir olay için, bu işlev olay oluştuğu anda yakalanan bir onay değeri döndürür.

::: moniker-end
