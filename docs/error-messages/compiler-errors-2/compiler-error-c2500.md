---
title: "Derleyici Hatası C2500 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2500
dev_langs: C++
helpviewer_keywords: C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9a7be7320c21469536f6ddada99abd862812d882
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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