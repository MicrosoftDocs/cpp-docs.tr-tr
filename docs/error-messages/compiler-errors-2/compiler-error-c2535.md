---
title: "Derleyici Hatası C2535 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2535
dev_langs:
- C++
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2cdcd4aa00f0b96e0995e7589a8bbe4d1b990c74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2535"></a>Derleyici Hatası C2535
'tanımlayıcısı': önceden tanımlanmış veya bildirilen üye işlevi  
  
 Birden fazla tanımı veya aşırı yüklenmiş bir işlevin bildirimi aynı biçimsel parametresi listesini kullanarak bu hataya neden.  
  
 Dispose işlevi nedeniyle C2535 alırsanız, bkz: [yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) daha fazla bilgi için.  
  
 ATL projesinde derleme, Bilgi Bankası makalesi Q241852 bakın.  
  
 Aşağıdaki örnek C2535 oluşturur:  
  
```  
// C2535.cpp  
// compile with: /c  
class C {  
public:  
   void func();   // forward declaration  
   void func() {}   // C2535  
};  
```