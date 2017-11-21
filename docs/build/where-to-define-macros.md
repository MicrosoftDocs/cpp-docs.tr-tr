---
title: "Makroları nerede tanımlamalı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cfb17f531df5c232f1f376cd003acb7bf5a62206
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="where-to-define-macros"></a>Makroları Nerede Tanımlamalı
Makrolar, bir komut satırı, komut dosyası, derleme görevleri dosyası veya Tools.ini dosyasında tanımlayın.  
  
 Derleme görevleri dosyası veya Tools.ini dosyasında, her bir makro tanımı ayrı bir satırda görünmesini gerekir ve bir boşluk veya sekme ile başlayamaz. Boşluk veya eşittir işaretinden geçici sekmeleri göz ardı edilir. Tüm [dize karakter](../build/defining-an-nmake-macro.md) çevresindeki tırnak işaretleri ve katıştırılmış boşluklar dahil olmak üzere hazır olan.  
  
 Komut satırı veya komut dosyası, boşluk ve sekme değişkenleri sınırlar ve eşittir işaretinden çevreleyen olamaz. Varsa `string` boşluk veya sekmeler, katıştırılmış içeren dize veya tüm makro çift tırnak işaretleri içine alın ("").  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE makrosu tanımlama](../build/defining-an-nmake-macro.md)