---
title: "BSCMAKE hatası BK1513 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK1513
dev_langs: C++
helpviewer_keywords: BK1513
ms.assetid: 9ba87c09-8d82-4c80-b0cf-a8de63dcf9da
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5ec1e317dcd686a76efba8b8ea8e4782246a3a87
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-error-bk1513"></a>BSCMAKE Hatası BK1513
nonincremental güncelleştirme tüm gerektirir. SBR dosyaları  
  
 Bir veya daha fazla .sbr dosyaları kesilmiş olduğundan BSCMAKE yeni bir göz atma bilgi (.bsc) dosyası oluşturulamıyor. Kesilmiş .sbr dosyaları adlarını bulmak için okuma [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md) bu hatayı eşlik uyarıları.  
  
 BSCMAKE .bsc dosyasını kesilmiş .sbr dosyası ile güncelleştirebilirsiniz, ancak yeni bir tane oluşturamaz. BSCMAKE aşağıdaki nedenlerle yeni .bsc dosyası derleme:  
  
-   .Bsc dosyası eksik.  
  
-   .BSC dosyası için belirtilen yanlış bir dosya adı.  
  
-   Bozuk .bsc dosyası.  
  
 Bu sorunu gidermek için yeniden oluşturma ve kesilmiş .sbr dosyaları silin veya çözümü temizleyin ve yeniden derleyin. (IDE içinde seçin **yapı**, **temiz çözüm**ve ardından **yapı**, **çözümü yeniden derle**.)