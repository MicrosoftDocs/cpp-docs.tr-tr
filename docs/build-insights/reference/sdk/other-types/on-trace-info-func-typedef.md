---
title: OnTraceInfoFunc typedef
description: C++ Build Insights SDK 'Sı OnTraceInfoFunc typedef başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnTraceInfoFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b168d6783b31454f6a2837bcad1fc81199ce9054
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332350"
---
# <a name="ontraceinfofunc-typedef"></a>OnTraceInfoFunc typedef

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`OnTraceInfoFunc` typedef, [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) ve [RELOG_CALLBACKS](relog-callbacks-struct.md) yapılarında kullanılan işlev imzalarından biridir.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnTraceInfoFunc)(
    const TRACE_INFO_DATA*          traceInfo,
    void*                           callbackContext);
```

### <a name="parameters"></a>Parametreler

*TraceInfo*\
Çözümlenmekte olan veya yeniden günlüğe kaydedilen izleme hakkında bilgi içeren [TRACE_INFO_DATA](../c-event-data-types/trace-info-data-struct.md) nesne.

*CallbackContext*\
[ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) veya [RELOG_DESCRIPTOR](relog-descriptor-struct.md)içinde bu geri çağırma için ayarlanan bağlam değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını denetleyen [CALLBACK_CODE](callback-code-enum.md) değeri.

::: moniker-end
