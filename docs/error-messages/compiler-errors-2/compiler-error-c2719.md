---
title: Derleyici hatası C2719
ms.date: 11/04/2016
f1_keywords:
- C2719
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
ms.openlocfilehash: a0a993069a0bd232154cf6c1b365c0828d9bede8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220255"
---
# <a name="compiler-error-c2719"></a>Derleyici hatası C2719

' Parameter ': __declspec (align (' # ')) ile biçimsel parametre hizalanmayacak

[align](../../cpp/align-cpp.md) **`__declspec`** İşlev parametrelerinde hizalama değiştiricisine izin verilmez. İşlev parametresi hizalaması kullanılan çağırma kuralına göre denetlenir. Daha fazla bilgi için bkz. [çağırma kuralları](../../cpp/calling-conventions.md).

Aşağıdaki örnek C2719 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2719.cpp
void func(int __declspec(align(32)) i);   // C2719
// try the following line instead
// void func(int i);
```
