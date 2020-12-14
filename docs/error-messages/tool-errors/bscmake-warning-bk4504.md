---
description: 'Daha fazla bilgi edinin: BSCMAKE Warning BK4504'
title: BSCMAKE Uyarısı BK4504
ms.date: 11/04/2016
f1_keywords:
- BK4504
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
ms.openlocfilehash: 8b07c15b03a040ea19ec368c6f869d02f3e36f79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237835"
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE Uyarısı BK4504

dosya çok fazla başvuru içeriyor; Bu kaynaktan gelen diğer başvurular yoksayılıyor

. Cpp dosyası 64.000 'den fazla sembol başvurusu içeriyor. BSCMAKE bir dosyada 64.000 başvurularıyla karşılaşıldığında, diğer tüm başvuruları yoksayar.

Sorunu düzeltmek için, her biri 64.000 ' den az sembol başvurusuna sahip olan iki veya daha fazla dosyaya ayırın ya da `#pragma component(browser)` belirli başvurular için oluşturulan sembolleri sınırlamak için Önişlemci yönergesini kullanın. Daha fazla bilgi için bkz. [bileşen](../../preprocessor/component.md).
