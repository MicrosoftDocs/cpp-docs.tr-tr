---
description: 'Daha fazla bilgi edinin: BSCMAKE hatası BK1513'
title: BSCMAKE Hatası BK1513
ms.date: 11/04/2016
f1_keywords:
- BK1513
helpviewer_keywords:
- BK1513
ms.assetid: 9ba87c09-8d82-4c80-b0cf-a8de63dcf9da
ms.openlocfilehash: bdf26e3268f98e5ab41ef27bbeaa3734a001671a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238095"
---
# <a name="bscmake-error-bk1513"></a>BSCMAKE Hatası BK1513

Artımlı olmayan güncelleştirme için tümü gereklidir. SBR dosyaları

BSCMAKE bir veya daha fazla. sbr dosyası kesildiği için yeni bir tarama bilgisi (. bsc) dosyası oluşturamıyor. Kesilen. sbr dosyalarının adlarını bulmak için, bu hataya eşlik eden [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md) uyarılarını okuyun.

BSCMAKE, bir. bsc dosyasını kesilmiş. sbr dosyasıyla güncelleştirebilir, ancak yeni bir tane derlenemez. BSCMAKE, aşağıdaki nedenlerden dolayı yeni bir. bsc dosyası oluşturabilir:

- Eksik. bsc dosyası.

- . Bsc dosyası için yanlış dosya adı belirtildi.

- Bozuk. bsc dosyası.

Bu sorunu çözmek için kesilen. sbr dosyalarını silip yeniden oluşturun veya çözümü temizleyip yeniden derleyin. (IDE 'de **Oluştur**, **Çözümü Temizle**' yi seçin ve sonra **Derle**, **çözümü yeniden derle**' yi seçin.)
