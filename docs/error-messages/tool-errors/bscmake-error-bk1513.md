---
title: BSCMAKE hatası BK1513 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1513
dev_langs:
- C++
helpviewer_keywords:
- BK1513
ms.assetid: 9ba87c09-8d82-4c80-b0cf-a8de63dcf9da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93664a1224b85ec808805da0172aec408e875bc9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33295746"
---
# <a name="bscmake-error-bk1513"></a>BSCMAKE Hatası BK1513
nonincremental güncelleştirme tüm gerektirir. SBR dosyaları  
  
 Bir veya daha fazla .sbr dosyaları kesilmiş olduğundan BSCMAKE yeni bir göz atma bilgi (.bsc) dosyası oluşturulamıyor. Kesilmiş .sbr dosyaları adlarını bulmak için okuma [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md) bu hatayı eşlik uyarıları.  
  
 BSCMAKE .bsc dosyasını kesilmiş .sbr dosyası ile güncelleştirebilirsiniz, ancak yeni bir tane oluşturamaz. BSCMAKE aşağıdaki nedenlerle yeni .bsc dosyası derleme:  
  
-   .Bsc dosyası eksik.  
  
-   .BSC dosyası için belirtilen yanlış bir dosya adı.  
  
-   Bozuk .bsc dosyası.  
  
 Bu sorunu gidermek için yeniden oluşturma ve kesilmiş .sbr dosyaları silin veya çözümü temizleyin ve yeniden derleyin. (IDE içinde seçin **yapı**, **temiz çözüm**ve ardından **yapı**, **çözümü yeniden derle**.)