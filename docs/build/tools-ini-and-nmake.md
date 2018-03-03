---
title: Tools.ini ve NMAKE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e4516c3206a08c2b9ee32aea4bbb669ce4cdf0d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="toolsini-and-nmake"></a>Tools.ini ve NMAKE
Derleme görevleri dosyaları, okumadan önce /R kullanılmadığı sürece NMAKE Tools.ini okur. Tools.ini için önce geçerli dizin ve ardından INIT ortam değişkeni tarafından belirtilen dizin görünüyor. NMAKE ayarları başlatma dosyasındaki bölüm ile başlayan `[NMAKE]` ve herhangi bir derleme görevleri dosyası bilgi içerebilir. Sayı işareti ile ayrı satırda başlayan bir açıklama belirtin (#).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE Çalıştırma](../build/running-nmake.md)