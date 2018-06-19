---
title: Derleyici Uyarısı (düzey 1 ve 4) C4115 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4115
dev_langs:
- C++
helpviewer_keywords:
- C4115
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2edfdc84ee38e20f7193d720eab0ccb58d30790b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33294199"
---
# <a name="compiler-warning-levels-1-and-4-c4115"></a>Derleyici Uyarısı (düzey 1 ve 4) C4115
'type': tür tanımı parantez içinde adlı  
  
 Belirtilen simge yapısı, UNION veya parantez içinde bir ifade içinde numaralandırılmış türünü tanımlamak için kullanılır. Tanımı kapsamını beklenmeyen olabilir.  
  
 C işlev çağrısında tanımı genel kapsama sahip. Bir C++ çağrısında çağrılan işlev aynı kapsamı tanımı içeriyor.  
  
 Bu uyarı bildirimleri parantez ifadeleri değildir (örneğin, prototipleri) parantez içinde tarafından da neden olabilir.  
  
 Düzey 1 uyarı C++ programları ve ANSI uyumluluğu (/Za) altında derlenmiş C programları ile budur. Aksi takdirde, Düzey 3 olur.