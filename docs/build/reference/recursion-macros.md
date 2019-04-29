---
title: Özyineleme Makroları
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
ms.openlocfilehash: 064bc40906bcf3a126c225585a6df43443b5c38e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319245"
---
# <a name="recursion-macros"></a>Özyineleme Makroları

Özyineleme makroları NMAKE yinelemeli olarak çağırmak için kullanın. Komut satırı ve ortam değişkeni makroları ve Tools.ini bilgi özyinelemeli oturumları devralır. Derleme görevleri dosyası tarafından tanımlanan çıkarım kuralları devralmamanızı veya **. SONEKLERİ** ve **. DEĞERLİ** belirtimleri. Bir özyinelemeli NMAKE oturumuna makroları geçirmek için önce Özyinelemeli çağrı KÜMESİYLE bir ortam değişkenini ayarlamak, özyinelemeli çağrı için komutu bir makro tanımlayın veya Tools.ini içinde bir makro tanımlayın.

|Makrosu|Tanım|
|-----------|----------------|
|**OLUN**|NMAKE çağırmak için ilk olarak kullanılan komutu.<br /><br /> $(MAKE) makrosu nmake.exe için tam yolunu sağlar.|
|**MAKEDIR**|NMAKE çağrıldığında geçerli dizin.|
|**MAKEFLAGS**|Seçeneklerinde şu anda etkin. Olarak `/$(MAKEFLAGS)`.  Unutmayın, /F dahil değildir.|

## <a name="see-also"></a>Ayrıca bkz.

[Özel NMAKE Makroları](special-nmake-macros.md)
