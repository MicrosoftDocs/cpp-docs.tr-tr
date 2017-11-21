---
title: "Derleyici Uyarısı (düzey 1) C4172 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4172
dev_langs: C++
helpviewer_keywords: C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d8e8abc6d26898dda197580e83a34f20acd4b01d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4172"></a>Derleyici Uyarısı (düzey 1) C4172
yerel değişken ya da geçici adresini döndürüyor  
  
 Bir işlev adresi yerel değişken ya da geçici nesne döndürür. İşlevi döndüğünde, döndürülen adresi geçerli değil şekilde yerel değişkenleri ve geçici nesneler yok olur.  
  
 Böylece yerel nesne adresi döndürmüyor işlevi yeniden tasarlamanız.  
  
 Aşağıdaki örnek C4172 oluşturur:  
  
```  
// C4172.cpp  
// compile with: /W1 /LD  
float f = 10;  
  
const double& bar() {  
// try the following line instead  
// const float& bar() {  
   return f;   // C4172  
}  
```