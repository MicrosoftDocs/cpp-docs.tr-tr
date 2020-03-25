---
title: Derleyici Uyarısı (düzey 1) C4920
ms.date: 11/04/2016
f1_keywords:
- C4920
helpviewer_keywords:
- C4920
ms.assetid: 1e501f2e-93c1-4d27-a4fa-54fc86271ae7
ms.openlocfilehash: b587a4ca2a78bc2ac54640adb2b149d97bef4def
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174667"
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
