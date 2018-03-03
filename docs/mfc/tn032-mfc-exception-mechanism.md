---
title: "TN032: MFC özel durum mekanizması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.exceptions
dev_langs:
- C++
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bf82d4b158cedd2d8f6916dfb01d26db6c62d83b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tn032-mfc-exception-mechanism"></a>TN032: MFC Özel Durum Mekanizması
Visual C++ önceki sürümlerini desteklemediği standart C++ özel durum mekanizması ve MFC makroları sağlanan **TRY/CATCH/THROW** , bunun yerine kullanıldığını. Bu sürümü Visual C++, C++ özel durumlarını tam olarak destekler. Bu Not önceki makroları Gelişmiş uygulama ayrıntılarını bazıları ele nasıl otomatik olarak temizleme yığını temel nesnelere dahil. C++ özel durum yığını varsayılan olarak geriye doğru izleme desteklemediğinden, bu Teknik Not artık gerekli değildir.  
  
 Başvurmak [özel durumlar: kullanarak MFC makroları ve C++ özel durumlarını](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) MFC makroları ve yeni C++ anahtar sözcükleri arasındaki farklar hakkında daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

