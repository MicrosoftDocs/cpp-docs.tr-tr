---
title: ANALYSIS_DESCRIPTOR yapısı
description: C++ derleme öngörüleri SDK ANALYSIS_DESCRIPTOR yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ec2d0a76618d6ff2cf0e7fdff7e360a4fd2e0174
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919858"
---
# <a name="analysis_descriptor-structure"></a>ANALYSIS_DESCRIPTOR yapısı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`ANALYSIS_DESCRIPTOR`Yapı, [analiz Zea](../functions/analyze-a.md) ve [analiz ZEW](../functions/analyze-w.md) işlevleriyle birlikte kullanılır. Windows için olay Izleme (ETW) izlemenin nasıl analiz edileceğini açıklar.

## <a name="syntax"></a>Syntax

```cpp
typedef struct ANALYSIS_DESCRIPTOR_TAG
{
    unsigned                NumberOfPasses;
    ANALYSIS_CALLBACKS      Callbacks;
    void*                   Context;
} ANALYSIS_DESCRIPTOR;
```

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `NumberOfPasses` | ETW izlemesi üzerinde yapılması gereken analiz geçişlerinin sayısı. |
| `Callbacks` | Analiz oturumu sırasında hangi işlevlerin çağrılacağını belirten [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) nesnesi. |
| `Context` | İçinde belirtilen tüm geri çağırma işlevlerine bağımsız değişken olarak geçirilen kullanıcı tarafından sağlanmış bir bağlam `Callbacks` |

## <a name="remarks"></a>Açıklamalar

`Callbacks`Yapı yalnızca üye olmayan işlevlere işaretçiler kabul eder. Bir nesne işaretçisine ayarlayarak bu sınırlamayı aşabilirsiniz `Context` . Bu nesne işaretçisi, tüm üye olmayan geri çağırma işlevleriniz için bir bağımsız değişken olarak geçirilir. Üye olmayan geri çağırma işlevlerinizin içinden üye işlevleri çağırmak için bu işaretçiyi kullanın.

::: moniker-end
