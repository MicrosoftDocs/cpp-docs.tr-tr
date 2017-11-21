---
title: "Derleyici Hatası C2238 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2238
dev_langs: C++
helpviewer_keywords: C2238
ms.assetid: 3d53060c-d6b7-4603-b9cf-d7c65eb64cd2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0fbf1b4d416a72d1836ac5a69f5106f84c6db1c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2238"></a>Derleyici Hatası C2238
'belirteci' önceki beklenmeyen belirteçleri  
  
 Yanlış bir belirteç bulundu.  
  
 Aşağıdaki örnek C2238 oluşturur:  
  
```  
// C2238.cpp  
// compile with: /c  
class v {  
virtual: int vvv;   // C2238  
};  
```