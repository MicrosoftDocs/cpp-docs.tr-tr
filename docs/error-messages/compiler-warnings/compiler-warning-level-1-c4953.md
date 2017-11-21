---
title: "Derleyici Uyarısı (düzey 1) C4953 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4953
dev_langs: C++
helpviewer_keywords: C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 807e091838db20fdcf66a74fe3050cf192fab1e3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4953"></a>Derleyici Uyarısı (düzey 1) C4953
Inlinee 'function' profili itibaren kullanılmıyor profil verileri, toplanan veriler, düzenlenebilir  
  
 Kullanırken [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), sonra derlendiğini bir giriş modülü derleyici algıladı `/LTCG:PGINSTRUMENT` ve bir işleve sahiptir (***işlevi***) düzenlenen ve varolan test çalıştığı tanımlanan aday olarak işlev satır içi kullanım. Ancak, bunun sonucunda modülü yeniden derlenmesi işlevi artık aday olmayacaktır satır içi kullanım.  
  
 Bu uyarı, bilgi amaçlıdır. Bu uyarıyı çözümlemek `/LTCG:PGINSTRUMENT`, tüm test yineleme çalıştırır ve Çalıştır `/LTCG:PGOPTIMIZE`.  
  
 Bu uyarı ile bir hata durumunda değiştirilmesi `/LTCG:PGOPTIMIZE` kullanılan.