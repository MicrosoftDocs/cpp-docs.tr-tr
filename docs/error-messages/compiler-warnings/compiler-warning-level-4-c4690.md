---
title: Derleyici Uyarısı (düzey 4) C4690
ms.date: 07/03/2018
f1_keywords:
- C4690
helpviewer_keywords:
- C4690
ms.assetid: 080a0ea1-458b-477b-a37a-4a34c94709ff
ms.openlocfilehash: de996128c68ebf96b4a00f6206cbaf54d97ca275
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509965"
---
# <a name="compiler-warning-level-4-c4690"></a>Derleyici Uyarısı (düzey 4) C4690

> \[ emitidl (pop)]: gönderimden daha fazla pop

## <a name="remarks"></a>Açıklamalar

[Emitidl](../../windows/attributes/emitidl.md) özniteliği gönderildiği bir kez daha vardı.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4690 oluşturur. Bu sorunu giderecek şekilde, özniteliğin tamamen itilmiş kadar çok kez belirlendiğinden emin olun.

```cpp
// C4690.cpp
// compile with: /c /W4
[emitidl(pop)];   // C4690
class x {};
```
