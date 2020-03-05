---
title: TraceInfo sınıfı
description: C++ BUILD Insights SDK TraceInfo sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TraceInfo
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5cf32c8dc954a803a11888231d35b1050ac81cc3
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332945"
---
# <a name="traceinfo-class"></a>TraceInfo sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`TraceInfo` sınıfı, analiz edilen veya yeniden günlüğe kaydedilen bir izleme hakkında faydalı özelliklere erişmek için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
class TraceInfo
{
public:
    TraceInfo(const TRACE_INFO_DATA& data);

    const unsigned long& LogicalProcessorCount() const;

    const long long& TickFrequency() const;
    const long long& StartTimestamp() const;
    const long long& StopTimestamp() const;

    std::chrono::nanoseconds Duration() const;
};
```

## <a name="remarks"></a>Açıklamalar

Tüm izleme sırasında geçen onay işareti sayısını almak için `StopTimestamp` `StartTimestamp` çıkarın. Elde edilen değeri bir zaman birimine dönüştürmek için `TickFrequency` kullanın. Zaman işaretlerini zamana dönüştürme örneği için bkz. [EVENT_DATA](../c-event-data-types/event-data-struct.md).

İşaretleri kendiniz dönüştürmek istemiyorsanız, `TraceInfo` sınıfı, süre nanosaniye cinsinden izleme süresini döndüren bir üye işlevi sağlar. Bu değeri diğer C++ zaman birimlerine dönüştürmek için standart `chrono` kitaplığı 'nı kullanın.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

[TraceInfo](#trace-info)

### <a name="functions"></a>İşlevler

[
](#duration) [logicalprocessorcount](#logical-processor-count)
[starttimestamp](#start-timestamp)
[durma zaman damgası](#stop-timestamp)
[TickFrequency](#tick-frequency)

## <a name="duration"></a>Sürenin

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinliğin nanosaniye cinsinden süresi.

## <a name="logical-processor-count"></a>LogicalProcessorCount

```cpp
const unsigned long& LogicalProcessorCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

, İzlemenin toplandığı makinedeki mantıksal işlemcilerin sayısı.

## <a name="start-timestamp"></a>StartTimestamp

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>Dönüş Değeri

İzleme başlatıldığı sırada yakalanan bir değer çizgisi.

## <a name="stop-timestamp"></a>StopTimestamp

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>Dönüş Değeri

İzleme durdurulduğu sırada yakalanan bir değer çizgisi.

## <a name="tick-frequency"></a>TickFrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zaman işaretleri cinsinden ölçülen bir süre değerlendirilirken kullanılacak saniye başına düşen saat sayısı.

## <a name="trace-info"></a>TraceInfo

```cpp
TraceInfo(const TRACE_INFO_DATA& data);
```

### <a name="parameters"></a>Parametreler

*veri*\
İzleme hakkındaki bilgileri içeren veriler.

::: moniker-end
