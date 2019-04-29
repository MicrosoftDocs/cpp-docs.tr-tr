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
ms.openlocfilehash: 7ac5f239ea4d242618fb23ba617a3a6539492053
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344765"
---
# <a name="control-flags"></a>Denetim Bayrakları

Microsoft C çalışma zamanı kitaplığı hata ayıklama sürümünü aşağıdaki bayraklar denetimi yığın ayırma ve raporlama işlemi kullanır. Daha fazla bilgi için [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).

|Bayrağı|Açıklama|
|----------|-----------------|
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|Temel yığın işlevlerin hata ayıklama sürümü karşılıkları eşler.|
|[_DEBUG](../c-runtime-library/debug.md)|Çalışma zamanı işlevlerin hata ayıklama sürümleri kullanılmasına olanak tanır|
|[_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|Hata ayıklama yığını Yöneticisi ayırmaları nasıl izlediği denetler|

Bu bayraklar veya /D komut satırı seçeneği ile tanımlanan bir `#define` yönergesi. Ne zaman bayrağı ile tanımlanan `#define`, üstbilgi dosyasını dahil etmeden önce düzenli bildirimleri deyimi yönergesi yer almalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Global Değişkenler ve Standart Türler](../c-runtime-library/global-variables-and-standard-types.md)
