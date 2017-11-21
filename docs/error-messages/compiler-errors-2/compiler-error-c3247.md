---
title: "Derleyici Hatası C3247 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3247
dev_langs: C++
helpviewer_keywords: C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fc07da3d6fa994bfba9588b1169287da8c0d738b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3247"></a>Derleyici Hatası C3247
'class1': bir coclass'ı başka bir coclass 'class2' devralır olamaz  
  
 Bir sınıf ile işaretli [coclass](../../windows/coclass.md) özniteliği ile işaretlenmiş başka bir sınıftan devralır olamaz `coclass` özniteliği.  
  
 Aşağıdaki örnek C3247 oluşturur:  
  
```  
// C3247.cpp  
[module(name="MyLib")];  
[coclass]  
class a {  
};  
  
[coclass]  
class b : public a {   // C3247  
};  
int main() {  
}  
```