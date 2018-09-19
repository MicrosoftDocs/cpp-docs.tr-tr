---
title: BSCMAKE hatası BK1513 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1513
dev_langs:
- C++
helpviewer_keywords:
- BK1513
ms.assetid: 9ba87c09-8d82-4c80-b0cf-a8de63dcf9da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f68f49ce11c95672abd40ecbaf1873a564a3912e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118810"
---
# <a name="bscmake-error-bk1513"></a>BSCMAKE Hatası BK1513

Artımlı olmayan güncelleştirme tüm gerektirir. SBR dosyaları

Bir veya daha fazla .sbr dosyaları kesildi için yeni bir gözatma bilgisi (.bsc) dosyası BSCMAKE oluşturamaz. Kesilen .sbr dosyaları adlarını bulmak için okuma [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md) bu hata ile birlikte gelen uyarıları.

BSCMAKE .bsc dosyasını bir kesilen .sbr dosyası ile güncelleştirebilir ancak yeni bir derleme başlatılamıyor. BSCMAKE aşağıdaki nedenlerle yeni .bsc dosyası derleme:

- .Bsc dosyası eksik.

- .BSC dosyası için belirtilen yanlış dosya adı.

- Bozuk .bsc dosyası.

Bu sorunu çözmek için kesilen .sbr dosyalarını ve yeniden oluşturun, silin veya çözümü Temizle ve yeniden oluşturun. (IDE'de seçin **derleme**, **çözümü Temizle**ve ardından **derleme**, **çözümü yeniden derle**.)