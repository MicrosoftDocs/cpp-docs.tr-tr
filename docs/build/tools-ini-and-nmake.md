---
title: Tools.ini ve NMAKE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 638132f640fd342a752ec45541275178f6f26692
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="toolsini-and-nmake"></a>Tools.ini ve NMAKE
Derleme görevleri dosyaları, okumadan önce /R kullanılmadığı sürece NMAKE Tools.ini okur. Tools.ini için önce geçerli dizin ve ardından INIT ortam değişkeni tarafından belirtilen dizin görünüyor. NMAKE ayarları başlatma dosyasındaki bölüm ile başlayan `[NMAKE]` ve herhangi bir derleme görevleri dosyası bilgi içerebilir. Sayı işareti ile ayrı satırda başlayan bir açıklama belirtin (#).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE çalıştırma](../build/running-nmake.md)