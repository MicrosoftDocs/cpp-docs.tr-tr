---
title: OnTraceInfoFunc typedef
description: C++ Build Insights SDK OnTraceInfoFunc typedef referans.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnTraceInfoFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b987d4db9852c2e52c148bb91015ad414c04d41b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329014"
---
# <a name="ontraceinfofunc-typedef"></a>OnTraceInfoFunc typedef

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

`OnTraceInfoFunc` [Typedef, ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) ve [RELOG_CALLBACKS](relog-callbacks-struct.md) yapılarında kullanılan işlev imzalarından biridir.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnTraceInfoFunc)(
    const TRACE_INFO_DATA*          traceInfo,
    void*                           callbackContext);
```

### <a name="parameters"></a>Parametreler

*Traceınfo*\
Şu anda çözümlenen veya yeniden günlüğe kaydedilen izleme hakkında bilgi içeren [TRACE_INFO_DATA](../c-event-data-types/trace-info-data-struct.md) bir nesne.

*geri aramaBağlam*\
[bu](analysis-descriptor-struct.md) geri arama için ANALYSIS_DESCRIPTOR veya [RELOG_DESCRIPTOR](relog-descriptor-struct.md)olarak ayarlanan bağlam değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki adımı kontrol eden [CALLBACK_CODE](callback-code-enum.md) bir değer.

::: moniker-end
