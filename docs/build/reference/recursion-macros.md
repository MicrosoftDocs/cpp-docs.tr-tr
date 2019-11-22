---
title: Özyineleme makroları
description: Özyinelemeli oturumlarda NMAKE 'i çağırmak için kullandığınız makroları açıklar.
ms.date: 11/20/2019
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
no-loc:
- MAKE
- MAKEDIR
- MAKEFLAGS
ms.openlocfilehash: f2bda23cb079e4fd7d12cea3598d33b3625c088d
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303146"
---
# <a name="recursion-macros"></a>Özyineleme makroları

Yineleme makrolarını kullanarak NMAKE 'i yinelemeli olarak çağırın. Özyinelemeli oturumlar komut satırı ve ortam değişkeni makrolarını ve Tools. ini bilgilerini miras alır. Derleme görevleri dosyası tanımlı çıkarımı kurallarını veya `.SUFFIXES` ve `.PRECIOUS` belirtimlerini almayacaktır. Yinelemeli bir NMAKE oturumuna makro geçirmenin üç yolu vardır: özyinelemeli çağrıdan önce bir :::no-loc text="SET"::: komutuyla bir ortam değişkeni ayarlayın. Komutta özyinelemeli çağrı için bir makro tanımlayın. Ya da Tools. ini dosyasında bir makro tanımlayın.

|Makrosu|Tanım|
|-----------|----------------|
|**MAKE**|Komut ilk olarak NMAKE çağırmak için kullanıldı.<br /><br /> `$(MAKE)` makrosu nmake. exe dosyasının tam yolunu verir.|
|**MAKEDIR**|NMAKE çağrıldığında geçerli dizin.|
|**MAKEFLAGS**|Şu anda etkin olan seçenekler. `/$(MAKEFLAGS)`olarak kullanın. **/F** seçeneği dahil değildir.|

## <a name="see-also"></a>Ayrıca bkz.

[Özel NMAKE makroları](special-nmake-macros.md)
