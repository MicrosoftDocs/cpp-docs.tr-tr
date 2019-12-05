---
title: allocator
ms.date: 03/21/2019
f1_keywords:
- allocator_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocator
- allocator __declspec keyword
ms.openlocfilehash: 2e2615829f6491bf660859fbc86ebcd07a56c5fe
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857690"
---
# <a name="allocator"></a>allocator

**Microsoft 'a özgü**

**Ayırıcı** bildirimi Belirleyicisi, ayırmaları Windows Için olay Izleme (ETW) aracılığıyla görünür hale getirmek için özel bellek ayırma işlevlerine uygulanabilir.

## <a name="syntax"></a>Sözdizimi

```
   __declspec(allocator) 
```

## <a name="remarks"></a>Açıklamalar

Visual Studio 'daki yerel bellek profili Oluşturucu, çalışma zamanı sırasında tarafından yayılan ayırma ETW olay verileri toplanarak işe yarar. Böylece ayırma verilerini yakalanabilir ayırıcılar CRT ve Windows SDK'sı kaynak düzeyinde ek açıklama eklenen. Kendi ayırıcılarınızı yazıyorsanız, yeni ayrılan yığın belleğine bir işaretçi döndüren işlevler, myMalloc için bu örnekte görüldüğü gibi `__declspec(allocator)`ile birlikte kullanılabilir.

```cpp
__declspec(allocator) void* myMalloc(size_t size)
```

Daha fazla bilgi için bkz. [Visual Studio 'da bellek kullanımını ölçme](/visualstudio/profiling/memory-usage) ve [özel yerel ETW yığın olayları](/visualstudio/profiling/custom-native-etw-heap-events).

**SON Microsoft 'a özgü**
