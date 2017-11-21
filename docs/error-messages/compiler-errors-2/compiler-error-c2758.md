---
title: "Derleyici Hatası C2758 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2758
dev_langs: C++
helpviewer_keywords: C2758
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f694df9f39edbc257b887bcfd9bd13a0ba31a1a0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2758"></a>Derleyici Hatası C2758
'member': başvuru türü üyesi başlatılması gerekir  
  
 Derleyici Hatası oluşturucu başlatıcı listesinde bir başvuru türü üyesi Başlatmıyor C2758 ortaya çıkar. Derleyici tanımsız üye bırakır. Değişkenleri gerekir başvuru üyesi olduğunda başlatılmış bildirilen veya oluşturucusu başlatma listesinde bir değer verilmesi.  
  
 Aşağıdaki örnek C2758 oluşturur:  
  
```  
// C2758.cpp  
// Compile by using: cl /W3 /c C2758.cpp  
struct A {  
   const int i;  
  
   A(int n) { };   // C2758  
   // try the following line instead  
   // A(int n) : i{n} {};  
};  
```