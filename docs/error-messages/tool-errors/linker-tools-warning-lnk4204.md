---
title: "Bağlayıcı araçları uyarısı LNK4204 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4204
dev_langs: C++
helpviewer_keywords: LNK4204
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 787d9ac2e4f5d18ea905cdf29a73530ff140a206
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4204"></a>Bağlayıcı Araçları Uyarısı LNK4204
hata ayıklama bilgileri modülü başvuran için 'filename' eksik; hata ayıklama bilgileri gibi nesne bağlama  
  
 .Pdb dosyası hatalı bir imza içeriyor. Bağlayıcı, hata ayıklama bilgisi olmadan nesneyi bağlamak devam eder. Nesne kullanarak dosya yeniden derleyin isteyebilirsiniz [/zı](../../build/reference/z7-zi-zi-debug-information-format.md) seçeneği.  
  
 Bazı nesneler Kitaplığı'nda artık bir dosyaya başvuruda bulunuyorsa LNK4204 ortaya çıkabilir. Bu çözüm, yeniden oluştururken örneğin olabilir; bir nesne dosyası silinecek ve derleme hatası nedeniyle yeniden değil. Bu durumda, ya da ile derleme **/Z7**, veya **/Fd**, bir tek dosya başına (yani varsayılan .pdb Dosya adı değil) Kitaplığı'na başvurmak için nesneleri güncelleştirmek için.  Daha fazla bilgi için bkz: [/Fd (Program veritabanı dosya adı)](../../build/reference/fd-program-database-file-name.md).  Kaynak denetim sistemi güncelleştirildiğinde her kitaplıkla .pdb kaydedildiğinden emin olun.