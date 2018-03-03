---
title: "Bağlayıcı araçları hatası LNK1140 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1140
dev_langs:
- C++
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a5a7bce157359d547f91ba2b560cf258e231b4a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1140"></a>Bağlayıcı Araçları Hatası LNK1140
program veritabanı için çok fazla modülleri; / pdb bağlantısıyla: yok  
  
 Projenin birden fazla 4096 modüller içerir.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümlere kullanarak düzeltmek için  
  
1.  Kullanarak yeniden Bağla [/pdb: hiçbiri](../../build/reference/pdb-use-program-database.md).  
  
2.  Bazı modüller, hata ayıklama bilgisi olmadan derleyin.  
  
3.  Modülleri sayısını azaltın.