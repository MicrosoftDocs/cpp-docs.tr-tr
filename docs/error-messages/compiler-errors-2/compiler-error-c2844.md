---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2844'
title: Derleyici hatası C2844
ms.date: 11/04/2016
f1_keywords:
- C2844
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
ms.openlocfilehash: 030d8526e7bfd85e7bcca1c115f1b5ce5d45c3aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260286"
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
