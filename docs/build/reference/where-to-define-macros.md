---
description: 'Hakkında daha fazla bilgi edinin: makrolar nerede tanımlanır'
title: Makroları Nerede Tanımlamalı
ms.date: 11/04/2016
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
ms.openlocfilehash: b5fc7d6e1fd8247816993929791bf734596d00e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259207"
---
# <a name="where-to-define-macros"></a>Makroları Nerede Tanımlamalı

Makroları bir komut satırı, komut dosyası, derleme görevleri dosyası veya Tools.ini dosyasında tanımlayın.

Derleme görevleri dosyası veya Tools.ini dosyasında, her makro tanımının ayrı bir satırda görünmesi ve boşluk veya sekme ile başlamamalıdır. Eşittir işareti etrafında boşluklar veya sekmeler yok sayılır. Tüm [dize karakterleri](defining-an-nmake-macro.md) , çevreleyen tırnak işaretleri ve gömülü boşluklar da dahil olmak üzere değişmez değerdir.

Bir komut satırında veya komut dosyasında, boşluklar ve sekmeler bağımsız değişkenleri sınırlamaz ve eşittir işaretini çevrelemez. `string`Eklenmiş boşluklar veya sekmeler varsa, dizenin kendisini veya tüm makroyu çift tırnak işaretleri ("") içine alın.

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE makrosu tanımlama](defining-an-nmake-macro.md)
