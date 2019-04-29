---
title: Derleyici Hatası C2791
ms.date: 11/04/2016
f1_keywords:
- C2791
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
ms.openlocfilehash: 66a111ea6fe2ca5acfbc473d19da62d9de67372a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360170"
---
# <a name="compiler-error-c2791"></a>Derleyici Hatası C2791

Geçersiz 'super' kullanımı: 'class', herhangi bir taban sınıfa sahip değil

Anahtar sözcüğü [Süper](../../cpp/super.md) herhangi bir taban sınıfa sahip olmayan bir sınıf üye işlevinin bağlamında kullanıldı.

Aşağıdaki örnek, C2791 oluşturur:

```
// C2791.cpp
struct D {
   void mf() {
      __super::mf();   // C2791
   }
};
```