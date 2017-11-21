---
title: "Derleyici Hatası C2082 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2082
dev_langs: C++
helpviewer_keywords: C2082
ms.assetid: 87a6d442-157c-46e8-9bff-8388f8338ae0
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fc76b22d70f23639758706f6fdcb13a0adbfbb69
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2082"></a>Derleyici Hatası C2082
biçimsel parametresi 'tanımlayıcısı' yeniden tanımlama  
  
 Bir çalışması biçimsel parametresi, işlev gövdesi içinde yeniden bildirilen. Hatayı gidermek için yeniden tanımlama kaldırın.  
  
 Aşağıdaki örnek C2082 oluşturur:  
  
```  
// C2082.cpp  
void func(int i) {  
   int i;   // C2082  
   int ii;   // OK  
}  
```