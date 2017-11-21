---
title: "Bağlayıcı araçları hatası LNK1264 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1264
dev_langs: C++
helpviewer_keywords: LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d58bad22604509546e7f1645b56594653d33b070
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1264"></a>Bağlayıcı Araçları Hatası LNK1264
Belirtilen /LTCG:PGINSTRUMENT ancak gerekli hiçbir kod oluşturma; izleme başarısız oldu  
  
 **/LTCG:PGINSTRUMENT** ile derlendi hiçbir .obj dosyaları bulundu ancak belirtildi [/GL](../../build/reference/gl-whole-program-optimization.md). İzleme yerinde ve bağlantının başarısız alamıyor. Komut satırında ile derlenmiş en az bir .obj dosya olmalıdır **/GL** böylece araçları oluşabilir.  
  
 Profil temelli iyileştirme (PGO) yalnızca 64-bit derleyicileri içinde kullanılabilir.