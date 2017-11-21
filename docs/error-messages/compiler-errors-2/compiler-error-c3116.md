---
title: "Derleyici Hatası C3116 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3116
dev_langs: C++
helpviewer_keywords: C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c9503250dd6ff165f6a955d36ebfe38f0715e422
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3116"></a>Derleyici Hatası C3116
'depolama birimi tanımlayıcısı': arabirim yöntemi için geçersiz depolama sınıfı  
  
 Kullanılan `typedef`, `register`, veya `static` arabirim yöntemi için depolama sınıf olarak. Bu depolama sınıfları arabirim üyeleri üzerinde izin verilmez.  
  
 Aşağıdaki örnek C3116 oluşturur:  
  
```  
// C3116.cpp  
__interface ImyInterface  
{  
   static void myFunc();   // C3116  
};  
```