---
title: Event sınıfı
description: C++ derleme öngörüleri SDK 'Sı olay sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Event
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7dd96ffa3518c58e1b18312bb4fe2c36df26bd67
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923303"
---
# <a name="event-class"></a>Event sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`Event`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Herhangi bir olayla eşleştirmek için kullanın.

## <a name="syntax"></a>Syntax

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
[Işlem](#process-id)\
[Processorındex](#processor-index)\
[ThreadID](#thread-id)\
[TickFrequency](#tick-frequency)\
[Zaman damgası](#timestamp)

## <a name="event"></a><a name="entity"></a> Olay

```cpp
Event(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
Herhangi bir olay.

## <a name="data"></a><a name="data"></a> Verileri

```cpp
const void* Data() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu olayda bulunan ek verilere yönelik bir işaretçi. Bu alanı yorumlama hakkında daha fazla bilgi için bkz. [EVENT_DATA](../c-event-data-types/event-data-struct.md).

## <a name="eventid"></a><a name="event-id"></a> Even

```cpp
const unsigned short& EventId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olay türünü tanımlayan bir sayı. Olay tanımlayıcılarının listesi için bkz. [EVENT_ID](../c-event-data-types/event-id-enum.md).

## <a name="eventinstanceid"></a><a name="event-instance-id"></a> Eventınstanceıd

```cpp
const unsigned long long& EventInstanceId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayı bir izleme içinde benzersiz bir şekilde tanımlayan bir sayı. Bu değer, aynı izlemeyi birden çok kez analiz veya yeniden günlüğe kaydetme sırasında değişmez. Aynı olayı birden çok çözümlemede veya yeniden günlüğe kaydetmenin aynı izleme üzerinden tanımlamak için bu değeri kullanın.

## <a name="eventname"></a><a name="event-name"></a> EventName

```cpp
const char* EventName() const;
```

### <a name="return-value"></a>Dönüş Değeri

[EventID](#event-id)tarafından tanımlanan olay türünün adını IÇEREN bir ANSI dizesi.

## <a name="eventwidename"></a><a name="event-wide-name"></a> EventWideName

```cpp
const wchar_t* EventWideName() const;
```

### <a name="return-value"></a>Dönüş Değeri

[EventID](#event-id)tarafından tanımlanan olayın adını içeren geniş bir dize.

## <a name="processid"></a><a name="process-id"></a> Işlem

```cpp
const unsigned long& ProcessId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayın gerçekleştiği işlemin tanımlayıcısı.

## <a name="processorindex"></a><a name="processor-index"></a> Processorındex

```cpp
const unsigned short& ProcessorIndex() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayın gerçekleştiği mantıksal işlemcinin sıfır tabanlı dizini.

## <a name="threadid"></a><a name="thread-id"></a> ThreadID

```cpp
const unsigned long& ThreadId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olayın gerçekleştiği iş parçacığının tanımlayıcısı.

## <a name="tickfrequency"></a><a name="tick-frequency"></a> TickFrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu olay için zaman işaretleri cinsinden ölçülen bir süre değerlendirilirken kullanılacak saniye başına saat sayısı.

## <a name="timestamp"></a><a name="timestamp"></a> İlişkin

```cpp
const long long& Timestamp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olay bir etkinlikse, bu işlev etkinliğin başlatıldığı zamanda yakalanan bir değer değeri döndürür. Basit bir olay için bu işlev, olay gerçekleştiği sırada yakalanan bir değer değeri döndürür.

::: moniker-end
