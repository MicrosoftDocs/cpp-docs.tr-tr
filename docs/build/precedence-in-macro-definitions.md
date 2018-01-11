---
title: "Makro tanımlarında öncelik | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7421ef51c37e3724bdb986321581e6736a62e18b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="precedence-in-macro-definitions"></a>Makro Tanımlarında Öncelik
Makro birden fazla tanımı varsa, en yüksek öncelik tanımını NMAKE kullanır. Aşağıdaki liste yüksekten en düşüğe öncelik sırasını göstermektedir:  
  
1.  Komut satırında tanımlanan makrosu  
  
2.  Makro derleme görevleri dosyası içinde tanımlanan veya dosya ekleyin  
  
3.  Devralınan bir ortam değişkeni makrosu  
  
4.  Tools.ini dosyasında tanımlanan bir makrosu  
  
5.  Önceden tanımlanmış bir makrosu gibi [CC](../build/command-macros-and-options-macros.md) ve [AS](../build/command-macros-and-options-macros.md)  
  
 Derleme görevleri dosyası makroları aynı adda geçersiz kılmak için ortam değişkenleri devralınan makroları neden /E kullanın. Kullanım **! UNDEF** bir komut satırı geçersiz kılmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE Makrosu Tanımlama](../build/defining-an-nmake-macro.md)