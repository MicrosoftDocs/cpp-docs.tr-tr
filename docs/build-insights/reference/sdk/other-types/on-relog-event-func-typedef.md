---
title: OnRelogEventFunc typedef
description: C++ Build Insights SDK 'sı OnRelogEventFunc typedef başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnRelogEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 619f9a142ad19a7809b867eda93f2db634825a8f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332392"
---
# <a name="onrelogeventfunc-typedef"></a>OnRelogEventFunc typedef

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`OnRelogEventFunc` typedef, [RELOG_CALLBACKS](relog-callbacks-struct.md) yapısında kullanılan işlev imzalarından biridir.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnRelogEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    const void*                     relogSession,
    void*                           callbackContext);
```

### <a name="parameters"></a>Parametreler

*Eventstack*\
Geçerli olay için olay yığını. Olay yığınları hakkında daha fazla bilgi için bkz. [Olaylar](../event-table.md).

*Relogsession*\
[Injectevent](../functions/inject-event.md)çağrılırken kullanılacak yeniden günlüğe kaydetme oturum işaretçisi.

*CallbackContext*\
[RELOG_DESCRIPTOR](analysis-descriptor-struct.md)içinde bu geri çağırma için ayarlanan bağlam değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını denetleyen [CALLBACK_CODE](callback-code-enum.md) değeri.

::: moniker-end
