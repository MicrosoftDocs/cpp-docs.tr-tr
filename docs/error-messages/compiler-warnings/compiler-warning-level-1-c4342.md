---
title: Derleyici Uyarısı (düzey 1) C4342
ms.date: 11/04/2016
f1_keywords:
- C4342
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
ms.openlocfilehash: 8ac00d3d57f8cf7d6c85f3106dbe9b8c3cb9adf0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162926"
---
# <a name="compiler-warning-level-1-c4342"></a>Derleyici Uyarısı (düzey 1) C4342

davranış değişikliği: '*Function*' çağrıldı, ancak önceki sürümlerde bir üye işleci çağrıldı

Visual Studio 2002 ' C++ den önceki Visual sürümlerinde bir üye çağrıldı, ancak bu davranış değiştirilmiştir ve derleyici artık ad uzayı kapsamında en iyi eşleşmeyi buluyor.

Bir üye operatörü bulunursa, derleyici daha önce herhangi bir ad alanı kapsam işlecini kabul etmez. Ad alanı kapsamında daha iyi bir eşleşme varsa, geçerli derleyici bunu doğru şekilde çağırır, ancak önceki derleyiciler bunu dikkate alınmaz.

Kodunuzun geçerli sürüme başarıyla bağlantı kurulduktan sonra bu uyarı devre dışı bırakılmalıdır.  Derleyici, hiçbir davranış değişikliğinin olmadığı kod için bu uyarıyı oluşturmak için hatalı pozitif sonuçlar verebilir.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

Aşağıdaki örnek C4342 oluşturur:

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
