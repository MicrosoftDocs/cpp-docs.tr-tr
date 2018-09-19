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
ms.openlocfilehash: 65f398dd9885c571ea0d66171889f20d3321a3b9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085868"
---
# <a name="fatal-error-c1307"></a>Önemli hata C1307

Profil verileri toplandıktan sonra program düzenlenmiş

Kullanırken [/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), bağlayıcı sonra /LTCG:PGINSTRUMENT derlendiğini bir giriş modülü algılandı ve modül profil verilerini mevcut olduğu artık ilgili noktasına değiştirildi. Örneğin, çağrı grafı yeniden derlenmiş bir modülde değiştirdiyseniz, derleyici C1307 oluşturur.

Bu hatayı gidermek için /LTCG:PGINSTRUMENT çalıştırın ve tüm test çalışmalarını Yinele /LTCG:PGOPTIMIZE çalıştırın. /LTCG:PGUPDATE yerine /LTCG:PGOPTIMIZE /LTCG:PGINSTRUMENT ve yineleme tüm test çalışmalarını çalıştıramıyorsanız, iyileştirilmiş görüntü oluşturmak için kullanın.