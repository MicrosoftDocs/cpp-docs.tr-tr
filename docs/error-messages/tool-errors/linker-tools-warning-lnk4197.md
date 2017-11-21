---
title: "Bağlayıcı araçları uyarısı LNK4197 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4197
dev_langs: C++
helpviewer_keywords: LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5977095609dc123866afc39ac610bb0ff9d1619c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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