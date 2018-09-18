---
title: Derleyici Hatası C2844 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2844
dev_langs:
- C++
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5dd4cbdc30523563207fe2a66c1c5cb158f84c94
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092109"
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
