---
title: Makroları nerede tanımlamalı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2e646de4cf67fc249d69fb07789f4c8a3e14bf0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="where-to-define-macros"></a>Makroları Nerede Tanımlamalı
Makrolar, bir komut satırı, komut dosyası, derleme görevleri dosyası veya Tools.ini dosyasında tanımlayın.  
  
 Derleme görevleri dosyası veya Tools.ini dosyasında, her bir makro tanımı ayrı bir satırda görünmesini gerekir ve bir boşluk veya sekme ile başlayamaz. Boşluk veya eşittir işaretinden geçici sekmeleri göz ardı edilir. Tüm [dize karakter](../build/defining-an-nmake-macro.md) çevresindeki tırnak işaretleri ve katıştırılmış boşluklar dahil olmak üzere hazır olan.  
  
 Komut satırı veya komut dosyası, boşluk ve sekme değişkenleri sınırlar ve eşittir işaretinden çevreleyen olamaz. Varsa `string` boşluk veya sekmeler, katıştırılmış içeren dize veya tüm makro çift tırnak işaretleri içine alın ("").  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE Makrosu Tanımlama](../build/defining-an-nmake-macro.md)