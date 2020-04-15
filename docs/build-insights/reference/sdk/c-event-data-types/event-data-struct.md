---
title: EVENT_DATA yapısı
description: C++ Yapı Öngörüleri SDK EVENT_DATA yapı referansı.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 8ce396febe278c5e7c34fe170939c9522913f92a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325607"
---
# <a name="event_data-structure"></a>EVENT_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı, `EVENT_DATA` bir analizden veya yeniden günlüğe kaydetme oturumundan alınan bir olayı açıklar. Bu oturumlar [Analyze,](../functions/analyze.md) [AnalyzeA,](../functions/analyze-a.md) [AnalyzeW,](../functions/analyze-w.md) [RelogA, RelogA](../functions/relog-a.md)veya [RelogW](../functions/relog-w.md) işlevlerini arayarak başlatılır. [Relog](../functions/relog.md)

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct EVENT_DATA_TAG
{
    unsigned short          EventId;
    unsigned long long      EventInstanceId;

    long long               TickFrequency;
    long long               StartTimestamp;
    long long               StopTimestamp;
    long long               ExclusiveDurationTicks;
    long long               CPUTicks;
    long long               ExclusiveCPUTicks;
    long long               WallClockTimeResponsibilityTicks;
    long long               ExclusiveWallClockTimeResponsibilityTicks;

    const void*             Data;

    unsigned long           ProcessId;
    unsigned long           ThreadId;
    unsigned short          ProcessorIndex;

    const char*             EventName;
    const wchar_t*          EventWideName;

} EVENT_DATA;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `EventId` | Olayı tanımlayan bir sayı. Olay tanımlayıcılarının listesi için [bkz. EVENT_ID.](event-id-enum.md) |
| `EventInstanceId` | İziçindeki geçerli olayı benzersiz olarak tanımlayan bir sayı. Aynı izlemeyi birden çok kez analiz ederken veya yeniden günlüğe kaydederken bu değer değişmez. Aynı olayı birden çok çözümlemede veya aynı izleme üzerinde yeniden günlüğe kaydetme geçişlerinde tanımlamak için bu alanı kullanın. |
| `TickFrequency` | Kenecinsinden ölçülen bir süreyi değerlendirirken kullanılacak saniye başına keneler sayısı. |
| `StartTimestamp` | Olay bir *Etkinlik*olduğunda, bu alan, etkinliğin başlatıldıkı anda yakalanan bir kene değerine ayarlanır. Bu olay *basit*bir olaysa, bu alan olayın oluştuğu anda yakalanan bir kene değerine ayarlanır. |
| `StopTimestamp` | Olay bir *Etkinlik*olduğunda, bu alan, etkinlik durdurulduğu anda yakalanan bir kene değerine ayarlanır. Bu etkinlik için durdurma olayı henüz alınmadıysa, bu alan sıfıra ayarlanır. Bu olay *basit*bir olaysa, bu alan sıfıra ayarlanır. |
| `ExclusiveDurationTicks` | Bu olay bir *Activity*Etkinlikse, bu alan doğrudan bu etkinlikte gerçekleşen onay sayısına ayarlanır. Bir alt etkinlikte oluşan kene sayısı hariç tutulur. Bu alan *Basit Olaylar*için sıfıra ayarlanır. |
| `CPUTicks` | Bu olay bir *Activity*Etkinlikse, bu alan bu etkinlik sırasında oluşan CPU onay sayısına ayarlanır. CPU işareti normal bir keneden farklıdır. CPU tikleri yalnızca CPU bir etkinlikte kod yürütüldüğünde sayılır. Etkinlikle ilişkili iş parçacığı uyku dayadığında CPU tikleri sayılmaz. Bu alan *Basit Olaylar*için sıfıra ayarlanır. |
| `ExclusiveCPUTicks` | Bu `CPUTicks`alan, çocuk etkinliklerinde gerçekleşen CPU işaretlerini içermemesi dışında, aynı anlama gelir. Bu alan *Basit Olaylar*için sıfıra ayarlanır. |
| `WallClockTimeResponsibilityTicks` | Bu olay bir *Activity*Etkinlikse, bu alan, bu etkinliğin genel duvar saati zamanına katkısını temsil eden bir kene sayısına ayarlanır. Bir duvar saati zaman sorumluluk kene normal bir kene farklıdır. Duvar saati zaman sorumluluğu, etkinlikler arasındaki paralelliği dikkate alır. Örneğin, iki paralel etkinlik 50 kene süresine ve aynı başlangıç ve durdurma süresine sahip olabilir. Bu durumda, her ikisi de 25 kene bir duvar saati zaman sorumluluğu atanır. Bu alan *Basit Olaylar*için sıfıra ayarlanır. |
| `ExclusiveWallClockTimeResponsibilityTicks` | Bu alan, çocuk `WallClockTimeResponsibilityTicks`etkinliklerinin duvar saati sorumluluk işaretlerini içermemesi dışında, aynı anlama gelir. Bu alan *Basit Olaylar*için sıfıra ayarlanır. |
| `Data` | Etkinlikte depolanan ek verilere işaret ediyor. Öne çıkan veri türü, `EventId` alana bağlı olarak farklıdır. |
| `ProcessId` | Olayın oluştuğu işlemin tanımlayıcısı. |
| `ThreadId` | Olayın oluştuğu iş parçacığı için tanımlayıcı. |
| `ProcessorIndex` | Olayın oluştuğu sıfır dizinli CPU numarası. |
| `EventName` | `EventId`Tarafından tanımlanan varlığın adını içeren bir ANSI dizesi. |
| `EventWideName` | `EventId`' ile tanımlanan varlığın adını içeren geniş bir dize |

## <a name="remarks"></a>Açıklamalar

Birçok alanda `EVENT_DATA` kene sayıları içerir. C++ Build Insights, pencerenin performans sayacını kene kaynağı olarak kullanır. Bir kene sayısı saniye `TickFrequency` gibi uygun bir zaman birimine dönüştürmek için alan ile kullanılmalıdır. Bu dönüşümü gerçekleştirmek için aşağıdaki örneğe bakın. `EVENT_DATA`bir etkinliğin normal onay sayısı için bir alan içermez. Bu değeri elde etmek `StartTimestamp` `StopTimestamp`için, 'den çıkarma `EVENT_DATA`C API kullanıcıları tarafından kullanılmak üzere bir yapıdır. C++ API kullanıcıları için [Olay](../cpp-event-data-types/event.md) gibi sınıflar otomatik olarak zaman dönüştürmeleri yapar.

Alanın değeri `EVENT_DATA` alanının `EventId` değerine bağlıdır. `Data` Değeri `Data` aşağıdaki tabloda açıklanmıştır. Bazı varlık tanımlayıcıları aşağıdaki tablodan eksik olabilir. Bu durumda, `Data` alan veya `nullptr` sıfır olarak ayarlanır.

| `EventId`Değer | Tarafından işaret edilen tür`Data` |
|--|--|
| `EVENT_ID_BACK_END_PASS` | [CL_PASS_DATA](cl-pass-data-struct.md) |
| `EVENT_ID_COMMAND_LINE` | `const wchar_t` |
| `EVENT_ID_COMPILER` | [INVOCATION_DATA](invocation-data-struct.md) |
| `EVENT_ID_ENVIRONMENT_VARIABLE` | [NAME_VALUE_PAIR_DATA](name-value-pair-data-struct.md) |
| `EVENT_ID_EXECUTABLE_IMAGE_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_EXP_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_FILE_INPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_FORCE_INLINE` | [FUNCTION_FORCE_INLINEE_DATA](function-force-inlinee-data-struct.md) |
| `EVENT_ID_FRONT_END_FILE` | [FRONT_END_FILE_DATA](front-end-file-data-struct.md) |
| `EVENT_ID_FRONT_END_PASS` | [CL_PASS_DATA](cl-pass-data-struct.md) |
| `EVENT_ID_FUNCTION` | [FUNCTION_DATA](function-data-struct.md) |
| `EVENT_ID_IMP_LIB_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_LIB_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_LINKER` | [INVOCATION_DATA](invocation-data-struct.md) |
| `EVENT_ID_OBJ_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_SYMBOL_NAME` | [SYMBOL_NAME_DATA](symbol-name-data-struct.md) |
| `EVENT_ID_TEMPLATE_INSTANTIATION` | [TEMPLATE_INSTANTIATION_DATA](template-instantiation-data-struct.md) |

## <a name="tick-conversion-example"></a>Onay dönüşüm örneği

```cpp
//
// We have the elapsed number of ticks, along with the
// number of ticks per second. We use these values
// to convert to the number of elapsed microseconds.
// To guard against loss-of-precision, we convert
// to microseconds *before* dividing by ticks-per-second.
//

long long ConvertDurationToMicroseconds(const sruct EVENT_DATA& eventData)
{
    long long duration = eventData.StopTimestamp - eventData.StartTimestamp;
    long long duration *= 1000000;
    return duration / eventData.TickFrequency;
}
```

::: moniker-end
