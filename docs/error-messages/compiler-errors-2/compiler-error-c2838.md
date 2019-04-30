---
title: Derleyici Hatası C2838
ms.date: 11/04/2016
f1_keywords:
- C2838
helpviewer_keywords:
- C2838
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
ms.openlocfilehash: 1482efa8b018914a4ebc509464622726ae9ebb20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383015"
---
# <a name="compiler-error-c2838"></a>Derleyici Hatası C2838

'member': üye bildiriminde geçersiz nitelenmiş ad

Bir sınıf, yapı veya birleşim başka bir sınıf, yapı veya birleşim üyesi yeniden bildirmek için tam bir ad kullanır.

Aşağıdaki örnek, C2838 oluşturur:

```
// C2838.cpp
// compile with: /c
class Bellini {
public:
    void Norma();
};

class Bottesini {
   Bellini::Norma();  // C2838
};
```