---
title: allocator
ms.date: 03/21/2019
f1_keywords:
- allocator_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocator
- allocator __declspec keyword
ms.openlocfilehash: f9c8de7c8686b89a2ab9570a2558e3f649e545b5
ms.sourcegitcommit: 0064d37467f958dd6a5111f20d7660eaccd53ee9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58417085"
---
# <a name="allocator"></a>allocator

**Microsoft'a özgü**

**Ayırıcı** bildirim belirticisi, ayırmaları aracılığıyla olay izleme için Windows (ETW) görünür yapmak için özel bellek ayırma işlevlere uygulanabilir.

## <a name="syntax"></a>Sözdizimi

```
   __declspec(allocator) 
```

## <a name="remarks"></a>Açıklamalar

Visual Studio'da yerel bellek profili Oluşturucu ayırma sırasında çalışma zamanı tarafından yayılan ETW olay verileri toplayarak çalışır. Böylece ayırma verilerini yakalanabilir ayırıcılar CRT ve Windows SDK'sı kaynak düzeyinde ek açıklama eklenen. Kendi ayırıcılar yazıyorsanız sonra yeni ayrılmış yığın bellek için bir işaretçi döndüren herhangi işlevleri ile donatılmış `__declspec(allocator)`myMalloc için bu örnekte görüldüğü gibi:

```cpp
__declspec(allocator) void* myMalloc(size_t size)
```

Daha fazla bilgi için [Visual Studio'daki bellek kullanımını ölçen](/visualstudio/profiling/memory-usage) ve [özel yerel ETW yığın olayları](/visualstudio/profiling/custom-native-etw-heap-events).