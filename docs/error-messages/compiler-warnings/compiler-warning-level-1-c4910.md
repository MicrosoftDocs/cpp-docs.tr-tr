---
title: Derleyici Uyarısı (düzey 1) C4910 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34ed2ec16f579b05a572cf6bfc236cd8d5743f63
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4910"></a>Derleyici Uyarısı (düzey 1) C4910
'\<tanımlayıcısı >': '__declspec(dllexport)' ve 'extern' üzerinde bir açık örnekleme uyumsuz  
  
 Adlı açık şablonu örneklemesi  *\<tanımlayıcısı >* her ikisi için de değiştiren `__declspec(dllexport)` ve `extern` anahtar sözcükler. Ancak, bu anahtar sözcükler karşılıklı olarak birbirini dışlar. `__declspec(dllexport)` Anahtar sözcüğü anlamına gelir şablon sınıfının örneği sırada `extern` anahtar sözcüğü anlamına gelir değil otomatik olarak örneği Şablon sınıfı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açık örnekleme](../../cpp/explicit-instantiation.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)   
 [Genel Kurallar ve Sınırlamalar](../../cpp/general-rules-and-limitations.md)