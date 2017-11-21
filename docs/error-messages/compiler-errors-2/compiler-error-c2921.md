---
title: "Derleyici Hatası C2921 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2921
dev_langs: C++
helpviewer_keywords: C2921
ms.assetid: 323642a0-bfc4-4942-9f41-c3adf5c54296
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e67921dab2b76f752bdf77184c16be2549bd3127
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2921"></a>Derleyici Hatası C2921
yeniden tanımlama: 'sınıfı': sınıf şablonu veya genel yeniden bildirilen 'türünde'  
  
 Bir genel veya Şablon sınıfı eşdeğer olmayan birden çok bildirimleri var. Bu hatayı düzeltmek için farklı türleri için farklı adlar kullanın veya tür adı şemadaki kaldırın.  
  
 Aşağıdaki örnek C2921 oluşturur:  
  
```  
// C2921.cpp  
// compile with: /c  
template <class T> struct TC2 {};  
typedef int TC2;   // C2921  
// try the following line instead  
// typedef struct TC2<int> x;   // OK - declare a template instance   
```  
  
 Ayrıca C2921 genel türler kullanma ortaya çıkabilir.  
  
```  
// C2921b.cpp  
// compile with: /clr /c  
generic <class T> ref struct GC2 {};  
typedef int GC2;   // C2921  
// try the following line instead  
// typedef ref struct GC2<int> x;  
```