---
title: Önceden derlenmiş üstbilgi dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4595ea9ce27c40fb798ac050ce456c4d43b2cacb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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