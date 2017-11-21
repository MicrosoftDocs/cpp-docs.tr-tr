---
title: "Derleyici Hatası C3153 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3153
dev_langs: C++
helpviewer_keywords: C3153
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9d6a2ad948ae8d5517f7b98316b4e3c67bea5afb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3153"></a>Derleyici Hatası C3153
'arabirimi': arabiriminin bir örneği oluşturulamıyor  
  
 Bir arabirim başlatılamaz. Arabirim üyeleri kullanmak için arabirimi öğesinden bir sınıf türetin, arabirim üyeleri uygulayan ve üyeleri kullanır.  
  
 Aşağıdaki örnek C3153 oluşturur:  
  
```  
// C3153.cpp  
// compile with: /clr  
interface class A {  
};  
  
int main() {  
   A^ a = gcnew A;   // C3153  
}  
```  
