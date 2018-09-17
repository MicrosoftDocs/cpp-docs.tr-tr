---
title: Boş ve tanımlanmamış makrolar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, undefined macros
- Null macros in NMAKE
- macros, null and undefined
- undefined macros and NMAKE
- NMAKE program, null macros
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eee6e713715e4709af990878224261a41f5470e3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702643"
---
# <a name="null-and-undefined-macros"></a>Boş ve Tanımlanmamış Makrolar

Null dizeler için null ve tanımlanmamış makrolar genişletin, ancak boş bir dize olarak tanımlanmış bir makro ifadeleri önişlemde tanımlı olarak kabul edilir. Makro boş bir dize tanımlamak için herhangi bir karakter boşluk veya sekme sonra hariç eşittir (=) bir komut satırı veya komut dosyası ve boş bir dize veya tanımı çift tırnak işaretleri içine alın belirtin (""). Makro tanımını kaldırmaya kullanın **! UNDEF.** Daha fazla bilgi için [derleme görevleri dosyası önişleme yönergeleri](../build/makefile-preprocessing-directives.md).

## <a name="see-also"></a>Ayrıca Bkz.

[NMAKE Makrosu Tanımlama](../build/defining-an-nmake-macro.md)