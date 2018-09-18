---
title: Derleyici Uyarısı (düzey 4) C4366 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4366
dev_langs:
- C++
helpviewer_keywords:
- C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb24c65605857124edf608bec88f1399d9df607d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047050"
---
# <a name="compiler-warning-level-4-c4366"></a>Derleyici Uyarısı (düzey 4) C4366

Birli 'operator' işlecinin sonucu hizalanmamış olabilir

Bir yapı üyesinin hiç olmadığı kadar paketleme nedeniyle hizalanmamış olabilir, derleyicinin zaman üyenin adresi hizalanmış bir işaretçi atanır uyarır. Varsayılan olarak, tüm işaretçiler hizalanır.

C4366 çözmek için yapıyı hizalamasını değiştirme ya da işaretçiyle bildirmek [__unaligned](../../cpp/unaligned.md) anahtar sözcüğü.

Daha fazla bilgi için bkz: __unaligned ve [paketi](../../preprocessor/pack.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4366 oluşturur.

```
// C4366.cpp
// compile with: /W4 /c
// processor: IPF x64
#pragma pack(1)
struct X {
   short s1;
   int s2;
};

int main() {
   X x;
   short * ps1 = &x.s1;   // OK
   int * ps2 = &x.s2;   // C4366
}
```