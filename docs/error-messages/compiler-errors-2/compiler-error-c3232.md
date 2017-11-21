---
title: "Derleyici Hatası C3232 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3232
dev_langs: C++
helpviewer_keywords: C3232
ms.assetid: 3119b3a9-0eff-4a3f-b805-e4d160af9e39
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4298ef45430f97260c041d3aee8e1c943ef9e834
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3232"></a>Derleyici Hatası C3232
'param': genel tür parametresi bir tam ad kullanılamaz  
  
 Genel tür parametresi yanlış kullanıldı.  
  
 Aşağıdaki örnek C3232 oluşturur:  
  
```  
// C3232.cpp  
// compile with: /clr  
generic <class T>  
ref class C {  
   typename T::TYPE t;   // C3232  
};  
```