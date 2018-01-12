---
title: "Derleyici Hatası C2507 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2507
dev_langs: C++
helpviewer_keywords: C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f520dee6ad9630dc338010311119ae9f41bbf86b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2507"></a>Derleyici Hatası C2507
'tanımlayıcısı': çok fazla sayıda sanal değiştiricileri temel sınıfı  
  
 Bir sınıf veya yapı olarak bildirilmiş `virtual` birden çok kez. Yalnızca bir `virtual` değiştiricisi her sınıfı temel sınıflar için bir listede görünebilir.  
  
 Aşağıdaki örnek C2507 oluşturur:  
  
```  
// C2507.cpp  
// compile with: /c  
class A {};  
class B : virtual virtual public A {};   // C2507  
class C : virtual public A {};   // OK  
```