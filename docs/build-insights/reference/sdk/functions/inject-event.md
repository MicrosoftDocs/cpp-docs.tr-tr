---
title: Injectevent
description: C++ Build Insights SDK 'Sı ınjectevent işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InjectEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7b53eb71cf7a2ae40d04dbc3f8b5829f2737aba4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332847"
---
# <a name="injectevent"></a>Injectevent

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`InjectEvent` işlevi, [ıregünlükçü](../other-types/irelogger-class.md) arabirimini uygulayan bir yeniden günlükçü içinde çağırılır. Yeniden günlüğe kaydetme oturumunun çıkış izleme dosyasında Windows için olay Izleme (ETW) olayı yazmak için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
void InjectEvent(
    const void* relogSession,
    LPCGUID providerId,
    PCEVENT_DESCRIPTOR eventDescriptor,
    unsigned long processId,
    unsigned long threadId,
    unsigned short processorIndex,
    long long timestamp,
    unsigned char* data,
    unsigned long byteCount);
```

### <a name="parameters"></a>Parametreler

*Relogsession*\
Yeniden günlüğe kaydetme oturumunun bir işaretçisi. `IRelogger` arabirimini uygulayan yeniden Günlükçüler için yeniden günlüğe kaydetme oturumu sağlanır. Daha fazla bilgi için bkz. [ıregünlükçü](../other-types/irelogger-class.md).

*ProviderID*\
ETW olayının yeniden günlüğe kaydedildiği bir Windows (ETW) sağlayıcısı GUID 'SI için olay Izleme.

*EventDescriptor*\
Yeniden günlüğe kaydedilen ETW olayının ETW olay tanımlayıcısı.

*işlemkimliği*\
Yeniden günlüğe kaydedilen ETW olayının işlem tanımlayıcısı (PID).

*ThreadID*\
Yeniden günlüğe kaydedilen ETW olayının iş parçacığı tanımlayıcısı (TıD).

*Processorındex*\
Yeniden günlüğe kaydedilen ETW olayının işlemci dizini.

*zaman damgası*\
Yeniden günlüğe kaydedilen ETW olayının zaman damgası.

*veri*\
Yeniden günlüğe kaydedilen ETW olayına dahil edilecek verilerin bir işaretçisi.

*ByteCount*\
Verilerin bayt cinsinden *verileri*tarafından işaret edilen boyutu.

## <a name="remarks"></a>Açıklamalar

*Sağlayıcı GUID 'si* ve *olay tanımlayıcısı*gibi ETW kavramları hakkında daha fazla bilgi için bkz. [ETW belgeleri](/windows/win32/etw/about-event-tracing). C++ Build Insights SDK 'sı ile yeniden günlüğe kaydetme oturumunun nasıl başlatılacağı hakkında ayrıntılı bilgi için bkz. [relog](relog.md).

::: moniker-end
