---
title: Derleyici hatası C2844
ms.date: 11/04/2016
f1_keywords:
- C2844
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
ms.openlocfilehash: fdfd2200503f80addb120117ce06f5f837d6b9f2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752021"
---
# <a name="compiler-error-c2844"></a>Derleyici hatası C2844

' Member ': ' Interface ' arabiriminin üyesi olamaz

[Arabirim sınıfı](../../extensions/interface-class-cpp-component-extensions.md) aynı zamanda bir özellik olmadığı takdirde bir veri üyesi içeremez.

Bir arabirimde özellik veya üye işlevi dışında bir şeye izin verilmez. Ayrıca, oluşturucular, Yıkıcılar ve işleçlere izin verilmez.

Aşağıdaki örnek C2844 oluşturur:

```cpp
// C2844a.cpp
// compile with: /clr /c
public interface class IFace {
   int i;   // C2844
   // try the following line instead
   // property int Size;
};
```
