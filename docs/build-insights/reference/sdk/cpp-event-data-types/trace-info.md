---
title: TraceInfo sınıfı
description: C++ Build Insights SDK TraceInfo sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TraceInfo
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 75d53937e3999f5692dee0ecf419e0ce5f49a274
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324167"
---
# <a name="traceinfo-class"></a>TraceInfo sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf, `TraceInfo` çözümlenen veya yeniden günlüğe kaydedilmiş bir izleme yle ilgili yararlı özelliklere erişmek için kullanılır.

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

Tüm izleme `StartTimestamp` `StopTimestamp` sırasında geçen kene sayısını elde etmek için çıkar. Elde `TickFrequency` edilen değeri bir zaman birimine dönüştürmek için kullanın. Keneleri zamana dönüştürme örneği için bkz. [EVENT_DATA.](../c-event-data-types/event-data-struct.md)

Keneleri kendiniz dönüştürmek istemiyorsanız, `TraceInfo` sınıf izleme süresini nanosaniye cinsinden döndüren bir üye işlev sağlar. Bu değeri diğer `chrono` zaman birimlerine dönüştürmek için standart C++ kitaplığını kullanın.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

[Traceınfo](#trace-info)

### <a name="functions"></a>İşlevler

[Süre](#duration)
[MantıksalİşlemerSayısı](#logical-processor-count)
[StartTimestamp](#start-timestamp)
[StopTimestamp](#stop-timestamp)
[TickFrequency](#tick-frequency)

## <a name="duration"></a><a name="duration"></a>Süre

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nanosaniye cinsinden etkinliğin süresi.

## <a name="logicalprocessorcount"></a><a name="logical-processor-count"></a>Mantıksalİşlemer Sayısı

```cpp
const unsigned long& LogicalProcessorCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

İzlemenin toplandığı makinedeki mantıksal işlemci sayısı.

## <a name="starttimestamp"></a><a name="start-timestamp"></a>Başlangıç Zamanı Damgası

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>Dönüş Değeri

İzlemenin başlatıldıında yakalanan bir kene dedesi.

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a>StopTimestamp

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>Dönüş Değeri

İzleme durdurulduğu sırada yakalanan bir onay değeri.

## <a name="tickfrequency"></a><a name="tick-frequency"></a>Tickfrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kenecinsinden ölçülen bir süreyi değerlendirirken kullanılacak saniye başına keneler sayısı.

## <a name="traceinfo"></a><a name="trace-info"></a>Traceınfo

```cpp
TraceInfo(const TRACE_INFO_DATA& data);
```

### <a name="parameters"></a>Parametreler

*Veri*\
İzleme yle ilgili bilgileri içeren veriler.

::: moniker-end
