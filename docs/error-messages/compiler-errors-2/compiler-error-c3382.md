---
title: "Derleyici Hatası C3382 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3382
dev_langs: C++
helpviewer_keywords: C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 782e5c4cc61294dbdaecbd63ff5c6031d387f843
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3382"></a>Derleyici Hatası C3382
/ CLR: safe ile 'sizeof' desteklenmiyor  
  
 Çıktı dosyası bir **/CLR: safe** derleme doğrulanabilir şekilde güvenli türü olan bir dosya olduğundan ve sizeof büyüklüğü işletim sistemine bağlı olarak değişir size_t sizeof işleci dönüş değeri olduğu için desteklenmiyor.  
  
 Daha fazla bilgi için bkz:  
  
-   [sizeof işleci](../../cpp/sizeof-operator.md)  
  
-   [/ CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Genel Visual C++ 64-bit geçiş sorunları](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3382 oluşturur.  
  
```  
// C3382.cpp  
// compile with: /clr:safe  
int main() {  
   sizeof( char );   // C3382  
}  
```