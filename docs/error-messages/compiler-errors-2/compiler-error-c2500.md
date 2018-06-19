---
title: Derleyici Hatası C2500 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2500
dev_langs:
- C++
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c05ffd59e415375dd3c7f94ae9bc377c0fc2b9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229228"
---
# <a name="compiler-error-c2500"></a>Derleyici Hatası C2500
'identifier1': 'identifier2' doğrudan temel sınıf bulunmakta  
  
 Bir sınıf veya yapı taban sınıflar listesi içinde birden fazla kez görüntülenir.  
  
 Bir doğrudan taban temel listesinde belirtilen biridir. Temel listesinde sınıflarından birini temel bir sınıfında bir dolaylı tabanıdır.  
  
 Bir sınıf doğrudan bir temel sınıf olarak birden çok kez belirtilemez. Bir sınıf dolaylı bir temel sınıf olarak birden çok kez kullanılabilir.  
  
 Aşağıdaki örnek C2500 oluşturur:  
  
```  
// C2500.cpp  
// compile with: /c  
class A {};  
class B : public A, public A {};    // C2500  
  
// OK  
class C : public A {};  
class D : public A {};  
class E : public C, public D {};  
```