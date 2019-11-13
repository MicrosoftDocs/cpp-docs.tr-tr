---
title: Derleyici Uyarısı (düzey 1) C4804
ms.date: 11/04/2016
f1_keywords:
- C4804
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
ms.openlocfilehash: 97ad076325b11329896d98367fb3ac311ec5ded9
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051567"
---
# <a name="compiler-warning-level-1-c4804"></a>Derleyici Uyarısı (düzey 1) C4804

' Operation ': işlemde güvenli olmayan ' bool ' türü kullanımı

Bu uyarı, `bool` değişken veya değeri beklenmedik bir şekilde kullandığınızda içindir. Örneğin, negatif birli işleç ( **-** ) veya tamamlama işleci (`~`) gibi işleçler kullanırsanız, C4804 oluşturulur. Derleyici, ifadeyi değerlendirir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4804 oluşturur:

```cpp
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