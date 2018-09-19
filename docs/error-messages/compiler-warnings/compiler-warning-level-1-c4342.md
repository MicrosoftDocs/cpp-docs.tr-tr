---
title: Derleyici Uyarısı (düzey 1) C4342 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4342
dev_langs:
- C++
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6aeb582ff891cc9d186604af5d2ca2c2844b1cb0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016266"
---
# <a name="compiler-warning-level-1-c4342"></a>Derleyici Uyarısı (düzey 1) C4342

davranış değişikliği: '*işlevi*' çağrıldı, ancak önceki sürümlerde bir üye işleç çağrılıyordu

Visual Studio 2002 önce Visual C++ sürümlerinde, üye çağrıldı, ancak bu davranışı değiştirildi ve derleyici artık ad alanı kapsamında en iyi eşleşme bulur.

Bir üye işleç bulunamazsa derleyici daha önce herhangi bir ad alanı kapsamı işleçleri göz önünde. Ad alanı kapsamında daha iyi bir eşleşme varsa, önceki derleyiciler düşünün mıydı ise geçerli derleyici doğru çağırır.

Kodunuzu geçerli sürüme başarıyla bağlantı noktası sonra bu uyarıyı devre dışı.  Derleyici, bu uyarı için kod oluşturma, hatalı pozitif sonuçları verebilir davranışı değişiklik olduğunda.

Varsayılan olarak bu uyarıyı kapalıdır. Daha fazla bilgi için [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

Aşağıdaki örnek, C4342 oluşturur:

```cpp
// C4342.cpp
// compile with: /EHsc /W1
#include <fstream>
#pragma warning(default: 4342)
using namespace std;
struct X : public ofstream {
   X();
};

X::X() {
   open( "ofs_bug_ev.txt." );
   if ( is_open() ) {
      *this << "Text" << "<-should be text" << endl;   // C4342
      *this << ' ' << "<-should be space symbol" << endl;   // C4342
   }
}

int main() {
   X b;
   b << "Text" << "<-should be text" << endl;
   b << ' ' << "<-should be space symbol" << endl;
}
```