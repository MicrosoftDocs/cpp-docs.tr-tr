---
title: "Birden çok satır içi dosyalar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8bdba2afcc7bc17cb0609e95764b06d83d4cc91e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Derleme görevleri dosyasındaki satır içi dosyalar](../build/inline-files-in-a-makefile.md)