---
title: Denetim bayrakları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.flags
dev_langs:
- C++
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 716e597be5d337d11d58df944bbba468e496f078
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078068"
---
# <a name="control-flags"></a>Denetim Bayrakları

Microsoft C çalışma zamanı kitaplığı hata ayıklama sürümünü aşağıdaki bayraklar denetimi yığın ayırma ve raporlama işlemi kullanır. Daha fazla bilgi için [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).

|Bayrağı|Açıklama|
|----------|-----------------|
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|Temel yığın işlevlerin hata ayıklama sürümü karşılıkları eşler.|
|[_DEBUG](../c-runtime-library/debug.md)|Çalışma zamanı işlevlerin hata ayıklama sürümleri kullanılmasına olanak tanır|
|[_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|Hata ayıklama yığını Yöneticisi ayırmaları nasıl izlediği denetler|

Bu bayraklar veya /D komut satırı seçeneği ile tanımlanan bir `#define` yönergesi. Ne zaman bayrağı ile tanımlanan `#define`, üstbilgi dosyasını dahil etmeden önce düzenli bildirimleri deyimi yönergesi yer almalıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[Global Değişkenler ve Standart Türler](../c-runtime-library/global-variables-and-standard-types.md)