---
title: "Derleyici Hatası C2533 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2533
dev_langs:
- C++
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c023fb47b0e2653cd7bf13b188b907558573a0ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2533"></a>Derleyici Hatası C2533
'tanımlayıcısı': oluşturucular bir dönüş türüne izin verilmiyor  
  
 Oluşturucu bir dönüş türüne sahip olamaz (değil bile bir `void` dönüş türü).  
  
 Bu hatanın ortak bir kaynaktan bir sınıf tanımı son ve ilk Oluşturucusu uygulama arasında eksik bir noktalı virgül ' dir. Derleyici Oluşturucusu işlevi için dönüş türü tanımı sınıf görür ve C2533 oluşturur.  
  
 Aşağıdaki örnek C2533 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2533.cpp  
// compile with: /c  
class X {  
public:  
   X();     
};  
  
int X::X() {}   // C2533 - constructor return type not allowed  
X::X() {}   // OK - fix by using no return type  
```