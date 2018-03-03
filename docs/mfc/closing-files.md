---
title: "Dosyaları kapatma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 27b1c59c952b022c7382db7d6b2dcb660cca2e9a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="closing-files"></a>Dosyaları Kapatma
Bir dosyayla tamamladıktan sonra her zamanki gibi g/ç işlemlerinde, onu kapatmanız gerekir.  
  
#### <a name="to-close-a-file"></a>Bir dosyayı kapatmak için  
  
1.  Kullanım **Kapat** üye işlevi. Bu işlev, dosya sistemi dosyasını kapatır ve gerekirse arabelleklerini alır.  
  
 Ayırdığınızda [CFile](../mfc/reference/cfile-class.md) çerçeve nesnesinde (gösterilen örnekte olduğu gibi [dosyaları açma](../mfc/opening-files.md)), nesne otomatik olarak ayarlanır kapatılacak ve kapsam dışına çıktığında sonra yok. Bu silme Not `CFile` nesnesi dosya sistemindeki fiziksel dosya silinmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosyaları](../mfc/files-in-mfc.md)

