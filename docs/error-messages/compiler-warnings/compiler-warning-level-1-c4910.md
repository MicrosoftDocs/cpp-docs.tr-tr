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
ms.openlocfilehash: f0402e03d77968de3b4c1addf58c481ec85a61b8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4910"></a>Derleyici Uyarısı (düzey 1) C4910
'\<tanımlayıcısı >': '__declspec(dllexport)' ve 'extern' üzerinde bir açık örnekleme uyumsuz  
  
 Adlı açık şablonu örneklemesi  *\<tanımlayıcısı >* her ikisi için de değiştiren `__declspec(dllexport)` ve `extern` anahtar sözcükler. Ancak, bu anahtar sözcükler karşılıklı olarak birbirini dışlar. `__declspec(dllexport)` Anahtar sözcüğü anlamına gelir şablon sınıfının örneği sırada `extern` anahtar sözcüğü anlamına gelir değil otomatik olarak örneği Şablon sınıfı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açık örnekleme](../../cpp/explicit-instantiation.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)   
 [Genel kurallar ve sınırlamalar](../../cpp/general-rules-and-limitations.md)