---
title: "Derleyici Uyarısı (düzey 1) C4086 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4086
dev_langs: C++
helpviewer_keywords: C4086
ms.assetid: 9248831b-22bf-47af-8684-bfadb17e94fc
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9d34694f2f991e31ee7a896e128881ff6f09c54d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4086"></a>Derleyici Uyarısı (düzey 1) C4086
'1', '2', '4', ' 8' veya ' 16' olması beklenen pragma parametresi  
  
 Pragma parametresi gerekli değer (1, 2, 4, 8 veya 16) sahip değil.  
  
## <a name="example"></a>Örnek  
  
```  
// C4086.cpp  
// compile with: /W1 /LD  
#pragma pack( 3 ) // C4086  
```