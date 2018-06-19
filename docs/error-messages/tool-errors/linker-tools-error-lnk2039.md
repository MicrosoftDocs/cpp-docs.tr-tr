---
title: Bağlayıcı araçları hatası LNK2039 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2039
dev_langs:
- C++
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 954ea12eb9b49c2bdf59b31a1ec2ec2e66c124ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302103"
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