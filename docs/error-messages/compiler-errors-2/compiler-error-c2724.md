---
title: "Derleyici Hatası C2724 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2724
dev_langs: C++
helpviewer_keywords: C2724
ms.assetid: 4e4664bc-8c96-4156-b79f-03436f532ea8
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 13c582f081d78e415b4c98bf300b18004fcc33bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2724"></a>Derleyici Hatası C2724
'tanımlayıcısı': 'static' kullanılmamalıdır üzerinde dosya kapsamında tanımlı üye işlevleri  
  
 Statik üye işlevleri ile dış bağlantı bildirilmelidir.  
  
 Aşağıdaki örnek C2724 oluşturur:  
  
```  
// C2724.cpp  
class C {  
   static void func();  
};  
  
static void C::func(){};   // C2724  
// try the following line instead  
// void C::func(){};  
```