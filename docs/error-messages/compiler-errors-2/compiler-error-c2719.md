---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2719'
title: Derleyici hatası C2719
ms.date: 11/04/2016
f1_keywords:
- C2719
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
ms.openlocfilehash: 61e01107d5681c4bab39b06b00293ecdbeb9fc9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320728"
---
# <a name="compiler-error-c2719"></a>Derleyici hatası C2719

' Parameter ': __declspec (align (' # ')) ile biçimsel parametre hizalanmayacak

[](../../cpp/align-cpp.md) **`__declspec`** İşlev parametrelerinde hizalama değiştiricisine izin verilmez. İşlev parametresi hizalaması kullanılan çağırma kuralına göre denetlenir. Daha fazla bilgi için bkz. [çağırma kuralları](../../cpp/calling-conventions.md).

Aşağıdaki örnek C2719 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2719.cpp
void func(int __declspec(align(32)) i);   // C2719
// try the following line instead
// void func(int i);
```
