---
title: Önemli hata C1307
ms.date: 11/04/2016
f1_keywords:
- C1307
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
ms.openlocfilehash: c7eb90c8e17408f6898ef7ff1a9d9e5efcafb4fa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203352"
---
# <a name="fatal-error-c1307"></a>Önemli hata C1307

profil verileri toplandıktan sonra program düzenlendi

[/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)kullanılırken bağlayıcı,/LTCG: pgınstrumafter ve modülün var olan profil verilerinin artık alakalı olduğu noktaya değiştiği bir giriş modülü algıladı. Örneğin, yeniden derlenen modülde çağrı grafı değiştiyse, derleyici C1307 oluşturacaktır.

Bu hatayı çözmek için/LTCG: PGıNSTRUMRUN, tüm test çalıştırmalarını Yinele ve/LTCG: PGOPTIMIZE ' i çalıştırın. /LTCG: PGıNSTRUMRUN ve tüm test çalıştırmalarını yinelemek istiyorsanız, iyileştirilmiş görüntüyü oluşturmak için/LTCG: PGOPTIMIZE yerine/LTCG: PGUPDATE kullanın.
