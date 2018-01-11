---
title: "Derleyici Uyarısı (düzey 1) C4910 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9f758e2e15d5492724e9b819622202831d4e9f5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4910"></a>Derleyici Uyarısı (düzey 1) C4910
'\<tanımlayıcısı >': '__declspec(dllexport)' ve 'extern' üzerinde bir açık örnekleme uyumsuz  
  
 Adlı açık şablonu örneklemesi  *\<tanımlayıcısı >* her ikisi için de değiştiren `__declspec(dllexport)` ve `extern` anahtar sözcükler. Ancak, bu anahtar sözcükler karşılıklı olarak birbirini dışlar. `__declspec(dllexport)` Anahtar sözcüğü anlamına gelir şablon sınıfının örneği sırada `extern` anahtar sözcüğü anlamına gelir değil otomatik olarak örneği Şablon sınıfı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açık örnekleme](../../cpp/explicit-instantiation.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)   
 [Genel Kurallar ve Sınırlamalar](../../cpp/general-rules-and-limitations.md)