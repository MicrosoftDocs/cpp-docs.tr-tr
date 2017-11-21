---
title: "Derleyici Hatası C2513 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2513
dev_langs: C++
helpviewer_keywords: C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7eb4e7c63821f449bf9677cb5fe03c448bbbc6ee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2513"></a>Derleyici Hatası C2513
'type': hiçbir değişken bildirilen '=' önce  
  
 Hiçbir değişken tanımlayıcıyla bildiriminde tür belirteci görüntülenir.  
  
 Aşağıdaki örnek C2513 oluşturur:  
  
```  
// C2513.cpp  
int main() {  
   int = 9;   // C2513  
   int i = 9;   // OK  
}  
```  
  
 Bu hata, Visual Studio .NET 2003'te yapılan bir derleyici uyumluluğu iş sonucunda da oluşturulabilir: artık izin TypeDef başlatma. Bir typedef başlatma standardına göre izin verilmiyor ve şimdi derleyici hatası oluşturur.  
  
```  
// C2513b.cpp  
// compile with: /c  
typedef struct S {  
   int m_i;  
} S = { 1 };   // C2513  
// try the following line instead  
// } S;  
```  
  
 Silmek için bir alternatif olacaktır `typedef` bu türle aynı ada sahip bir değişken oluşturun ve tür adı gizlemek için toplama başlatıcı listesi, ancak bu bir değişkeni tanımlamak için önerilmez.