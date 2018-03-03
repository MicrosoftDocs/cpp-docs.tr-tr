---
title: "Bağlayıcı araçları hatası LNK1200 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1200
dev_langs:
- C++
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 70bf262d4f99c807e3488c1f9b2ed9e73b1eb715
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1200"></a>Bağlayıcı Araçları Hatası LNK1200
Program Veritabanı 'filename' okunurken hata oluştu  
  
 Program veritabanı (PDB) okunamadı.  
  
 Bu hata, dosya bozulması nedeniyle oluşabilir.  
  
 Varsa `filename` PDB olan bir nesne dosyası için dosya nesnesini kullanarak yeniden derleyin [/zı](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
 Varsa `filename` PDB ana çıktı dosyası için ise ve artımlı bir bağlantı sırasında bu bir hata oluştu, PDB silip yeniden bağla.