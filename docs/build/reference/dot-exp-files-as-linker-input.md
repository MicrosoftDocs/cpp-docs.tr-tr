---
title: ". Bağlayıcı girişi olarak exp dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- exporting functions
- import libraries, linker files
- linking [C++], exports
- exporting functions, information about exported functions
- exporting data, export (.exp) files
- functions [C++], exporting
- .exp files [C++]
- EXP files
ms.assetid: 399f5636-0a4d-462e-b500-5f5b9ae5ad22
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5cd6351623b230e3be1e432bd6ee0fb760da5abd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="exp-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Exp Dosyaları
Dışarı aktarma (.exp) dosyaları, dışarı aktarılan işlevler ve veri öğeleri hakkında bilgi içerir. LIB içeri aktarma kitaplığı oluşturduğunda, ayrıca bir .exp dosyası oluşturur. Hem verir ve başka bir programda doğrudan veya dolaylı olarak içe aktaran bir program bağladığınızda .exp dosyası kullanın. Bir .exp dosyası ile bağlantı varsa, bağlantı LIB zaten bir oluşturduğunuzu varsayar çünkü bir içeri aktarma kitaplığı üretmez. .Exp dosyaları ve içeri aktarma kitaplıkları hakkında daha fazla ayrıntı için bkz: [içeri aktarma kitaplıkları ve dışarı aktarma dosyalarıyla çalışma](../../build/reference/working-with-import-libraries-and-export-files.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINK giriş dosyaları](../../build/reference/link-input-files.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)