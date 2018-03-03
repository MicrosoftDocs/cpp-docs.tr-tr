---
title: "Önemli hata C1307 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1307
dev_langs:
- C++
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe97f1658a74b0db5985ed755bf387811f2c6d1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1307"></a>Önemli hata C1307
Profil verileri toplanmasından bu yana programı düzenlendi  
  
 Kullanırken [/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), bağlayıcı /LTCG:PGINSTRUMENT sonra derlendiğini bir giriş modülü algılandı ve modül varolan profil verileri olduğu artık ilgili noktasına değiştirildi. Örneğin, arama grafiği derlenmiş modüle değiştirdiyseniz, derleyici C1307 oluşturur.  
  
 Bu hatayı gidermek için /LTCG:PGINSTRUMENT çalıştırın, tüm test çalışmalarını Yinele ve /LTCG:PGOPTIMIZE çalıştırın. /LTCG:PGINSTRUMENT ve Yinele tüm test çalışmalarını çalışmazsa, /LTCG:PGUPDATE /LTCG:PGOPTIMIZE yerine en iyi duruma getirilmiş görüntüsünü oluşturmak için kullanın.