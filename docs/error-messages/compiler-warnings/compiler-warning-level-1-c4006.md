---
title: Derleyici Uyarısı (düzey 1) C4006
ms.date: 11/04/2016
f1_keywords:
- C4006
helpviewer_keywords:
- C4006
ms.assetid: f1a59819-0fd2-4361-8e3a-99e4b514b8e1
ms.openlocfilehash: b589a4bd6b9e14ec926f634f12883e02bf450514
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164722"
---
# <a name="compiler-warning-level-1-c4006"></a>Derleyici Uyarısı (düzey 1) C4006

\#undef bir tanımlayıcı bekliyordu

`#undef` yönergesi, tanımlanmayan bir tanımlayıcı belirtmedi. Yönerge yoksayıldı. Uyarıyı çözmek için bir tanımlayıcı belirttiğinizden emin olun. Aşağıdaki örnek C4006 oluşturur:

```cpp
// C4006.cpp
// compile with: /W1
#undef   // C4006

// try..
// #undef TEST

int main() {
}
```
