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
ms.workload: cplusplus
ms.openlocfilehash: a67763ba2c2b8f72f539cdb5528e696eaa700f8b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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