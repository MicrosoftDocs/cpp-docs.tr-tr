---
title: FRONT_END_FILE_DATA yapısı
description: C++ derleme öngörüleri SDK FRONT_END_FILE_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FRONT_END_FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 488faf80fc073d5bd41712f66bd263e4043f978e
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923587"
---
# <a name="front_end_file_data-structure"></a>FRONT_END_FILE_DATA yapısı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`FRONT_END_FILE_DATA`Yapı, bir dosyanın derleyicinin ön ucuna göre işlenmesini açıklar.

## <a name="syntax"></a>Syntax

```cpp
typedef struct FRONT_END_FILE_DATA_TAG
{
    const char*         Path;

} FRONT_END_FILE_DATA;
```

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `Path` | Dosyanın mutlak yolu UTF-8 olarak kodlanır. |

::: moniker-end
