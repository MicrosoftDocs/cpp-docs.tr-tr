---
title: OnBeginEndPassFunc typedef
description: C++ Build Insights SDK 'Sı OnBeginEndPassFunc typedef başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnBeginEndPassFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2008dfb86d6f45a1c05a59e1f0f4f8c7868dcda2
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041984"
---
# <a name="onbeginendpassfunc-typedef"></a>OnBeginEndPassFunc typedef

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

`OnBeginEndPassFunc`Typedef, [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) ve [RELOG_CALLBACKS](relog-callbacks-struct.md) yapılarında kullanılan işlev imzalarından biridir.

## <a name="syntax"></a>Syntax

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnBeginEndPassFunc)(
    void*                           callbackContext);
```

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `callbackContext` |  |

::: moniker-end
