---
title: "Derleyici Hatası C2365 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2365
dev_langs: C++
helpviewer_keywords: C2365
ms.assetid: 35839b0b-4055-4b79-8957-b3a0871bdd02
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0df8543311b2212a53b571cf47fd4e0de54b003a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2365"></a>Derleyici Hatası C2365
'sınıf üyesi': şemadaki; Önceki tanımı 'sınıf üyesi' idi  
  
 Sınıf üyesine tanımlanacak çalıştı.  
  
 Aşağıdaki örnek C2365 oluşturur.  
  
```  
// C2365.cpp  
// compile with: /c  
class C1 {  
   int CFunc();  
   char *CFunc;   // C2365, already exists as a member function  
  
   int CMem;  
   char *CMem();   // C2365, already exists as a data member  
};  
```