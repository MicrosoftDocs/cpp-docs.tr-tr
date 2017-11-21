---
title: "Derleyici Hatası C2007 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2007
dev_langs: C++
helpviewer_keywords: C2007
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7b4cb49426125df28793e7d2b7800198a129db3d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2007"></a>Derleyici Hatası C2007
\#sözdizimi tanımlayın  
  
 Sonra hiçbir tanımlayıcı görünür bir `#define`. Hatayı gidermek için bir tanımlayıcı kullanın.  
  
 Aşağıdaki örnek C2007 oluşturur:  
  
```  
// C2007.cpp  
#define   // C2007  
```  
  
 Olası çözüm:  
  
```  
// C2007b.cpp  
// compile with: /c  
#define true 1  
```