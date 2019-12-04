---
title: Derleyici hatası C2719
ms.date: 11/04/2016
f1_keywords:
- C2719
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
ms.openlocfilehash: 574a04923c20c3104083a6aa05a71838e7ec13d2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760510"
---
# <a name="compiler-error-c2719"></a>Derleyici hatası C2719

' Parameter ': __declspec (align (' # ')) ile biçimsel parametre hizalanmayacak

[Hizalama](../../cpp/align-cpp.md) `__declspec` değiştiricisine işlev parametrelerinde izin verilmez. İşlev parametresi hizalaması kullanılan çağırma kuralına göre denetlenir. Daha fazla bilgi için bkz. [çağırma kuralları](../../cpp/calling-conventions.md).

Aşağıdaki örnek C2719 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2719.cpp
void func(int __declspec(align(32)) i);   // C2719
// try the following line instead
// void func(int i);
```
