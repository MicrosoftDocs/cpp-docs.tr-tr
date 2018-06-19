---
title: Bağlayıcı araçları hatası LNK1140 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1140
dev_langs:
- C++
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc0d59589a1882aca4ef2deb419e1e4f1081e52b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302743"
---
# <a name="linker-tools-error-lnk1140"></a>Bağlayıcı Araçları Hatası LNK1140
program veritabanı için çok fazla modülleri; / pdb bağlantısıyla: yok  
  
 Projenin birden fazla 4096 modüller içerir.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümlere kullanarak düzeltmek için  
  
1.  Kullanarak yeniden Bağla [/pdb: hiçbiri](../../build/reference/pdb-use-program-database.md).  
  
2.  Bazı modüller, hata ayıklama bilgisi olmadan derleyin.  
  
3.  Modülleri sayısını azaltın.