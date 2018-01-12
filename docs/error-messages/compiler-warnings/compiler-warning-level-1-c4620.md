---
title: "Derleyici Uyarısı (düzey 1) C4620 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4620
dev_langs: C++
helpviewer_keywords: C4620
ms.assetid: fed29934-b797-47e8-bbea-c7e5f8dd6e93
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f550a857f1799e32d599231348123e3f85a0dfd5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4620"></a>Derleyici Uyarısı (düzey 1) C4620
hiçbir sonek biçiminde ' işleci ++' türü 'type' öneki formunu kullanarak, bulundu  
  
 Belirtilen tür için tanımlı hiçbir sonek artırma işlecinin yoktur. Derleyici aşırı yüklenmiş önek işleci kullanılır.  
  
 Bu uyarı bir sonek tanımlayarak önlenebilir `++` işleci. İki bağımsız değişken sürümünü Oluştur `++` aşağıda gösterildiği gibi işleci:  
  
```  
// C4620.cpp  
// compile with: /W1  
class A  
{  
public:  
   A(int nData) : m_nData(nData)  
   {  
   }  
  
   A operator++()  
   {  
      m_nData -= 1;  
      return *this;  
   }  
  
   // A operator++(int)  
   // {  
   //    A tmp = *this;  
   //    m_nData -= 1;  
   //    return tmp;  
   // }  
  
private:  
   int m_nData;  
};  
  
int main()  
{  
   A a(10);  
   ++a;  
   a++;   // C4620  
}  
```