---
title: Derleyici Hatası C2844
ms.date: 11/04/2016
f1_keywords:
- C2844
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
ms.openlocfilehash: 8af9f42be279f728f72fc6968aeba98ee5d2474a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462718"
---
# <a name="compiler-error-c2844"></a>Derleyici Hatası C2844

'member': 'interface' arabiriminin üyesi olamaz

Bir [arabirim sınıfı](../../windows/interface-class-cpp-component-extensions.md) ayrıca bir özellik olmadığı sürece bir veri üyesini içeremez.

Bir özellik veya üye işlev dışındaki herhangi bir arabirimde izin verilmez. Ayrıca, Oluşturucular, Yıkıcılar ve işleçler izin verilmez.

Aşağıdaki örnek, C2844 oluşturur:

```
// C2844a.cpp
// compile with: /clr /c
public interface class IFace {
   int i;   // C2844
   // try the following line instead
   // property int Size;
};
```
