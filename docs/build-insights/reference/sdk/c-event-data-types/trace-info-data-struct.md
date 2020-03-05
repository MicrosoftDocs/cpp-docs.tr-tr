---
title: TRACE_INFO_DATA yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK TRACE_INFO_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACE_INFO_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 04cb5c013bca8879507983d169b38e5af0f1322b
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333589"
---
# <a name="trace_info_data-structure"></a>TRACE_INFO_DATA yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`TRACE_INFO_DATA` yapısı, çözümlenmekte olan veya yeniden günlüğe kaydedilen bir izlemeyi tanımlar.

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
| `LogicalProcessorCount` | , İzlemenin toplandığı makinedeki mantıksal işlemcilerin sayısı. |
| `TickFrequency` | Zaman işaretleri cinsinden ölçülen bir süre değerlendirilirken kullanılacak saniye başına düşen saat sayısı. |
| `StartTimestamp` | Bu alan, izleme başlatıldığı sırada yakalanan bir değer değere ayarlanır. |
| `StopTimestamp` | Bu alan, izleme durdurulduğu sırada yakalanan bir değer değere ayarlanır. |

## <a name="remarks"></a>Açıklamalar

Tüm izleme sırasında geçen onay işareti sayısını almak için `StopTimestamp` `StartTimestamp` çıkarın. Elde edilen değeri bir zaman birimine dönüştürmek için `TickFrequency` kullanın. Ticks sayısını zaman birimlerine dönüştüren bir örnek için bkz. [EVENT_DATA](event-data-struct.md).

::: moniker-end
