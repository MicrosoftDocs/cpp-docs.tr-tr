---
title: "Derleyici Uyarısı (düzey 4) C4673 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4673
dev_langs:
- C++
helpviewer_keywords:
- C4673
ms.assetid: 95626ec6-f05b-43c7-8b9a-a60a6f98dd30
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bff39a9045ba1543f42eb7e02b82565421969d8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4673"></a>Derleyici Uyarısı (düzey 4) C4673
Aşağıdaki türlerden 'tanımlayıcısı' atma catch sitede değerlendirilmeyecek  
  
 İçinde bir throw nesnesi işlenemiyor **catch** bloğu. İşlenemez her türü hemen bu uyarıyı içeren satırı aşağıdaki hata çıktısında listelenir. Her işlenmemiş türü kendi uyarı sahiptir. Daha fazla bilgi için belirli her türünün uyarıyı okuyun.  
  
 Aşağıdaki örnek C4673 oluşturur:  
  
```  
// C4673.cpp  
// compile with: /EHsc /W4  
class Base {  
private:  
   char * m_chr;  
public:  
   Base() {  
      m_chr = 0;  
   }  
  
   ~Base() {  
      if(m_chr)  
         delete m_chr;  
   }  
};  
  
class Derv : private Base {  
public:  
   Derv() {}  
   ~Derv() {}  
};  
  
int main() {  
   try {  
      Derv D1;  
      // delete previous line, uncomment the next line to resolve  
      // Base D1;  
      throw D1;   // C4673  
   }  
  
   catch(...) {}  
}  
```