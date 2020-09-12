---
title: FUNCTION_FORCE_INLINEE_DATA yapısı
description: C++ derleme öngörüleri SDK FUNCTION_FORCE_INLINEE_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FUNCTION_FORCE_INLINEE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d64a23c603d1f30726f30ffc91c1889c51138ef6
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041711"
---
# <a name="function_force_inlinee_data-structure"></a>FUNCTION_FORCE_INLINEE_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

`FUNCTION_FORCE_INLINEE_DATA`Yapı, zorla satır içine alınmış bir işlevi tanımlar.

## <a name="syntax"></a>Syntax

```cpp
typedef struct FUNCTION_FORCE_INLINEE_DATA_TAG
{
    const char*         Name;
    unsigned short      Size;

} FUNCTION_FORCE_INLINEE_DATA;
```

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `Name` | İşlevin adı, UTF-8 olarak kodlanır. |
| `Size` | Bir dizi ara yönerge olarak işlevin boyutu. |

::: moniker-end
