---
title: Önemli hata C1307 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1307
dev_langs:
- C++
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d06ce51ada7cd9159b8e02ff627bf12ebb7293d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227141"
---
# <a name="fatal-error-c1307"></a>Önemli hata C1307
Profil verileri toplanmasından bu yana programı düzenlendi  
  
 Kullanırken [/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), bağlayıcı /LTCG:PGINSTRUMENT sonra derlendiğini bir giriş modülü algılandı ve modül varolan profil verileri olduğu artık ilgili noktasına değiştirildi. Örneğin, arama grafiği derlenmiş modüle değiştirdiyseniz, derleyici C1307 oluşturur.  
  
 Bu hatayı gidermek için /LTCG:PGINSTRUMENT çalıştırın, tüm test çalışmalarını Yinele ve /LTCG:PGOPTIMIZE çalıştırın. /LTCG:PGINSTRUMENT ve Yinele tüm test çalışmalarını çalışmazsa, /LTCG:PGUPDATE /LTCG:PGOPTIMIZE yerine en iyi duruma getirilmiş görüntüsünü oluşturmak için kullanın.