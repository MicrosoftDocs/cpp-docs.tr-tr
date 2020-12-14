---
description: 'Hakkında daha fazla bilgi edinin: denetim bayrakları'
title: Denetim Bayrakları
ms.date: 11/04/2016
f1_keywords:
- c.flags
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
ms.openlocfilehash: 6b49bfa49e2e231a64af8d88739778964ce8ed21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195742"
---
# <a name="control-flags"></a>Denetim Bayrakları

Microsoft C çalışma zamanı kitaplığı 'nın hata ayıklama sürümü, yığın ayırmayı ve raporlama işlemini denetlemek için aşağıdaki bayrakları kullanır. Daha fazla bilgi için bkz. [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).

|Bayrak|Açıklama|
|----------|-----------------|
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|Taban yığın işlevlerini hata ayıklama sürümü karşılıklarına eşler|
|[_DEBUG](../c-runtime-library/debug.md)|Çalışma zamanı işlevlerinin hata ayıklama sürümlerinin kullanımını sağlar|
|[_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|Hata ayıklama yığın yöneticisinin ayırmaları nasıl izlediğini denetler|

Bu bayraklar,/D komut satırı seçeneğiyle veya bir yönergesi ile tanımlanabilir `#define` . Bayrak ile tanımlandığında `#define` , yönerge, Routine bildirimleri için üstbilgi dosyası include ifadesinden önce gelmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Genel değişkenler ve standart türler](../c-runtime-library/global-variables-and-standard-types.md)
