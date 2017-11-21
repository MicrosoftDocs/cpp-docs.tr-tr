---
title: "Derleyici Hatası C2206 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2206
dev_langs: C++
helpviewer_keywords: C2206
ms.assetid: d7fba68b-aa28-4885-a9a0-27107358f066
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f68484c5e28206b29cb4a76d4333c7c2c5fb266e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2206"></a>Derleyici Hatası C2206
'function': typedef işlev tanımı için kullanılamaz  
  
 A `typedef` bir işlev türü tanımlamak için kullanılır.  
  
 Aşağıdaki örnek C2206 oluşturur:  
  
```  
// C2206.cpp  
typedef int functyp();  
typedef int MyInt;  
functyp func1 {};   // C2206  
int main() {  
   MyInt i = 0;   // OK  
}  
```