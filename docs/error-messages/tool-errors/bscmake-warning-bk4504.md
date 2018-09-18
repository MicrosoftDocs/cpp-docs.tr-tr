---
title: BSCMAKE uyarısı BK4504 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK4504
dev_langs:
- C++
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c8a2da8903dade37faf3b14175b65f3169efd908
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049780"
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE Uyarısı BK4504

Dosya çok fazla başvuru içeriyor; Bu kaynaktan diğer başvurular yoksayılıyor

.Cpp dosyası birden fazla 64.000 sembol başvurularını içerir. BSCMAKE 64.000 başvuruları bir dosyada karşılaştı, diğer tüm başvurularını yoksayar.

Sorunu düzeltmek için ya da dosyanın ikiye ayırma ya da daha fazla dosya, her biri sahip az 64.000 sembol başvuruları kullanın `#pragma component(browser)` önişlemci yönergesi için belirli başvurular için oluşturulan sınırı semboller. Daha fazla bilgi için [bileşeni](../../preprocessor/component.md).