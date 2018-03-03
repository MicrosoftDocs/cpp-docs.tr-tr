---
title: "Birden çok satır içi dosyalar | Microsoft Docs"
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
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 412c68f4d1279fea7969b3ddfdd2bf82e3cdbc47
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="multiple-inline-files"></a>Birden Çok Satır İçi Dosya
Bir komutu, birden fazla satır içi dosya oluşturabilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      command << <<  
inlinetext  
<<[KEEP | NOKEEP]  
inlinetext  
<<[KEEP | NOKEEP]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Her dosya için satır içi metin sınırlayıcısı içeren bir kapanış satırı tarafından izlenen bir veya daha fazla satırı belirtin. İlk dosya sınırlandırma çizgi aşağıdaki satırda ikinci dosyanın metni başlayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme Görevleri Dosyasındaki Satır İçi Dosyalar](../build/inline-files-in-a-makefile.md)