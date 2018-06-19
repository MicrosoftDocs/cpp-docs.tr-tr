---
title: Derleyici Hatası C2600 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2600
dev_langs:
- C++
helpviewer_keywords:
- C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13b4cdf15dca9b3978f8c7855a5f1b07cc86f0b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230956"
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