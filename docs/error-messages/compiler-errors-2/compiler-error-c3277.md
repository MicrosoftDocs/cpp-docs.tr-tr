---
title: "Derleyici Hatası C3277 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3277
dev_langs: C++
helpviewer_keywords: C3277
ms.assetid: 8ac5f476-e30c-4879-92c6-f03cdbd74045
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c5ce51c198c998b96dfa941cb088276b610142f1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3277"></a>Derleyici Hatası C3277
Yönetilmeyen enum 'enum' yönetilen 'type' tanımlanamıyor  
  
 Numaralandırma yanlış bir yönetilen türü içinde tanımlandı.  
  
 Aşağıdaki örnek C3277 oluşturur:  
  
```  
// C3277a.cpp  
// compile with: /clr  
ref class A  
{  
   enum E {e1,e2};   // C3277  
   // try the following line instead  
   // enum class E {e1,e2};  
};  
  
int main()  
{  
}  
```  
