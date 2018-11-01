---
title: Tools.ini ve NMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
ms.openlocfilehash: 1a8673741cb49c504855fb1af00dbdc06379210d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654421"
---
# <a name="toolsini-and-nmake"></a>Tools.ini ve NMAKE

Derleme görevleri dosyalarını, okumadan önce /R kullanılmadığı sürece NMAKE Tools.ini okur. Tools.ini için önce geçerli dizinde, ardından INIT ortam değişkeni tarafından belirtilen dizindeki görünüyor. NMAKE ayarlarında başlatma dosyası bölümü ile başlayan `[NMAKE]` ve herhangi bir derleme görevleri dosyası bilgi içerebilir. Sayı işareti ile ayrı satırda başlayan bir açıklama belirtin (#).

## <a name="see-also"></a>Ayrıca Bkz.

[NMAKE Çalıştırma](../build/running-nmake.md)