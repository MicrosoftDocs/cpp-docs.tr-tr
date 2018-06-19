---
title: Derleyici Hatası C3116 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3116
dev_langs:
- C++
helpviewer_keywords:
- C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fde589df31e6e3b75f9a0153d7383ab1e85ed180
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33250349"
---
# <a name="compiler-error-c3116"></a>Derleyici Hatası C3116
'depolama birimi tanımlayıcısı': arabirim yöntemi için geçersiz depolama sınıfı  
  
 Kullanılan `typedef`, `register`, veya `static` arabirim yöntemi için depolama sınıf olarak. Bu depolama sınıfları arabirim üyeleri üzerinde izin verilmez.  
  
 Aşağıdaki örnek C3116 oluşturur:  
  
```  
// C3116.cpp  
__interface ImyInterface  
{  
   static void myFunc();   // C3116  
};  
```