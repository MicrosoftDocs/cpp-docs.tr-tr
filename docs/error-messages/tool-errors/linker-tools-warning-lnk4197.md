---
title: Bağlayıcı araçları uyarısı LNK4197 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4197
dev_langs:
- C++
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfef7f0fe2d9cd50fa6a18ad682c3e4d80df99c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4197"></a>Bağlayıcı Araçları Uyarısı LNK4197
Verme 'exportname' birden çok kez belirtildi; ilk belirtimi kullanma  
  
 Bir verme birden çok belirtilen ve farklı yolları. Bağlayıcı ilk belirtimi kullanır ve kalan yok sayar.  
  
 C çalışma zamanı kitaplığı yeniden bu iletiyi yoksayabilirsiniz.  
  
 Bir verme tamamen aynı şekilde birden çok kez belirtilirse, bağlayıcı bir uyarı veremez.  
  
 Örneğin, aşağıdaki .def dosyası içeriğini bu uyarıyı neden olur:  
  
```  
EXPORTS  
   functioname      NONAME  
   functioname      @10  
```  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Aynı verme belirtilen komut satırında her ikisi de (verme aracılığıyla:) ve .def dosyası  
  
2.  Aynı verme iki kez farklı özniteliklerle .def dosyası listelenir.