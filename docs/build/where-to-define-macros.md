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
ms.openlocfilehash: 29a2899d7dba0b34c0ac3319c253c8056912d883
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713823"
---
# <a name="where-to-define-macros"></a>Makroları Nerede Tanımlamalı

Bir komut satırı, komut dosyası, derleme görevleri dosyası veya Tools.ini dosya makroları tanımlar.

Derleme görevleri dosyası veya Tools.ini dosyanın, her bir makro tanımı ayrı bir satıra görünmesi gerekir ve bir boşluk veya sekme ile başlayamaz. Boşluk veya sekme eşittir işareti etrafında göz ardı edilir. Tüm [dize karakter](../build/defining-an-nmake-macro.md) tırnak işaretleri ve gömülü boşluklar çevreleyen dahil olmak üzere kelimesine yapılmış.

Komut satırını veya komut dosyası, boşluk ve sekme bağımsız değişkenleri sınırlandırmak ve eşittir işaretini çevreleyen olamaz. Varsa `string` boşluk veya sekme, katıştırılmış içeren dize ya da tüm makro çift tırnak işaretleri içine alın ("").

## <a name="see-also"></a>Ayrıca Bkz.

[NMAKE Makrosu Tanımlama](../build/defining-an-nmake-macro.md)