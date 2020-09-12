---
title: FUNCTION_DATA yapısı
description: C++ derleme öngörüleri SDK FUNCTION_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FUNCTION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1034ce01bba6422d0c47fc34b308cafcc113e32b
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041750"
---
# <a name="function_data-structure"></a>FUNCTION_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

`FUNCTION_DATA`Yapı bir işlevi tanımlar.

## <a name="syntax"></a>Syntax

```cpp
typedef struct FUNCTION_DATA_TAG
{
    const char*         Name;

} FUNCTION_DATA;
```

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `Name` | İşlevin adı, UTF-8 olarak kodlanır. |

::: moniker-end
