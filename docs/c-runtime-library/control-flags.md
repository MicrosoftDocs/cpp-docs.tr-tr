---
title: Denetim Bayrakları
ms.date: 11/04/2016
f1_keywords:
- c.flags
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
ms.openlocfilehash: 45349099ed5c607468430d2f0a901c6374d88fc7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475744"
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