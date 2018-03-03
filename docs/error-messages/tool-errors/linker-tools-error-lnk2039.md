---
title: "Bağlayıcı araçları hatası LNK2039 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2039
dev_langs:
- C++
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 441765d85ce65a80102ed94b3f4394ae48c0e29f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2039"></a>Bağlayıcı Araçları Hatası LNK2039
ref sınıfı alma\<türü >' another.obj içinde tanımlanan; içeri aktarılan veya tanımlı, ancak her ikisi de olması gerekir  
  
 Ref sınıfı ' <`type`>' belirtilen .obj dosyasında alınır ancak de başka bir .obj dosyasında belirtilir. Bu durum, çalışma zamanı hatası veya başka beklenmeyen davranışlara neden olabilir.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Denetleme olup olmadığını '`type`' diğer .obj dosyasında tanımlanmış olması gerekir ve bunu .winmd dosyasından içe aktarılması gerekir olup olmadığını denetleyin.  
  
2.  Tanımı veya içeri aktarma kaldırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı araçları hataları ve Uyarıları](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)   
 [Bağlayıcı Araçları Hatası LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)