---
title: TRACE_INFO_DATA yapısı
description: C++ Yapı Öngörüleri SDK yapı referansı TRACE_INFO_DATA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACE_INFO_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 70ae17a376f79cad7a669d81e482f551afd0ec62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325274"
---
# <a name="trace_info_data-structure"></a>TRACE_INFO_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı, `TRACE_INFO_DATA` analiz edilen veya yeniden kaydedilen bir izlemeyi açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct TRACE_INFO_DATA_TAG
{
    unsigned long           LogicalProcessorCount;
    long long               TickFrequency;
    long long               StartTimestamp;
    long long               StopTimestamp;

} TRACE_INFO_DATA;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `LogicalProcessorCount` | İzlemenin toplandığı makinedeki mantıksal işlemci sayısı. |
| `TickFrequency` | Kenecinsinden ölçülen bir süreyi değerlendirirken kullanılacak saniye başına keneler sayısı. |
| `StartTimestamp` | Bu alan, izlemenin başlatıldıkı sırada yakalanan bir kene değerine ayarlanır. |
| `StopTimestamp` | Bu alan, izleme durdurulduğu sırada yakalanan bir kene değerine ayarlanır. |

## <a name="remarks"></a>Açıklamalar

Tüm `StartTimestamp` izleme `StopTimestamp` sırasında geçen kene sayısını elde etmek için çıkarma. Elde `TickFrequency` edilen değeri bir zaman birimine dönüştürmek için kullanın. Keneleri zaman birimlerine dönüştüren bir örnek [EVENT_DATA](event-data-struct.md)için bkz.

::: moniker-end
