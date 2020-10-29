---
title: TraceInfo sınıfı
description: C++ Build Insights SDK TraceInfo sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TraceInfo
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b772cc13981720c73238e56a561ca92144775cb4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922915"
---
# <a name="traceinfo-class"></a>TraceInfo sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`TraceInfo`Sınıfı, analiz edilen veya yeniden günlüğe kaydedilen bir izleme hakkında faydalı özelliklere erişmek için kullanılır.

## <a name="syntax"></a>Syntax

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

`StartTimestamp` `StopTimestamp` Tüm izleme sırasında geçen onay işareti sayısını almak için ' den çıkarın. `TickFrequency`Elde edilen değeri bir zaman birimine dönüştürmek için kullanın. Zaman işaretlerini zamana dönüştürme örneği için bkz. [EVENT_DATA](../c-event-data-types/event-data-struct.md).

İşaretleri kendiniz dönüştürmek istemiyorsanız, `TraceInfo` sınıfı, izleme süresini nanosaniye cinsinden döndüren bir üye işlevi sağlar. `chrono`Bu değeri diğer zaman birimlerine dönüştürmek için standart C++ kitaplığını kullanın.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

[TraceInfo](#trace-info)

### <a name="functions"></a>İşlevler

[Süre](#duration) 
 [Logicalprocessorcount](#logical-processor-count) 
 [StartTimestamp](#start-timestamp) 
 [Stoptimestamp](#stop-timestamp) 
 [TickFrequency](#tick-frequency)

## <a name="duration"></a><a name="duration"></a> Sürenin

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkinliğin nanosaniye cinsinden süresi.

## <a name="logicalprocessorcount"></a><a name="logical-processor-count"></a> LogicalProcessorCount

```cpp
const unsigned long& LogicalProcessorCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

, İzlemenin toplandığı makinedeki mantıksal işlemcilerin sayısı.

## <a name="starttimestamp"></a><a name="start-timestamp"></a> StartTimestamp

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>Dönüş Değeri

İzleme başlatıldığı sırada yakalanan bir değer çizgisi.

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a> StopTimestamp

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>Dönüş Değeri

İzleme durdurulduğu sırada yakalanan bir değer çizgisi.

## <a name="tickfrequency"></a><a name="tick-frequency"></a> TickFrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zaman işaretleri cinsinden ölçülen bir süre değerlendirilirken kullanılacak saniye başına düşen saat sayısı.

## <a name="traceinfo"></a><a name="trace-info"></a> TraceInfo

```cpp
TraceInfo(const TRACE_INFO_DATA& data);
```

### <a name="parameters"></a>Parametreler

*verileri*\
İzleme hakkındaki bilgileri içeren veriler.

::: moniker-end
