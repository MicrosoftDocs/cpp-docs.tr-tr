---
title: "Derleyici Uyarısı (düzey 1) C4109 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4109
dev_langs: C++
helpviewer_keywords: C4109
ms.assetid: 9e8d95c6-e05d-47e0-bd87-78974b3cc06c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8efbf042901c484606a5fb8303acf2c08e20ace0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4109"></a>Derleyici Uyarısı (düzey 1) C4109
Beklenmeyen tanımlayıcı 'tanımlayıcısı'  
  
 Beklenmeyen tanımlayıcısını içeren pragma göz ardı edilir.  
  
## <a name="example"></a>Örnek  
  
```  
// C4109.cpp  
// compile with: /W1 /LD  
#pragma init_seg( abc ) // C4109  
```