---
title: Makroları Nerede Tanımlamalı
ms.date: 11/04/2016
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
ms.openlocfilehash: 130863f8c5640a0c4915734732d93fc00d3d6479
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656254"
---
# <a name="where-to-define-macros"></a>Makroları Nerede Tanımlamalı

Bir komut satırı, komut dosyası, derleme görevleri dosyası veya Tools.ini dosya makroları tanımlar.

Derleme görevleri dosyası veya Tools.ini dosyanın, her bir makro tanımı ayrı bir satıra görünmesi gerekir ve bir boşluk veya sekme ile başlayamaz. Boşluk veya sekme eşittir işareti etrafında göz ardı edilir. Tüm [dize karakter](../build/defining-an-nmake-macro.md) tırnak işaretleri ve gömülü boşluklar çevreleyen dahil olmak üzere kelimesine yapılmış.

Komut satırını veya komut dosyası, boşluk ve sekme bağımsız değişkenleri sınırlandırmak ve eşittir işaretini çevreleyen olamaz. Varsa `string` boşluk veya sekme, katıştırılmış içeren dize ya da tüm makro çift tırnak işaretleri içine alın ("").

## <a name="see-also"></a>Ayrıca Bkz.

[NMAKE Makrosu Tanımlama](../build/defining-an-nmake-macro.md)