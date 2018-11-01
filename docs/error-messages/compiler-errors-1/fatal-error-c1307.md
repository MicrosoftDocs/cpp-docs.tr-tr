---
title: Önemli hata C1307
ms.date: 11/04/2016
f1_keywords:
- C1307
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
ms.openlocfilehash: 1acdda77ac9cbf8d99752de3b78ab9c32bbb4cbc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552275"
---
# <a name="fatal-error-c1307"></a>Önemli hata C1307

Profil verileri toplandıktan sonra program düzenlenmiş

Kullanırken [/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), bağlayıcı sonra /LTCG:PGINSTRUMENT derlendiğini bir giriş modülü algılandı ve modül profil verilerini mevcut olduğu artık ilgili noktasına değiştirildi. Örneğin, çağrı grafı yeniden derlenmiş bir modülde değiştirdiyseniz, derleyici C1307 oluşturur.

Bu hatayı gidermek için /LTCG:PGINSTRUMENT çalıştırın ve tüm test çalışmalarını Yinele /LTCG:PGOPTIMIZE çalıştırın. /LTCG:PGUPDATE yerine /LTCG:PGOPTIMIZE /LTCG:PGINSTRUMENT ve yineleme tüm test çalışmalarını çalıştıramıyorsanız, iyileştirilmiş görüntü oluşturmak için kullanın.