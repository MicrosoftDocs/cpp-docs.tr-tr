---
title: "Derleyici Uyarısı (düzey 1) c4584 arasındaki | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4584
dev_langs: C++
helpviewer_keywords: C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1c17d8871d16cd2eec6b46e01d9c1779f3440398
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4584"></a>Derleyici Uyarısı (düzey 1) c4584 arasındaki
'class1': temel sınıf 'class2' olan zaten 'Ders3 alanları' ın bir temel sınıf  
  
 Bunlardan biri diğer devralır iki sınıf, tanımlanmış sınıf devralır. Örneğin:  
  
```  
// C4584.cpp  
// compile with: /W1 /LD  
class A {  
};  
  
class B : public A {  
};  
  
class C : public A, public B { // C4584  
};  
```  
  
 Hem A ve sınıf da A. sınıfından devralan B öğesinden devraldığı için bu durumda, bir uyarı C sınıfı verilmesi Bu uyarı, temel sınıflar üyelerinden kullanımını tam olarak nitelemek gerekir veya derleyici hatası hangi sınıf üyesine aldığını başvurmak belirsizlik nedeniyle oluşturulacak bir anımsatıcı olarak görev yapar.