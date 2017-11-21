---
title: "Bağlayıcı araçları hatası LNK1140 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1140
dev_langs: C++
helpviewer_keywords: LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f19c69fad3ac9cc25863bfe8cd4de8100dbf372e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1140"></a>Bağlayıcı Araçları Hatası LNK1140
program veritabanı için çok fazla modülleri; / pdb bağlantısıyla: yok  
  
 Projenin birden fazla 4096 modüller içerir.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümlere kullanarak düzeltmek için  
  
1.  Kullanarak yeniden Bağla [/pdb: hiçbiri](../../build/reference/pdb-use-program-database.md).  
  
2.  Bazı modüller, hata ayıklama bilgisi olmadan derleyin.  
  
3.  Modülleri sayısını azaltın.