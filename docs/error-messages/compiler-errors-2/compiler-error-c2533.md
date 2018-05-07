---
title: Derleyici Hatası C2533 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2533
dev_langs:
- C++
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06733dc8ee52462ab7fcac4255ee8fa697a9bac4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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