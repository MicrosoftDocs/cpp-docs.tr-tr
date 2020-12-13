---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3909'
title: Derleyici hatası C3909
ms.date: 11/04/2016
f1_keywords:
- C3909
helpviewer_keywords:
- C3909
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
ms.openlocfilehash: a85e0201e192caae1e4f170a12544177cbb2d7f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144163"
---
# <a name="compiler-error-c3909"></a>Derleyici hatası C3909

Awınrt veya yönetilen olay bildirimi bir WinRT veya yönetilen türde gerçekleşmelidir

Bir Windows Çalışma Zamanı olayı veya yönetilen olay yerel bir tür içinde bildirildi. Bu hatayı onarmak için Windows Çalışma Zamanı türlerinde veya yönetilen türlerde olayları bildirin.

Daha fazla bilgi için bkz. [olay](../../extensions/event-cpp-component-extensions.md).

Aşağıdaki örnek C3909 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3909.cpp
// compile with: /clr /c
delegate void H();
class X {
   event H^ E;   // C3909 - use ref class X instead
};

ref class Y {
   static event H^ E {
      void add(H^) {}
      void remove( H^ h ) {}
      void raise( ) {}
   }
};
```
