---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4161'
title: Derleyici Uyarısı (düzey 3) C4161
ms.date: 08/27/2018
f1_keywords:
- C4161
helpviewer_keywords:
- C4161
ms.assetid: 03d3be61-83f1-4009-8310-8758ab67055f
ms.openlocfilehash: 6bb96fbee367751533fba769a6c56f01f94df19c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272194"
---
# <a name="compiler-warning-level-3-c4161"></a>Derleyici Uyarısı (düzey 3) C4161

> #<a name="pragma-pragmapop--more-pops-than-pushes"></a>pragma *pragma*(pop...): gönderimden daha fazla pop

## <a name="remarks"></a>Açıklamalar

Kaynak kodunuz pragma *pragma* için gönderimden daha fazla bir pop içerdiğinden, yığın beklendiği gibi davranmayabilir. Uyarıyı önlemek için, pop sayısının gönderim sayısını aşmadığından emin olun.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4161 oluşturur:

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
