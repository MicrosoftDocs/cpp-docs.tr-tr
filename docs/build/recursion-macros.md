---
title: Özyineleme makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f91a5f327686a522608b6eec9fd7106cbab00028
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702046"
---
# <a name="recursion-macros"></a>Özyineleme Makroları

Özyineleme makroları NMAKE yinelemeli olarak çağırmak için kullanın. Komut satırı ve ortam değişkeni makroları ve Tools.ini bilgi özyinelemeli oturumları devralır. Derleme görevleri dosyası tarafından tanımlanan çıkarım kuralları devralmamanızı veya **. SONEKLERİ** ve **. DEĞERLİ** belirtimleri. Bir özyinelemeli NMAKE oturumuna makroları geçirmek için önce Özyinelemeli çağrı KÜMESİYLE bir ortam değişkenini ayarlamak, özyinelemeli çağrı için komutu bir makro tanımlayın veya Tools.ini içinde bir makro tanımlayın.

|Makrosu|Tanım|
|-----------|----------------|
|**OLUN**|NMAKE çağırmak için ilk olarak kullanılan komutu.<br /><br /> $(MAKE) makrosu nmake.exe için tam yolunu sağlar.|
|**MAKEDIR**|NMAKE çağrıldığında geçerli dizin.|
|**MAKEFLAGS**|Seçeneklerinde şu anda etkin. Olarak `/$(MAKEFLAGS)`.  Unutmayın, /F dahil değildir.|

## <a name="see-also"></a>Ayrıca Bkz.

[Özel NMAKE Makroları](../build/special-nmake-macros.md)