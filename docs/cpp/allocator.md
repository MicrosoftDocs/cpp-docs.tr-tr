---
title: allocator
ms.date: 03/21/2019
f1_keywords:
- allocator_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocator
- allocator __declspec keyword
ms.openlocfilehash: a26cf4d2b79d64ddc9f0b60982d778e33d0f200a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216654"
---
# `allocator`

**Microsoft'a Özgü**

**`allocator`** Bildirim Belirleyicisi, ayırmaları Windows Için olay izleme (ETW) aracılığıyla görünür hale getirmek için özel bellek ayırma işlevlerine uygulanabilir.

## <a name="syntax"></a>Sözdizimi

> **`__declspec(allocator)`**

## <a name="remarks"></a>Açıklamalar

Visual Studio 'daki yerel bellek profili Oluşturucu, çalışma zamanı sırasında tarafından yayılan ayırma ETW olay verileri toplanarak işe yarar. CRT ve Windows SDK ayırıcıları, ayırma verilerinin yakalanabilmesi için kaynak düzeyinde açıklanmalıdır. Kendi ayırıcılarınızı yazıyorsanız, yeni ayrılan yığın belleğine bir işaretçi döndüren işlevler `__declspec(allocator)` , myMalloc için bu örnekte görüldüğü gibi ile birlikte kullanılabilir.

```cpp
__declspec(allocator) void* myMalloc(size_t size)
```

Daha fazla bilgi için bkz. [Visual Studio 'da bellek kullanımını ölçme](/visualstudio/profiling/memory-usage) ve [özel yerel ETW yığın olayları](/visualstudio/profiling/custom-native-etw-heap-events).

**SON Microsoft 'a özgü**
