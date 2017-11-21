---
title: "Derleyici Uyarısı C4355 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4355
dev_langs: C++
helpviewer_keywords: C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 061ad3df17cf9c86fbc5ac98048932aff8b0b25b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-c4355"></a>Derleyici Uyarısı C4355
'this' : taban üye başlatıcı listesinde kullanıldı  
  
 **Bu** işaretçi yalnızca statik olmayan üye işlevleri içinde geçerlidir. İçin bir taban sınıf Başlatıcı listesinde kullanılamaz.  
  
 Önce temel sınıf oluşturucular ve sınıf üyesi oluşturucular çağrılır **bu** Oluşturucusu. Aslında, başka bir oluşturucuya unconstructed nesneye bir işaretçi başarıyla geçmenizin. Bu diğer oluşturucular herhangi bir üye erişmek veya üye işlevlerini bu çağırın, sonucu tanımsız olacaktır. Kullanılamaz **bu** tüm yapım tamamlanana kadar işaretçi.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C4355 oluşturur:  
  
```  
// C4355.cpp  
// compile with: /w14355 /c  
#include <tchar.h>  
  
class CDerived;  
class CBase {  
public:  
   CBase(CDerived *derived): m_pDerived(derived) {};  
   ~CBase();  
   virtual void function() = 0;  
  
   CDerived * m_pDerived;  
};  
  
class CDerived : public CBase {  
public:  
   CDerived() : CBase(this) {};   // C4355 "this" used in derived c'tor  
   virtual void function() {};  
};  
  
CBase::~CBase() {  
   m_pDerived -> function();  
}  
  
int main() {  
   CDerived myDerived;  
}  
```