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
ms.workload: cplusplus
ms.openlocfilehash: ba427de26d07851c5bf2a2dd3f599c4cbe7afc5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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