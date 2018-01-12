---
title: "Derleyici Uyarısı (düzey 1 ve 4) C4115 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4115
dev_langs: C++
helpviewer_keywords: C4115
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ec1c4377c2b7670b9d934d13d09bc5336fe5f30b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-levels-1-and-4-c4115"></a>Derleyici Uyarısı (düzey 1 ve 4) C4115
'type': tür tanımı parantez içinde adlı  
  
 Belirtilen simge yapısı, UNION veya parantez içinde bir ifade içinde numaralandırılmış türünü tanımlamak için kullanılır. Tanımı kapsamını beklenmeyen olabilir.  
  
 C işlev çağrısında tanımı genel kapsama sahip. Bir C++ çağrısında çağrılan işlev aynı kapsamı tanımı içeriyor.  
  
 Bu uyarı bildirimleri parantez ifadeleri değildir (örneğin, prototipleri) parantez içinde tarafından da neden olabilir.  
  
 Düzey 1 uyarı C++ programları ve ANSI uyumluluğu (/Za) altında derlenmiş C programları ile budur. Aksi takdirde, Düzey 3 olur.