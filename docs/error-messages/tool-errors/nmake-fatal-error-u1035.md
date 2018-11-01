---
title: NMAKE Önemli Hatası U1035
ms.date: 11/04/2016
f1_keywords:
- U1035
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
ms.openlocfilehash: 9c4055bb99243f7d20c1da90aef7b916c46c2749
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589497"
---
# <a name="nmake-fatal-error-u1035"></a>NMAKE Önemli Hatası U1035

sözdizimi hatası: beklenen ':' veya '=' ayracı

Her iki iki nokta (**:**) ya da eşittir işaretini (**=**) bekleniyordu.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Bir iki nokta üst üste bir hedef izleyin değil.

1. Tek harfli hedef ardından, bir virgül ve boşluk (örneğin, c:). NMAKE sürücü belirtimi olarak yorumlanır.

1. Bir iki nokta üst üste çıkarım kuralı izleyin değil.

1. Makro tanımı, bir eşittir işareti izlenmeyen.

1. Bir karakteri ve ardından bir eğik çizgi (**\\**) yeni bir satır komutuna devam etmek için kullanıldı.

1. NMAKE söz dizimi kuralların izleyin değil, bir dize görüntülenmektedir.

1. Derleme görevleri dosyası bir sözcük işlemcisi tarafından biçimlendirildi.