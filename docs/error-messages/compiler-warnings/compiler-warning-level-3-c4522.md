---
title: Derleyici Uyarısı (Düzey 3) C4522 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4522
dev_langs:
- C++
helpviewer_keywords:
- C4522
ms.assetid: 7065dc27-0b6c-4e68-a345-c51cdb99a20b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65662d3e62abbeb06127c7b5a49479a23fb20a7a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070944"
---
# <a name="compiler-warning-level-3-c4522"></a>Derleyici Uyarısı (Düzey 3) C4522

'class': belirtilen birden fazla atama işleçleri

Sınıfın tek bir türde birden fazla atama işleci vardır. Bu uyarı, bilgi amaçlıdır; Oluşturucular, programınızda çağrılabilir.

Kullanım [uyarı](../../preprocessor/warning.md) Bu uyarının gösterilmemesi için pragması.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4522 oluşturur.

```
// C4522.cpp
// compile with: /EHsc /W3
#include <iostream>

using namespace std;
class A {
public:
   A& operator=( A & o ) { cout << "A&" << endl; return *this; }
   A& operator=( const A &co ) { cout << "const A&" << endl; return *this; }   // C4522
};

int main() {
   A o1, o2;
   o2 = o1;
   const A o3;
   o1 = o3;
}
```