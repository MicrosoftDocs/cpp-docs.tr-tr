---
title: "Derleyici Hatası C3848 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3848
dev_langs: C++
helpviewer_keywords: C3848
ms.assetid: 32d3ccef-01ec-4f8b-bbff-fb9b1a76b4c4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3220d3d278c0b5d877273b96defc23ac5852e066
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3848"></a>Derleyici Hatası C3848
ifade türü 'type' sahip 'function' çağırmak için bazı const geçici niteleyicileri kaybeder  
  
 Belirtilen bir const geçici türüne sahip bir değişken, yalnızca üye ile aynı veya daha büyük const geçici nitelikleri tanımlanan işlevleri çağırabilir.  
  
 Aşağıdaki örnekler C3848 oluştur:  
  
```  
// C3848.cpp  
void glbFunc1()  
{  
}  
  
typedef void (* pFunc1)();  
  
struct S3  
{  
   operator pFunc1() // const  
   {  
      return &glbFunc1;  
   }  
};  
  
int main()  
{  
   const S3 s3;  
   s3();   // C3848, uncomment const qualifier  
}  
```