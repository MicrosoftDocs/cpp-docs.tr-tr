---
title: "Derleyici Hatası C2600 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2600
dev_langs: C++
helpviewer_keywords: C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1fe5383e17212b21c11394c6b987e92aacbe637e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2600"></a>Derleyici Hatası C2600
'function': (bildirilmelidir sınıfta ilk) derleyicinin ürettiği özel üye işlevi tanımlanamıyor  
  
 Oluşturucular veya Yıkıcılar gibi işlevler için bir sınıf tanımlanabilir üye önce bunlar sınıfında bildirilmelidir. Hiçbiri sınıfında tanımlanan varsa derleyici varsayılan oluşturucular ve Yıkıcılar (özel üye işlevleri adı verilir) oluşturabilirsiniz. Ancak, bu işlevler eşleşen bir bildirimi olmadan birini sınıfında tanımlarsanız derleyici bir çakışma algılar.  
  
 Sınıf bildiriminde bu hatayı düzeltmek için sınıf bildiriminin dışında tanımladığınız her üye işlevi bildirin.  
  
 Aşağıdaki örnek C2600 oluşturur:  
  
```  
// C2600.cpp  
// compile with: /c  
class C {};  
C::~C() {}   // C2600  
  
class D {  
   D::~D();  
};  
  
D::~D() {}  
```