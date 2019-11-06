---
title: Derleyici Uyarısı (düzey 1) C4006
ms.date: 11/04/2016
f1_keywords:
- C4006
helpviewer_keywords:
- C4006
ms.assetid: f1a59819-0fd2-4361-8e3a-99e4b514b8e1
ms.openlocfilehash: fc1fd34fe4c9f9c3c72447e5c5c89f3e9ba2f875
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627371"
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