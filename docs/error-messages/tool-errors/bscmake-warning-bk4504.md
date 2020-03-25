---
title: BSCMAKE Uyarısı BK4504
ms.date: 11/04/2016
f1_keywords:
- BK4504
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
ms.openlocfilehash: 57858827439ac8cc11e3718d7a484124ae8a6d74
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197450"
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE Uyarısı BK4504

dosya çok fazla başvuru içeriyor; Bu kaynaktan gelen diğer başvurular yoksayılıyor

. Cpp dosyası 64.000 'den fazla sembol başvurusu içeriyor. BSCMAKE bir dosyada 64.000 başvurularıyla karşılaşıldığında, diğer tüm başvuruları yoksayar.

Sorunu düzeltmek için, her biri 64.000 ' den az sembol başvurusuna sahip olan iki veya daha fazla dosyaya ayırın ya da belirli başvurular için oluşturulan sembolleri sınırlamak için `#pragma component(browser)` Önişlemci yönergesini kullanın. Daha fazla bilgi için bkz. [bileşen](../../preprocessor/component.md).
