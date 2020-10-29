---
title: TRACE_INFO_DATA yapısı
description: C++ derleme öngörüleri SDK TRACE_INFO_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACE_INFO_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ce6301b168aed9f279fc7aaee9aa3a97221fd23a
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923423"
---
# <a name="trace_info_data-structure"></a>TRACE_INFO_DATA yapısı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`TRACE_INFO_DATA`Yapı, analiz edilen veya yeniden günlüğe kaydedilen bir izlemeyi açıklar.

## <a name="syntax"></a>Syntax

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

| Ad | Açıklama |
|--|--|
| `LogicalProcessorCount` | , İzlemenin toplandığı makinedeki mantıksal işlemcilerin sayısı. |
| `TickFrequency` | Zaman işaretleri cinsinden ölçülen bir süre değerlendirilirken kullanılacak saniye başına düşen saat sayısı. |
| `StartTimestamp` | Bu alan, izleme başlatıldığı sırada yakalanan bir değer değere ayarlanır. |
| `StopTimestamp` | Bu alan, izleme durdurulduğu sırada yakalanan bir değer değere ayarlanır. |

## <a name="remarks"></a>Açıklamalar

`StartTimestamp` `StopTimestamp` Tüm izleme sırasında geçen onay işareti sayısını almak için öğesinden çıkarın. `TickFrequency`Elde edilen değeri bir zaman birimine dönüştürmek için kullanın. Ticks sayısını zaman birimlerine dönüştüren bir örnek için bkz. [EVENT_DATA](event-data-struct.md).

::: moniker-end
