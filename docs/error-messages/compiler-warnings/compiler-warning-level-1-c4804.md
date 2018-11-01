---
title: Derleyici Uyarısı (düzey 1) C4804
ms.date: 11/04/2016
f1_keywords:
- C4804
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
ms.openlocfilehash: 28b3e49717993a3bf20c8cfec5938d698266c0f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476082"
---
# <a name="compiler-warning-level-1-c4804"></a>Derleyici Uyarısı (düzey 1) C4804

'operation': işlemde ' bool' türü güvensiz kullanımı

Bu uyarı için kullanıldığında bir `bool` değişkeni veya beklenmedik bir şekilde değer. Negatif birli işleç gibi işleçler kullanın, örneğin, C4804 oluşturulur (**-**) veya Tamamlayıcı işleci (`~`). Derleyici, ifadeyi değerlendirir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4804 oluşturur:

```
// C4804.cpp
// compile with: /W1

int main()
{
   bool i = true;
   if (-i)   // C4804, remove the '-' to resolve
   {
      i = false;
   }
}
```