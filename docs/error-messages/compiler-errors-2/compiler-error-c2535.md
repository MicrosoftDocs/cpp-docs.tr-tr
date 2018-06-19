---
title: Derleyici Hatası C2535 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2535
dev_langs:
- C++
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1dc791cd7782cc758aa51b0c61d87a79570c13c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229567"
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