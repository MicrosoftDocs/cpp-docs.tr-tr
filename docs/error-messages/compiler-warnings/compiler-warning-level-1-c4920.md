---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4920'
title: Derleyici Uyarısı (düzey 1) C4920
ms.date: 11/04/2016
f1_keywords:
- C4920
helpviewer_keywords:
- C4920
ms.assetid: 1e501f2e-93c1-4d27-a4fa-54fc86271ae7
ms.openlocfilehash: d9b0daab6ec08a39c928984fcbed720657a24de8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301964"
---
# <a name="compiler-warning-level-1-c4920"></a>Derleyici Uyarısı (düzey 1) C4920

Enum enum member member = değeri Member = Value olarak Enum numaralandırmasında zaten görüldü

#İmport geçirdiğiniz bir. tlb iki veya daha fazla numaralandırmalarda tanımlanmış aynı simgeye sahipse, bu uyarı izleyen aynı sembollerin yoksayıldığını ve. tlh dosyasında açıklama alınmayacağını gösterir.

Şunu içeren bir. tlb varsayılıyor:

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

Aşağıdaki örnekler C4920 oluşturur.

```cpp
// C4920.cpp
// compile with: /W1
#import "t4920.tlb"   // C4920

int main() {
}
```
