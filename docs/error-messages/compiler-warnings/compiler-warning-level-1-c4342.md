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
ms.openlocfilehash: 1df710912338aa540dd2a29f859fc4533445b09b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4342"></a>Derleyici Uyarısı (düzey 1) C4342
davranış değişikliği: '*işlevi*' çağrılır, ancak üye işleci önceki sürümlerde çağrıldı  
  
 Visual Studio 2002 önce Visual C++ sürümlerinde, üyesi çağrıldı, ancak bu davranışı değişmiştir ve ve derleyici şimdi en iyi eşleşmeyi ad alanı kapsamında bulur.  
  
 Üye işleci bulunduysa derleyici daha önce tüm ad alanı kapsamı işleçleri dikkate. Ad alanı kapsamında daha iyi bir eşleşme varsa, önceki derleyicileri düşünün olmayacaktır ancak geçerli derleyici doğru çağırır.  
  
 Başarıyla kodunuzu geçerli sürümü için bağlantı noktası sonra bu uyarıyı devre dışı gerekir.  Derleme kodu için bu uyarı oluşturma hatalı pozitif sonuç verebilir söz konusu olduğunda davranış değişikliği.  
  
 Varsayılan olarak bu uyarı kapalıdır. Daha fazla bilgi için bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
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