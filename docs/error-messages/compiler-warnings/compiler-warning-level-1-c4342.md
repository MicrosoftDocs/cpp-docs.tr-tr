---
title: Derleyici Uyarısı (düzey 1) C4342
ms.date: 11/04/2016
f1_keywords:
- C4342
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
ms.openlocfilehash: 439c4976f25688fd9220c3f58ceb933266b5f15c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187515"
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