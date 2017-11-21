---
title: "Önemli hata C1307 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1307
dev_langs: C++
helpviewer_keywords: C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1173f538f02e8178d523bb51476b4a10427099ea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1307"></a>Önemli hata C1307
Profil verileri toplanmasından bu yana programı düzenlendi  
  
 Kullanırken [/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), bağlayıcı /LTCG:PGINSTRUMENT sonra derlendiğini bir giriş modülü algılandı ve modül varolan profil verileri olduğu artık ilgili noktasına değiştirildi. Örneğin, arama grafiği derlenmiş modüle değiştirdiyseniz, derleyici C1307 oluşturur.  
  
 Bu hatayı gidermek için /LTCG:PGINSTRUMENT çalıştırın, tüm test çalışmalarını Yinele ve /LTCG:PGOPTIMIZE çalıştırın. /LTCG:PGINSTRUMENT ve Yinele tüm test çalışmalarını çalışmazsa, /LTCG:PGUPDATE /LTCG:PGOPTIMIZE yerine en iyi duruma getirilmiş görüntüsünü oluşturmak için kullanın.