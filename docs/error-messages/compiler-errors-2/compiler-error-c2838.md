---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2838'
title: Derleyici hatası C2838
ms.date: 11/04/2016
f1_keywords:
- C2838
helpviewer_keywords:
- C2838
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
ms.openlocfilehash: 70bc1fa038df33cfe63fccd7dc3db8983950b525
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194403"
---
# <a name="compiler-error-c2838"></a>Derleyici hatası C2838

' üye ': üye bildiriminde geçersiz nitelenmiş ad

Bir sınıf, yapı veya birleşim, başka bir sınıf, yapı veya birleşim üyesini yeniden bildirmek için tam nitelikli bir ad kullanır.

Aşağıdaki örnek C2838 oluşturur:

```cpp
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
