---
title: Derleyici Uyarısı (düzey 1) C4003
ms.date: 11/04/2016
f1_keywords:
- C4003
helpviewer_keywords:
- C4003
ms.assetid: 0ed1c285-4428-4c90-8131-86897e31f115
ms.openlocfilehash: 3bf1eea1b8ad0529d6603a2388e61b9107304f43
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164748"
---
# <a name="compiler-warning-level-1-c4003"></a>Derleyici Uyarısı (düzey 1) C4003

' tanımlayıcı ' makrosu için yeterli gerçek parametre yok

Makro tanımındaki biçimsel parametrelerin sayısı, makrodaki gerçek parametrelerin sayısını aşıyor. Makro genişletmesi, eksik parametrelerin boş metnini değiştirir.

Aşağıdaki örnek C4003 oluşturur:

```cpp
// C4003.cpp
// compile with: /WX
#define test(a,b) (a+b)

int main()
{
   int a = 1;
   int b = 2;
   a = test(b);   // C4003
   // try..
   a = test(a,b);
}
```
