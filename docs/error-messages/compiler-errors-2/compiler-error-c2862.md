---
title: "Derleyici Hatası C2862 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2862
dev_langs: C++
helpviewer_keywords: C2862
ms.assetid: c04d8499-b799-48a1-9fb4-7902a0b0ac8e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d39cce24f46b8b0ef1ed21ac603feb95684b2f02
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2862"></a>Derleyici Hatası C2862
'arabirimi': Arabirim yalnızca Genel üyeler olabilir  
  
 Korunan ve özel üyeler, yalnızca diğer üye işlevleri erişilen. Bu tür üyeler yok, uygulamaları herhangi bir üyeleri için sağlamayabilir bu yana bir arabirim kullanılıyor.  
  
 Aşağıdaki örnek C2862 üretir:  
  
```  
// C2862.cpp  
// compile with: /c  
#include <unknwn.h>  
  
[object, uuid="60719E20-EF37-11D1-978D-0000F805D73B"]  
__interface IMyInterface {  
   HRESULT mf1(void);   // OK  
protected:  
   HRESULT mf2(int *b);   // C2862  
private:  
   HRESULT mf3(int *c);   // C2862  
};  
```