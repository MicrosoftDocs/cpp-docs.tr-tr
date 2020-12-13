---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4342'
title: Derleyici Uyarısı (düzey 1) C4342
ms.date: 11/04/2016
f1_keywords:
- C4342
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
ms.openlocfilehash: f08cf24b0fe429e8b788a20fbcb05d2a8cd8b1d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340027"
---
# <a name="compiler-warning-level-1-c4342"></a>Derleyici Uyarısı (düzey 1) C4342

davranış değişikliği: '*Function*' çağrıldı, ancak önceki sürümlerde bir üye işleci çağrıldı

Visual Studio 2002 ' den önceki Visual C++ sürümlerinde bir üye çağrıldı, ancak bu davranış değiştirilmiştir ve derleyici artık ad uzayı kapsamında en iyi eşleşmeyi buluyor.

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
