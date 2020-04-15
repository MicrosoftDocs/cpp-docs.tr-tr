---
title: Enjektör Olayı
description: C++ Build Insights SDK InjectEvent fonksiyon başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InjectEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c82aad5923eff60e5c72ceccaa39aa136f942665
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324045"
---
# <a name="injectevent"></a>Enjektör Olayı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

`InjectEvent` [İşlev, IRelogger](../other-types/irelogger-class.md) arabirimini uygulayan bir relogger içinde çağrılır. Bir yeniden günleme oturumunun çıktı izleme dosyasına Windows için Olay İzleme (ETW) olayı yazmak için kullanılır.

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
Yeniden günlüğe kaydetme oturumuiçin bir işaretçi. `IRelogger` Arabirimi uygulayan relogger'lara yeniden günlüğe kaydetme oturumu sağlanır. Daha fazla bilgi için [Bkz. IRelogger.](../other-types/irelogger-class.md)

*Providerıd*\
Windows (ETW) sağlayıcısı GUID için Bir Olay İzleme altında ETW olay relogged alır.

*Eventdescriptor*\
Yeniden kaydedilmiş Olan ETW olayı için ETW olay tanımlayıcısı.

*Processıd*\
Yeniden kaydedilmiş ETW olayı için işlem tanımlayıcısı (PID).

*Threadıd*\
Yeniden kaydedilmiş ETW olayı için iş parçacığı tanımlayıcısı (TID).

*processorIndex*\
Yeniden kaydedilmiş ETW olayının işlemci dizini.

*Zaman damgası*\
Yeniden kaydedilmiş ETW olayının zaman damgası.

*Veri*\
Yeniden kaydedilmiş ETW olayına dahil edilmesi gereken verilere işaretçi.

*Bytecount*\
Verilerin boyutu, baytlar halinde, *veriler*tarafından işaret.

## <a name="remarks"></a>Açıklamalar

*Sağlayıcı GUID* ve *olay tanımlayıcısı*gibi ETW kavramları hakkında daha fazla bilgi için [ETW belgelerine](/windows/win32/etw/about-event-tracing)bakın. C++ Build Insights SDK ile yeniden kaydetme oturumu başlatma hakkında ayrıntılı bilgi [için](relog.md)Bkz.

::: moniker-end
