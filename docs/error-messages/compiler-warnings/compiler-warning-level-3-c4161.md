---
title: Derleyici Uyarısı (Düzey 3) C4161 | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4161
dev_langs:
- C++
helpviewer_keywords:
- C4161
ms.assetid: 03d3be61-83f1-4009-8310-8758ab67055f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d279822d823ffb8efcaf08ff3f64cd9d82d0a44
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220564"
---
# <a name="compiler-warning-level-3-c4161"></a>Derleyici Uyarısı (Düzey 3) C4161

> #<a name="pragma-pragmapop--more-pops-than-pushes"></a>pragma *pragma*(POP..): atma sayısından fazla

## <a name="remarks"></a>Açıklamalar

Kaynak kodunuzu bir pragma için bildirim daha pop içerdiği için *pragma*, yığın beklediğiniz gibi çalışmayabilir. Uyarıyı önlemek için gönderim sayısı yığından sayısını aşmadığından emin olun.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4161 oluşturur:

```cpp
// C4161.cpp
// compile with: /W3 /LD
#pragma pack(push, id)
#pragma pack(pop, id)
#pragma pack(pop, id)   // C4161, an extra pop

#pragma bss_seg(".my_data1")
int j;

#pragma bss_seg(push, stack1, ".my_data2")
int l;

#pragma bss_seg(pop, stack1)
int m;

#pragma bss_seg(pop, stack1)   // C4161
```