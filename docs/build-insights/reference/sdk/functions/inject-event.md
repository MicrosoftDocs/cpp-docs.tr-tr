---
title: InjectEvent
description: C++ Build Insights SDK 'Sı ınjectevent işlev başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InjectEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b4d85f17a6d553d9dffa727824e6d4de94518645
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922841"
---
# <a name="injectevent"></a>InjectEvent

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`InjectEvent`İşlev, [ıregünlükçü](../other-types/irelogger-class.md) arabirimini uygulayan bir yeniden günlükçü içinde çağırılır. Yeniden günlüğe kaydetme oturumunun çıkış izleme dosyasında Windows için olay Izleme (ETW) olayı yazmak için kullanılır.

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

*relogSession*\
Yeniden günlüğe kaydetme oturumunun bir işaretçisi. Yeniden günlüğe kaydetme oturumu, arabirimi uygulayan yeniden Günlükçüler için sağlanır `IRelogger` . Daha fazla bilgi için bkz. [ıregünlükçü](../other-types/irelogger-class.md).

*Kimliği*\
ETW olayının yeniden günlüğe kaydedildiği bir Windows (ETW) sağlayıcısı GUID 'SI için olay Izleme.

*eventDescriptor*\
Yeniden günlüğe kaydedilen ETW olayının ETW olay tanımlayıcısı.

*Işlem*\
Yeniden günlüğe kaydedilen ETW olayının işlem tanımlayıcısı (PID).

*ThreadID*\
Yeniden günlüğe kaydedilen ETW olayının iş parçacığı tanımlayıcısı (TıD).

*Processorındex*\
Yeniden günlüğe kaydedilen ETW olayının işlemci dizini.

*ilişkin*\
Yeniden günlüğe kaydedilen ETW olayının zaman damgası.

*verileri*\
Yeniden günlüğe kaydedilen ETW olayına dahil edilecek verilerin bir işaretçisi.

*byteCount*\
Verilerin bayt cinsinden *verileri* tarafından işaret edilen boyutu.

## <a name="remarks"></a>Açıklamalar

*Sağlayıcı GUID 'si* ve *olay tanımlayıcısı* gibi ETW kavramları hakkında daha fazla bilgi için bkz. [ETW belgeleri](/windows/win32/etw/about-event-tracing). C++ Build Insights SDK 'Sı ile yeniden günlüğe kaydetme oturumunun nasıl başlatılacağı hakkında ayrıntılı bilgi için bkz. [relog](relog.md).

::: moniker-end
