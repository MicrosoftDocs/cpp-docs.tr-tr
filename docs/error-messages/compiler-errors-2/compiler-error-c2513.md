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
ms.workload: cplusplus
ms.openlocfilehash: 62c55a1a6eb093d4ef6921f6d0f8b7c50683ff8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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