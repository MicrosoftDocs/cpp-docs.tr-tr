---
title: NMAKE Önemli Hatası U1100
description: Microsoft NMAKE önemli hatası U1100 nedenleri açıklaması.
ms.date: 07/17/2020
f1_keywords:
- U1100
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
ms.openlocfilehash: f908514469a6c9fdb53df3b2bded1b30bddc5a41
ms.sourcegitcommit: 00af3df3331854b23693ee844e5e7c10c8b05a90
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86491394"
---
# <a name="nmake-fatal-error-u1100"></a>NMAKE Önemli Hatası U1100

> '*Macro-* Name ' makrosu, '*kural-adı*' toplu işlem kuralının bağlamında geçersizdir

Bir toplu işlem modu kuralının komut bloğu doğrudan veya dolaylı olarak olmayan özel bir dosya makrosuna başvurduğunda, NMAKE bu hatayı oluşturur `$<` .

`$<`, Batch modu kuralları için tek izin verilen makrodur.

Batch kurallarında NMAKE makroları hakkında daha fazla bilgi için bkz. [özel NMAKE makroları](../../build/reference/special-nmake-macros.md).
