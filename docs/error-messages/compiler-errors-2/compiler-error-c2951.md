---
title: "Derleyici Hatası C2951 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2951
dev_langs:
- C++
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad6d5f3b7ab97b799a23c124505d8930774918aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2951"></a>Derleyici Hatası C2951
tür bildirimleri genel ad alanında yalnızca izin verilen veya kapsam sınıfı  
  
 Bir genel veya genel dışında Şablon sınıfı veya ad alanı kapsamında bildiremezsiniz. Genel veya şablon bildirimlerinizde bir içerme dosyası yaparsanız, genel kapsamda içerme dosyası olduğundan emin olun.  
  
 Aşağıdaki örnek C2951 oluşturur:  
  
```  
// C2951.cpp  
template <class T>  
class A {};  
  
int main() {  
   template <class T>   // C2951  
   class B {};  
}  
```  
  
 Ayrıca C2951 genel türler kullanma ortaya çıkabilir:  
  
```  
// C2951b.cpp  
// compile with: /clr /c  
  
// OK  
generic <class T>   
ref class GC { };  
  
int main() {  
   generic <class T> ref class GC2 {};   // C2951  
}  
```