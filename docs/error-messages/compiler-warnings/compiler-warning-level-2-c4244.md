---
title: Derleyici Uyarısı (Düzey 2) C4244 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4244
dev_langs:
- C++
helpviewer_keywords:
- C4244
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c6dd4b15fe3bda6468f8d5bebcf7cb0926ba69e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084802"
---
# <a name="compiler-warning-level-2-c4244"></a>Derleyici Uyarısı (Düzey 2) C4244

'bağımsız değişkeni': 'type1' öğesinden 'type2', olası veri kaybı dönüştürme

Bir kayan nokta türü bir tamsayı türüne dönüştürüldü.  Olası bir veri kaybı meydana gelebilir.

C4244 alırsanız, uyumlu türler kullanmak için programınızı değiştirmenize veya mantığa olası değerler aralığı her zaman kullanmakta olduğunuz türleri ile uyumlu olmasını sağlamak için kodunuzu ekleyin.

Ayrıca C4244 3 ve 4 düzeyinde özelliği kullanabilirsiniz; bkz: [Derleyici Uyarısı (Düzey 3 ve 4) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4244 oluşturur:

```
// C4244_level2.cpp
// compile with: /W2

int f(int x){ return 0; }
int main() {
   double x = 10.1;
   int i = 10;
   return (f(x));   // C4244
   // try the following line instead
   // return (f(i));
}
```