---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3640'
title: Derleyici hatası C3640
ms.date: 11/04/2016
f1_keywords:
- C3640
helpviewer_keywords:
- C3640
ms.assetid: fcc56894-0f98-48af-8561-3bf7c7b2b93f
ms.openlocfilehash: 7f26a824cc39f2b5509c6d935a95cbc5af48aca0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239187"
---
# <a name="compiler-error-c3640"></a>Derleyici hatası C3640

' üye ': yerel bir sınıfın başvurulan veya sanal üye işlevinin tanımlanması gerekir

Derleyici belirli işlevlerin tanımlanmasını gerektirir.

Aşağıdaki örnek C3640 oluşturur:

```cpp
// C3640.cpp
void f()
{
   struct S
   {
      virtual void f1();   // C3640
      // Try the following line instead:
      // virtual void f1(){}
   };
}
```
