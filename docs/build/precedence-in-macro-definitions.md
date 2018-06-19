---
title: Makro tanımlarında öncelik | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ce6f0acc898dc719d2252d5cc59dff92bda4a98
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368619"
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