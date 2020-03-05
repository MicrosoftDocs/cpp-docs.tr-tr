---
title: ANALYSIS_DESCRIPTOR yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK ANALYSIS_DESCRIPTOR yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: fc11ce11e1faaae02edb36aac447c18ea8107e35
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332483"
---
# <a name="analysis_descriptor-structure"></a>ANALYSIS_DESCRIPTOR yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`ANALYSIS_DESCRIPTOR` yapısı, [analiz Zea](../functions/analyze-a.md) ve [analiz ZEW](../functions/analyze-w.md) işlevleriyle birlikte kullanılır. Windows için olay Izleme (ETW) izlemenin nasıl analiz edileceğini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct ANALYSIS_DESCRIPTOR_TAG
{
    unsigned                NumberOfPasses;
    ANALYSIS_CALLBACKS      Callbacks;
    void*                   Context;
} ANALYSIS_DESCRIPTOR;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `NumberOfPasses` | ETW izlemesi üzerinde yapılması gereken analiz geçişlerinin sayısı. |
| `Callbacks` | Analiz oturumu sırasında hangi işlevlerin çağrılacağını belirten [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) nesnesi. |
| `Context` | `Callbacks` ' de belirtilen tüm geri çağırma işlevlerine bağımsız değişken olarak geçirilen kullanıcı tarafından sağlanmış bağlam |

## <a name="remarks"></a>Açıklamalar

`Callbacks` yapısı yalnızca üye olmayan işlevlere yönelik işaretçileri kabul eder. Bir nesne işaretçisine `Context` ayarlayarak bu sınırlamayı aşabilirsiniz. Bu nesne işaretçisi, tüm üye olmayan geri çağırma işlevleriniz için bir bağımsız değişken olarak geçirilir. Üye olmayan geri çağırma işlevlerinizin içinden üye işlevleri çağırmak için bu işaretçiyi kullanın.

::: moniker-end
