---
title: "Derleyici Uyarısı (Düzey 2) C4056 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4056
dev_langs:
- C++
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 78b95111e69cdb8b27e65654fbf64756786d2097
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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