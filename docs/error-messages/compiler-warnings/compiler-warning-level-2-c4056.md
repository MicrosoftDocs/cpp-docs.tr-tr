---
title: "Derleyici Uyarısı (Düzey 2) C4056 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4056
dev_langs: C++
helpviewer_keywords: C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7457e1d6e9eeeb2bc4c0f957383e51f258a44120
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4056"></a>Derleyici Uyarısı (Düzey 2) C4056
noktası sabit aritmetik kayan taşması  
  
 Kayan nokta sabit aritmetik izin verilen en büyük değeri aşıyor bir sonuç oluşturur.  
  
 Bu uyarı sürekli aritmetik sırasında gerçekleştirilen derleyici iyileştirmelerini neden olabilir. En iyi duruma getirme etkinleştirdiğinizde uzakta olması durumunda bu uyarıyı yok sayabilirsiniz ([/Od](../../build/reference/od-disable-debug.md)).  
  
 Aşağıdaki örnek C4056 oluşturur:  
  
```  
// C4056.cpp  
// compile with: /W2 /LD  
#pragma warning (default : 4056)  
float fp_val = 1.0e300 * 1.0e300;   // C4056  
```