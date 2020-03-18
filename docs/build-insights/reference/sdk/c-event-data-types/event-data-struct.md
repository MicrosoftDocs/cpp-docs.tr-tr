---
title: EVENT_DATA yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK EVENT_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 572cbdaba346ddb77b665b5677b978c83a80aa3d
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417448"
---
# <a name="event_data-structure"></a>EVENT_DATA yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`EVENT_DATA` yapısı, bir analiz veya yeniden günlüğe kaydetme oturumundan alınan bir olayı açıklar. Bu oturumlar, [Çözümle](../functions/analyze.md), analiz [Zea](../functions/analyze-a.md), analiz [ZEW](../functions/analyze-w.md), [relog](../functions/relog.md), [reloga](../functions/relog-a.md)veya [relogw](../functions/relog-w.md) işlevleri çağırarak başlatılır.

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
| `EventId` | Olayı tanımlayan bir sayı. Olay tanımlayıcılarının listesi için bkz. [EVENT_ID](event-id-enum.md). |
| `EventInstanceId` | Bir izleme içinde geçerli olayı benzersiz bir şekilde tanımlayan bir sayı. Bu değer, aynı izlemeyi birden çok kez analiz veya yeniden günlüğe kaydetme sırasında değişmez. Aynı olayı birden çok çözümlemede veya yeniden günlüğe kaydetmenin aynı izleme üzerinden tanımlamak için bu alanı kullanın. |
| `TickFrequency` | Zaman işaretleri cinsinden ölçülen bir süre değerlendirilirken kullanılacak saniye başına düşen saat sayısı. |
| `StartTimestamp` | Olay bir *etkinlik*olduğunda, bu alan etkinlik başlatıldığı sırada yakalanan bir değer değere ayarlanır. Bu olay *basit bir olaysa*, bu alan olay gerçekleştiği sırada yakalanan bir değer değere ayarlanır. |
| `StopTimestamp` | Olay bir *etkinlik*olduğunda, bu alan etkinlik durdurulduğu sırada yakalanan bir değer değere ayarlanır. Bu etkinlik için durdurma olayı henüz alınmadıysa, bu alan sıfır olarak ayarlanır. Bu olay *basit bir olaydır*, bu alan sıfır olarak ayarlanır. |
| `ExclusiveDurationTicks` | Bu olay bir *etkinlikise*, bu alan doğrudan bu etkinlikte gerçekleşen onay işareti sayısına ayarlanır. Alt etkinlikte gerçekleşen onay işareti sayısı hariç tutulur. Bu alan, *basit olaylar*için sıfır olarak ayarlanır. |
| `CPUTicks` | Bu olay bir *etkinlik*ise, bu alan bu etkinlik SıRASıNDA oluşan CPU onay işareti sayısına ayarlanır. Bir CPU çentik, düzenli bir Tick 'ten farklıdır. CPU işaretleri yalnızca CPU bir etkinlikte kod yürütürken sayılır. Etkinlikle ilişkili iş parçacığı uyurken CPU işaretleri sayılmaz. Bu alan, *basit olaylar*için sıfır olarak ayarlanır. |
| `ExclusiveCPUTicks` | Bu alan, `CPUTicks`ile aynı anlama sahiptir, ancak alt etkinliklerde oluşan CPU işaretlerini içermez. Bu alan, *basit olaylar*için sıfır olarak ayarlanır. |
| `WallClockTimeResponsibilityTicks` | Bu olay bir *etkinlikise*, bu alan, bu etkinliğin genel duvar saati saatine katkısı temsil eden bir değer sayısı olarak ayarlanır. Bir duvar saati zaman sorumluluğu çentik, düzenli bir Tick 'ten farklıdır. Duvar saati zaman sorumluluk işaretleri, etkinlikler arasında paralellik hesaba sahiptir. Örneğin, iki paralel Etkinliğin süresi 50 saat ve aynı başlangıç ve bitiş zamanı olabilir. Bu durumda, her ikisine de 25 saat için bir duvar saati zaman sorumluluğu atanır. Bu alan, *basit olaylar*için sıfır olarak ayarlanır. |
| `ExclusiveWallClockTimeResponsibilityTicks` | Bu alan, `WallClockTimeResponsibilityTicks`ile aynı anlama sahiptir, ancak alt etkinliklerin duvar saati zaman sorumluluğu işaretlerini içermez. Bu alan, *basit olaylar*için sıfır olarak ayarlanır. |
| `Data` | Olayda depolanan ek verilere işaret eder. İşaret edilen veri türü, `EventId` alanına bağlı olarak farklılık gösterdiği şekilde değişir. |
| `ProcessId` | Olayın gerçekleştiği işlemin tanımlayıcısı. |
| `ThreadId` | Olayın gerçekleştiği iş parçacığının tanımlayıcısı. |
| `ProcessorIndex` | Olayın gerçekleştiği sıfır dizinli CPU numarası. |
| `EventName` | `EventId`tarafından tanımlanan varlığın adını içeren bir ANSI dizesi. |
| `EventWideName` | `EventId`tarafından tanımlanan varlığın adını içeren geniş bir dize. |

## <a name="remarks"></a>Açıklamalar

`EVENT_DATA` çok sayıda alan, değer sayılarını içerir. C++Yapı öngörüleri, pencerenin onay işareti kaynağı olarak performans sayacını kullanır. Değer sayısı, saniye gibi uygun bir zaman birimine dönüştürmek için `TickFrequency` alanla birlikte kullanılmalıdır. Bu dönüştürmeyi gerçekleştirmek için aşağıdaki örneğe bakın. `EVENT_DATA` etkinliğin normal değer sayısı için bir alan içermez. Bu değeri almak için `StopTimestamp``StartTimestamp` çıkarın. `EVENT_DATA`, C API kullanıcıları tarafından kullanılması amaçlanan bir yapıdır. API C++ kullanıcıları Için, [olay](../cpp-event-data-types/event.md) gibi sınıflar, zaman dönüştürmeleri otomatik olarak yapılır.

`EVENT_DATA` `Data` alanının değeri `EventId` alanının değerine bağlıdır. `Data` değeri aşağıdaki tabloda açıklanmıştır. Aşağıdaki tabloda bazı varlık tanımlayıcıları eksik olabilir. Bu durumda `Data` alanı `nullptr` veya sıfır olarak ayarlanır.

| `EventId` değeri | `Data` göre işaret eden tür |
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

## <a name="tick-conversion-example"></a>Değer dönüştürme örneği

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
