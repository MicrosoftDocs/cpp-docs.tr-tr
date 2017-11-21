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
ms.openlocfilehash: 2b869ca0ba959e9b774a005298ef4456d0995156
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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