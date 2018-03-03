---
title: "Önceden derlenmiş üstbilgi dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdafx.h
dev_langs:
- C++
helpviewer_keywords:
- stdafx.h
- PCH files, file descriptions
- .pch files, file descriptions
- precompiled header files, file descriptions
- stdafx.cpp
ms.assetid: 8228d87a-5609-41f3-9697-b16094c000e5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1208b000f57397764277cc0a43e223f7c781a06e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="precompiled-header-files"></a>Önceden Derlenmiş Üst Bilgi Dosyaları
Bu dosyalar önceden derlenmiş üst bilgi dosyasını oluşturmak için kullanılan *Projname*Stdafx.obj dosya .pch ve önceden derlenmiş türleri.  
  
 Bu dosyalar bulunur *Projname* dizini. Çözüm Gezgini'nde, Stdafx.h üstbilgi dosyaları klasördür ve Stdafx.cpp kaynak dosyaları klasöründe bulunur.  
  
|Dosya adı|Açıklama|  
|---------------|-----------------|  
|Stdafx.h|Bir içerme dosyası olduğu standart sistem dosyaları ve sık kullanılan ancak seyrek değişen dosyaları projeye özgü Ekle.<br /><br /> Tanımlayın veya gerekir stdafx.h _AFX_NO_XXX makrolarındaki hiçbirini tanımsız; Bilgi Bankası makalesi "sorun: sorun _AFX_NO_XXX tanımlarken". MSDN Kitaplığı'nda veya Bilgi Bankası makaleleri bulabilirsiniz [http:// support.microsoft.com/](http://%20support.microsoft.com/).|  
|Stdafx.cpp|Önişlemci yönergeyi içeren `#include "stdafx.h"` ve ekler önceden derlenmiş türleri için dosyaları içerir. Önceden derlenmiş üstbilgi dosyaları dahil olmak üzere herhangi bir türü dosyalarının derleme gerektiren dosyaları kısıtlayarak daha hızlı derleme sürelerini destekler. İlk kez projeniz oluşturulduktan sonra çok daha hızlı kez sonraki sürümlerde önceden derlenmiş üstbilgi dosyaları varlığı nedeniyle yapı fark edeceksiniz.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ projeleri için oluşturulan dosya türleri](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)