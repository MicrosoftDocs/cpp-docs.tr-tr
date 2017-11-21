---
title: "Derleyici Hatası C2811 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2811
dev_langs: C++
helpviewer_keywords: C2811
ms.assetid: 6a44b18e-44c1-49d8-9b99-e0545b9a6e7d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b5a8f38fecb6b139a8e36007affc1a394bd81254
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2811"></a>Derleyici Hatası C2811
'type1': 'type2' bir ref devral olamaz sınıfı yalnızca devralınan bir ref sınıf veya arabirim sınıfı  
  
 Yönetilmeyen bir sınıfı için yönetilen bir sınıfın temel sınıf olarak kullanma girişimi.  
  
 Aşağıdaki örnek C2811 oluşturur:  
  
```  
// C2811.cpp  
// compile with: /clr /c  
struct S{};  
ref struct T {};  
ref class C : public S {};   // C2811  
ref class D : public T {};   // OK  
```