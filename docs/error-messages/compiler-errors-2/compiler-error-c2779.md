---
title: "Derleyici Hatası C2779 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2779
dev_langs: C++
helpviewer_keywords: C2779
ms.assetid: 4a00e492-855a-41f3-8a18-5f60ee20c2f2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d0ef3215445e2245229407d41c7592b203cc1f70
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2779"></a>Derleyici Hatası C2779
'bildirimi': özellik yöntemleri yalnızca statik olmayan veri üyeleri ile ilişkili olabilir  
  
 `property` Genişletilmiş öznitelik statik veri üyesi yanlış uygulanır.  
  
 Aşağıdaki örnek C2779 oluşturur:  
  
```  
// C2779.cpp  
struct A {  
   static __declspec(property(put=PutProp))  
   // try the following line instead  
   __declspec(property(put=PutProp))  
      int prop;   // C2779  
   int PutProp(void);  
};  
```