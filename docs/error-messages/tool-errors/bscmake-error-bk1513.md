---
title: BSCMAKE Hatası BK1513
ms.date: 11/04/2016
f1_keywords:
- BK1513
helpviewer_keywords:
- BK1513
ms.assetid: 9ba87c09-8d82-4c80-b0cf-a8de63dcf9da
ms.openlocfilehash: c02e9b47b3d32e4d21914188b96913d6dff03127
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477226"
---
# <a name="bscmake-error-bk1513"></a>BSCMAKE Hatası BK1513

Artımlı olmayan güncelleştirme tüm gerektirir. SBR dosyaları

Bir veya daha fazla .sbr dosyaları kesildi için yeni bir gözatma bilgisi (.bsc) dosyası BSCMAKE oluşturamaz. Kesilen .sbr dosyaları adlarını bulmak için okuma [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md) bu hata ile birlikte gelen uyarıları.

BSCMAKE .bsc dosyasını bir kesilen .sbr dosyası ile güncelleştirebilir ancak yeni bir derleme başlatılamıyor. BSCMAKE aşağıdaki nedenlerle yeni .bsc dosyası derleme:

- .Bsc dosyası eksik.

- .BSC dosyası için belirtilen yanlış dosya adı.

- Bozuk .bsc dosyası.

Bu sorunu çözmek için kesilen .sbr dosyalarını ve yeniden oluşturun, silin veya çözümü Temizle ve yeniden oluşturun. (IDE'de seçin **derleme**, **çözümü Temizle**ve ardından **derleme**, **çözümü yeniden derle**.)