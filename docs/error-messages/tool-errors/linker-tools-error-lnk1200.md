---
title: Bağlayıcı araçları hatası LNK1200 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1200
dev_langs:
- C++
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab32939c55dce5e27f907f3d23e639b24741cdc3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1200"></a>Bağlayıcı Araçları Hatası LNK1200
Program Veritabanı 'filename' okunurken hata oluştu  
  
 Program veritabanı (PDB) okunamadı.  
  
 Bu hata, dosya bozulması nedeniyle oluşabilir.  
  
 Varsa `filename` PDB olan bir nesne dosyası için dosya nesnesini kullanarak yeniden derleyin [/zı](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
 Varsa `filename` PDB ana çıktı dosyası için ise ve artımlı bir bağlantı sırasında bu bir hata oluştu, PDB silip yeniden bağla.