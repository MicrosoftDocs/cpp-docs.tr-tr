---
title: Derleyici Uyarısı (Düzey 2) C4056 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4056
dev_langs:
- C++
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bf5a5855d0b4291105826679e2ae81ed6d69e5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290572"
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