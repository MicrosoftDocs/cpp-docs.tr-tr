---
title: Derleyici Hatası C2920 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2920
dev_langs:
- C++
helpviewer_keywords:
- C2920
ms.assetid: 0a4cb2de-00a0-4209-8160-c7ce6ed7d9ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18a2ccc8809b18d9a28b1fc60f5460dd4272a49c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2920"></a>Derleyici Hatası C2920
yeniden tanımlama: 'sınıfı': sınıf şablonu veya genel zaten bildirildiği 'türünde'  
  
 Bir genel veya Şablon sınıfı eşdeğer olmayan birden çok bildirimleri var. Bu hatayı düzeltmek için farklı türleri için farklı adlar kullanın veya tür adı şemadaki kaldırın.  
  
 Aşağıdaki örnek C2920 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2920.cpp  
// compile with: /c  
typedef int TC1;  
template <class T>   
struct TC1 {};   // C2920  
struct TC2 {};   // OK - fix by using a different name  
```  
  
 Ayrıca C2920 genel türler kullanma ortaya çıkabilir:  
  
```  
// C2920b.cpp  
// compile with: /clr /c  
typedef int GC1;  
generic <class T>   
ref struct GC1 {};   // C2920  
ref struct GC2 {};   // OK - fix by using a different name  
```