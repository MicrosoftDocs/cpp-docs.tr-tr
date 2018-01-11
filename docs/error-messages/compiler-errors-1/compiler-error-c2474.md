---
title: "Derleyici Hatası C2474 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2474
dev_langs: C++
helpviewer_keywords: C2474
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 91384ef6ea2a26ad21a8a43f022819b846efb385
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2474"></a>Derleyici Hatası C2474
'anahtar sözcüğü': bitişik bir noktalı virgül eksik olabilir anahtar sözcüğü veya tanımlayıcısı.  
  
 Derleyici noktalı virgül bekleniyordu ve maksadınızı belirleyemedi. Bu hatayı gidermek için noktalı virgül ekleyin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2474 oluşturur.  
  
```  
// C2474.cpp  
// compile with: /clr /c  
  
ref class A {  
   ref class B {}  
   property int i;   // C2474 error  
};  
  
// OK  
ref class B {  
   ref class D {};  
   property int i;  
};  
  
ref class E {  
   ref class F {} property;   
   int i;  
};  
```