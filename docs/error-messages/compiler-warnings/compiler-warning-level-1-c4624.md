---
title: Derleyici Uyarısı (düzey 1) C4624 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4624
dev_langs:
- C++
helpviewer_keywords:
- C4624
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d11bc5c8b5034fa305a22ba893c62faff18cc38
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281040"
---
# <a name="compiler-warning-level-1-c4624"></a>Derleyici Uyarısı (düzey 1) C4624
'türetilmiş bir sınıf': yıkıcı bir temel sınıf yıkıcı erişilemez veya silinmiş olduğundan silindi olarak örtük olarak tanımlanmıştı  
  
 Bir yıkıcı erişilebilir ya da bir taban sınıf içinde silinen değildi ve türetilmiş bir sınıf için oluşturulmamış. Yığında bu türde bir nesne oluşturma girişimi herhangi bir derleyici hatasına neden olur.  
  
 Aşağıdaki örnek C4624 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C4624.cpp  
// compile with: /W1 /c  
class B {  
// Uncomment the following line to fix.  
// public:  
   ~B();  
};  
  
class D : public B {};   // C4624 B's destructor not public  
```