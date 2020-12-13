---
description: 'Daha fazla bilgi edinin: önemli hata C1307'
title: Önemli hata C1307
ms.date: 11/04/2016
f1_keywords:
- C1307
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
ms.openlocfilehash: 235d51f272669ba3b205eea5c3703b40dc1e9077
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177893"
---
# <a name="fatal-error-c1307"></a>Önemli hata C1307

profil verileri toplandıktan sonra program düzenlendi

[/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)kullanılırken bağlayıcı,/LTCG: pgınstrumafter ve modülün var olan profil verilerinin artık alakalı olduğu noktaya değiştiği bir giriş modülü algıladı. Örneğin, yeniden derlenen modülde çağrı grafı değiştiyse, derleyici C1307 oluşturacaktır.

Bu hatayı çözmek için/LTCG: PGıNSTRUMRUN, tüm test çalıştırmalarını Yinele ve/LTCG: PGOPTIMIZE ' i çalıştırın. /LTCG: PGıNSTRUMRUN ve tüm test çalıştırmalarını yinelemek istiyorsanız, iyileştirilmiş görüntüyü oluşturmak için/LTCG: PGOPTIMIZE yerine/LTCG: PGUPDATE kullanın.
