---
title: "Derleyici Hatası C2228 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2228
dev_langs: C++
helpviewer_keywords: C2228
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6960d2a34a6a68925e04e0812730025d1ce2ff92
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2228"></a>Derleyici Hatası C2228
'.identifier' solundaki struct/sınıfı/birleşimi olmalıdır  
  
 Nokta (.) sol işleneni bir sınıf, yapı veya birleşim değil.  
  
 Aşağıdaki örnek C2228 oluşturur:  
  
```  
// C2228.cpp  
int i;  
struct S {  
public:  
    int member;  
} s, *ps = &s;  
  
int main() {  
   i.member = 0;   // C2228 i is not a class type  
   ps.member = 0;  // C2228 ps is a pointer to a structure  
  
   s.member = 0;   // s is a structure type  
   ps->member = 0; // ps points to a structure S  
}  
```  
  
 Yönetilen Uzantılar kullanırken sözdizimi yanlış kullanırsanız, bu hata iletisiyle karşılaşırsınız. Diğer Visual Studio dillerde dot işleci bir yönetilen sınıf üyesi erişmek için kullanabileceğiniz gelirken, c++ nesnesine bir işaretçi kullanmak zorunda demektir -> işleci üye erişmek için:  
  
 Yanlış:`String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`  
  
 Sağ:`String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`