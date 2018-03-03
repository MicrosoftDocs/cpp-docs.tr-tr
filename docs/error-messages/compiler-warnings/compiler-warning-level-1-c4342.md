---
title: "Derleyici Uyarısı (düzey 1) C4342 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4342
dev_langs:
- C++
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7d2a3550a3d1b7333412b7828809120db89c60b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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