---
title: Derleyici Uyarısı (düzey 1) C4804
ms.date: 11/04/2016
f1_keywords:
- C4804
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
ms.openlocfilehash: aa2cdf0103a1ccc607f2e4a55e1d8f85bb8cc45d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233229"
---
# <a name="compiler-warning-level-1-c4804"></a>Derleyici Uyarısı (düzey 1) C4804

' Operation ': işlemde güvenli olmayan ' bool ' türü kullanımı

Bu uyarı, bir **`bool`** değişken veya değeri beklenmedik bir şekilde kullandığınızda içindir. Örneğin, negatif birli işleç ( **-** ) veya tamamlama işleci () gibi işleçler kullanırsanız C4804 oluşturulur `~` . Derleyici, ifadeyi değerlendirir.

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
