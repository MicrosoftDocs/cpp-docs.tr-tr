---
title: "Derleyici Hatası C3182 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3182
dev_langs: C++
helpviewer_keywords: C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7af33bd1854525bebd5d0cb423558d6077366431
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3182"></a>Derleyici Hatası C3182
'class': üye kullanarak bildirimi veya erişim bildirimi yönetilen veya WinRTtype içinde geçersiz  
  
 A [kullanarak](../../cpp/using-declaration.md) bildirimi tüm yönetilen sınıflar formları içinde geçersiz.  
  
 Aşağıdaki örnek C3182 oluşturur ve nasıl düzeltileceği gösterir.  
  
```  
// C3182a.cpp  
// compile with: /clr /c  
ref struct B {  
   void mf(int) {  
   }  
};  
  
ref struct D : B {  
   using B::mf;   // C3182, delete to resolve  
   void mf(char) {  
   }  
};  
```  
