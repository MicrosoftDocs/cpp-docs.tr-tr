---
title: "Derleyici Hatası C2600 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2600
dev_langs:
- C++
helpviewer_keywords:
- C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 407598a68df37aa130ce26e4f02e98de975ab527
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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