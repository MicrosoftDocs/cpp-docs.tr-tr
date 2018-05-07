---
title: Bağlayıcı araçları hatası LNK1264 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1264
dev_langs:
- C++
helpviewer_keywords:
- LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ed21327028fc9849f6e0694bb82ae34c6084842
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1264"></a>Bağlayıcı Araçları Hatası LNK1264
Belirtilen /LTCG:PGINSTRUMENT ancak gerekli hiçbir kod oluşturma; izleme başarısız oldu  
  
 **/LTCG:PGINSTRUMENT** ile derlendi hiçbir .obj dosyaları bulundu ancak belirtildi [/GL](../../build/reference/gl-whole-program-optimization.md). İzleme yerinde ve bağlantının başarısız alamıyor. Komut satırında ile derlenmiş en az bir .obj dosya olmalıdır **/GL** böylece araçları oluşabilir.  
  
 Profil temelli iyileştirme (PGO) yalnızca 64-bit derleyicileri içinde kullanılabilir.