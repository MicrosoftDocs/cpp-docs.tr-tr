---
title: "Derleyici Uyarısı (düzey 4) C4670 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4670
dev_langs: C++
helpviewer_keywords: C4670
ms.assetid: e172b134-b1fb-4dfe-8e9d-209ea08b73c7
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 49c29f03b8b6f364cddd0c55672b4ab246f1e708
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4670"></a>Derleyici Uyarısı (düzey 4) C4670
'tanımlayıcısı': taban sınıfı erişilemiyor  
  
 Belirtilen taban sınıfı durum oluşturulmasına bir nesnenin bir **deneyin** blok erişilebilir durumda değil. Bu durum, nesne örneği oluşturulamıyor. Temel sınıfı ile doğru erişim belirticisi devralınır denetleyin.  
  
 Aşağıdaki örnek C4670 oluşturur:  
  
```  
// C4670.cpp  
// compile with: /EHsc /W4  
class A  
{  
};  
  
class B : /* public */ A  
{  
} b;   // inherits A with private access by default  
  
int main()  
{  
    try  
    {  
       throw b;   // C4670  
    }  
    catch( B )  
    {  
    }  
}  
```