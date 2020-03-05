---
title: Onanalsıseventfunc typedef
description: C++ Build Insights SDK 'sı Onanalsıseventfunc typedef başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnAnalysisEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d260f6060e759f315589abda82e31c2c2b95a65e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332434"
---
# <a name="onanalysiseventfunc-typedef"></a>Onanalsıseventfunc typedef

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`OnAnalysisEventFunc` typedef, [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) yapısında kullanılan işlev imzalarından biridir.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnAnalysisEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    void*                           callbackContext);
```

### <a name="parameters"></a>Parametreler

*Eventstack*\
Geçerli olay için olay yığını. Olay yığınları hakkında daha fazla bilgi için bkz. [Olaylar](../event-table.md).

*CallbackContext*\
[ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) veya [RELOG_DESCRIPTOR](relog-descriptor-struct.md)içinde bu geri çağırma için ayarlanan bağlam değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını denetleyen [CALLBACK_CODE](callback-code-enum.md) değeri.

::: moniker-end
