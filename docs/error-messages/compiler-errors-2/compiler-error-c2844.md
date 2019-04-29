---
title: Derleyici Hatası C2844
ms.date: 11/04/2016
f1_keywords:
- C2844
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
ms.openlocfilehash: 2676a32cee487595a2241359496ae9b0380126b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62329198"
---
# <a name="compiler-error-c2844"></a>Derleyici Hatası C2844

'member': 'interface' arabiriminin üyesi olamaz

Bir [arabirim sınıfı](../../extensions/interface-class-cpp-component-extensions.md) ayrıca bir özellik olmadığı sürece bir veri üyesini içeremez.

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
