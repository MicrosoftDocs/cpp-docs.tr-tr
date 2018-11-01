---
title: BSCMAKE Uyarısı BK4504
ms.date: 11/04/2016
f1_keywords:
- BK4504
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
ms.openlocfilehash: 7ffcb7c2e6ae512006ccd29c87b05c53fdfcaef5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50450303"
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE Uyarısı BK4504

Dosya çok fazla başvuru içeriyor; Bu kaynaktan diğer başvurular yoksayılıyor

.Cpp dosyası birden fazla 64.000 sembol başvurularını içerir. BSCMAKE 64.000 başvuruları bir dosyada karşılaştı, diğer tüm başvurularını yoksayar.

Sorunu düzeltmek için ya da dosyanın ikiye ayırma ya da daha fazla dosya, her biri sahip az 64.000 sembol başvuruları kullanın `#pragma component(browser)` önişlemci yönergesi için belirli başvurular için oluşturulan sınırı semboller. Daha fazla bilgi için [bileşeni](../../preprocessor/component.md).