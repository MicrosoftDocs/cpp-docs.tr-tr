---
title: "Önemli hata C1022 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1022
dev_langs: C++
helpviewer_keywords: C1022
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8215a0a505503c9a4040439629aea59926baf27e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1022"></a>Önemli hata C1022
Beklenen #endif  
  
 Bir `#if`, `#ifdef`, veya `#ifndef` yönergesi sahip eşleşen `#endif` yönergesi. Her emin olmanız `#if`, `#ifdef`, veya `#ifndef` eşleşen bir `#endif`.  
  
 Aşağıdaki örnek C1022 oluşturur:  
  
```  
// C1022.cpp  
#define true 1  
  
#if (true)  
#else   
#else    // C1022  
```  
  
 Olası çözüm:  
  
```  
// C1022b.cpp  
// compile with: /c  
#define true 1  
  
#if (true)  
#else   
#endif  
```