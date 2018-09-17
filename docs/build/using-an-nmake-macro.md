---
title: NMAKE makrosu kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0b68a5f3128b5d3780895f8080411819ed9b538
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712601"
---
# <a name="using-an-nmake-macro"></a>NMAKE Makrosu Kullanma

Makro kullanmak için aşağıdaki gibi bir dolar işareti ($) tarafından öncesinde parantez içine adını alın.

## <a name="syntax"></a>Sözdizimi

```
$(macroname)
```

## <a name="remarks"></a>Açıklamalar

Boşluk olmayan izin verilir. Parantezler isteğe bağlıdır, *makroadı* tek bir karakterdir. Tanımı dize $ değiştirir (*makroadı*); tanımlanmamış bir makro boş bir dize ile değiştirilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

[Makro değiştirme](../build/macro-substitution.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Makrolar ve NMAKE](../build/macros-and-nmake.md)