---
title: Makroları nerede tanımlamalı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9cf3e87a50362c770d45f00c4dc17ac3d264f611
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380920"
---
# <a name="where-to-define-macros"></a>Makroları Nerede Tanımlamalı
Makrolar, bir komut satırı, komut dosyası, derleme görevleri dosyası veya Tools.ini dosyasında tanımlayın.  
  
 Derleme görevleri dosyası veya Tools.ini dosyasında, her bir makro tanımı ayrı bir satırda görünmesini gerekir ve bir boşluk veya sekme ile başlayamaz. Boşluk veya eşittir işaretinden geçici sekmeleri göz ardı edilir. Tüm [dize karakter](../build/defining-an-nmake-macro.md) çevresindeki tırnak işaretleri ve katıştırılmış boşluklar dahil olmak üzere hazır olan.  
  
 Komut satırı veya komut dosyası, boşluk ve sekme değişkenleri sınırlar ve eşittir işaretinden çevreleyen olamaz. Varsa `string` boşluk veya sekmeler, katıştırılmış içeren dize veya tüm makro çift tırnak işaretleri içine alın ("").  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE Makrosu Tanımlama](../build/defining-an-nmake-macro.md)