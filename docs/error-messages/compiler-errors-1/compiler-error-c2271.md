---
title: "Derleyici Hatası C2271 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2271
dev_langs: C++
helpviewer_keywords: C2271
ms.assetid: ea47bf57-f55d-4171-8e98-95a71d62820e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 59a4057d9d52df1a8a1b4b629dc3a13ae4c4c7a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2271"></a>Derleyici Hatası C2271
'işleci': yeni/silme resmi listesi değiştiricileri sahip olamaz  
  
 İşleç (`new` veya `delete`) bellek model tanımlayıcısı ile bildirilmedi.  
  
 Aşağıdaki örnek C2271 oluşturur:  
  
```  
// C2271.cpp  
// compile with: /c  
void* operator new(size_t) const {   // C2271  
// try the following line instead  
// void* operator new(size_t) {  
   return 0;  
}  
  
struct X {  
   static void* operator new(size_t) const;   // C2271  
   // try the following line instead  
   // void * X::operator new(size_t) const;   // static member operator new  
};  
```