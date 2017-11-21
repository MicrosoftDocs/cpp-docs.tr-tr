---
title: "Derleyici Hatası C2794 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2794
dev_langs: C++
helpviewer_keywords: C2794
ms.assetid: d508191c-9044-4c6a-9119-4bca668c0b93
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5b25829804bf8cb375507550f339022d09951d35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2794"></a>Derleyici Hatası C2794
'function': 'sınıfının' herhangi doğrudan veya dolaylı olarak temel sınıf üyesi değil  
  
 Kullanmaya çalıştığınız [Süper](../../cpp/super.md) varolmayan üye işlevi çağırmak için.  
  
 Aşağıdaki örnek C2794 oluşturur  
  
```  
// C2794.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super::f();  // C2794  
   }  
};  
```