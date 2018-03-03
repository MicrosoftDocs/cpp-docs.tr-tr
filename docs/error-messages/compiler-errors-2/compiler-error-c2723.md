---
title: "Derleyici Hatası C2723 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2723
dev_langs:
- C++
helpviewer_keywords:
- C2723
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 587dd742a089a0eddc416e59563cd1e0707e662b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2723"></a>Derleyici Hatası C2723
'function': 'tanımlayıcısı' tanımlayıcısı işlev tanımı geçersiz  
  
 Belirleyici işlevi tanımlı bir sınıf bildiriminin dışında yer alamaz. `virtual` Belirleyicisi yalnızca bir üye işlevi bildirimi sınıf bildirimi içinde üzerinde belirtilebilir.  
  
 Aşağıdaki örnek C2723 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2723.cpp  
struct X {  
   virtual void f();  
   virtual void g();  
};  
  
virtual void X::f() {}   // C2723  
  
// try the following line instead  
void X::g() {}  
```