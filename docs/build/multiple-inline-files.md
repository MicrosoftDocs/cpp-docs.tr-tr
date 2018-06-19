---
title: Birden çok satır içi dosyalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ee9be15f029c0aaab3ca4bc47fb183e1499c2e2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368219"
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