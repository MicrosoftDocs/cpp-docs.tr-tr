---
title: Derleyici Uyarısı (düzey 1) C4953 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4953
dev_langs:
- C++
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0af5a16ebbf7851eceb2f2cd355f953b14c4bd38
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4953"></a>Derleyici Uyarısı (düzey 1) C4953
Inlinee 'function' profili itibaren kullanılmıyor profil verileri, toplanan veriler, düzenlenebilir  
  
 Kullanırken [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), sonra derlendiğini bir giriş modülü derleyici algıladı `/LTCG:PGINSTRUMENT` ve bir işleve sahiptir (***işlevi***) düzenlenen ve varolan test çalıştığı tanımlanan aday olarak işlev satır içi kullanım. Ancak, bunun sonucunda modülü yeniden derlenmesi işlevi artık aday olmayacaktır satır içi kullanım.  
  
 Bu uyarı, bilgi amaçlıdır. Bu uyarıyı çözümlemek `/LTCG:PGINSTRUMENT`, tüm test yineleme çalıştırır ve Çalıştır `/LTCG:PGOPTIMIZE`.  
  
 Bu uyarı ile bir hata durumunda değiştirilmesi `/LTCG:PGOPTIMIZE` kullanılan.