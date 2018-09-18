---
title: Bağlayıcı araçları hatası LNK1201 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1201
dev_langs:
- C++
helpviewer_keywords:
- LNK1201
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c133748f95846160e1387e31e023d9ce459b281
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055282"
---
# <a name="linker-tools-error-lnk1201"></a>Bağlayıcı Araçları Hatası LNK1201

'filename'; program veritabanına yazılırken hata oluştu yetersiz disk alanı, geçersiz bir yol veya yetersiz ayrıcalık denetimi

Çıkış dosyası için program veritabanı (PDB) bağlantı yazılamadı.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Dosya bozuk olabilir. Yeniden Bağla ve PDB dosyasını silin.

1. Dosya yazmak için yeterli disk alanı.

1. Sürücü, büyük olasılıkla bir ağ sorunu nedeniyle kullanılabilir değil.

1. Hata ayıklayıcı bağlantı oluşturmaya çalıştığınız programın etkin değil.

1. Yığın alanı kalmadı.  Bkz: [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) daha fazla bilgi için.