---
title: Derleyici Uyarısı (düzey 1) C4920
ms.date: 11/04/2016
f1_keywords:
- C4920
helpviewer_keywords:
- C4920
ms.assetid: 1e501f2e-93c1-4d27-a4fa-54fc86271ae7
ms.openlocfilehash: cd501cf0e3b434523623276027056c93c77fc278
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580701"
---
# <a name="compiler-warning-level-1-c4920"></a>Derleyici Uyarısı (düzey 1) C4920

Enum sabit listesi üyesi üyesi numaralandırma sabit listesi üyesi olarak zaten görüldü value = value =

#İmport için geçirdiğiniz bir .tlb iki veya daha fazla sabit listelerinde tanımlanan aynı sembolü varsa, bu uyarı, sonraki aynı sembolleri göz ardı edilir ve .tlh dosyasına yorum gösterir.

İçeren bir .tlb varsayılarak:

```
library MyLib
{
    typedef enum {
        enumMember = 512
    } AProblem;

    typedef enum {
        enumMember = 1024
    } BProblem;
};
```

Aşağıdaki örnekler C4920 oluşturur,

```
// C4920.cpp
// compile with: /W1
#import "t4920.tlb"   // C4920

int main() {
}
```