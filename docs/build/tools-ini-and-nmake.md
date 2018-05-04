---
title: Tools.ini ve NMAKE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 860a334274a3a1a4ac9e11c3e7b5e9a0f136ecc0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="toolsini-and-nmake"></a>Tools.ini ve NMAKE
Derleme görevleri dosyaları, okumadan önce /R kullanılmadığı sürece NMAKE Tools.ini okur. Tools.ini için önce geçerli dizin ve ardından INIT ortam değişkeni tarafından belirtilen dizin görünüyor. NMAKE ayarları başlatma dosyasındaki bölüm ile başlayan `[NMAKE]` ve herhangi bir derleme görevleri dosyası bilgi içerebilir. Sayı işareti ile ayrı satırda başlayan bir açıklama belirtin (#).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE Çalıştırma](../build/running-nmake.md)