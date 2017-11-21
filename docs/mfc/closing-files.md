---
title: "Dosyaları kapatma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3833763394eda3ad64f1c72b80bee4d76785d5a7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="closing-files"></a>Dosyaları Kapatma
Bir dosyayla tamamladıktan sonra her zamanki gibi g/ç işlemlerinde, onu kapatmanız gerekir.  
  
#### <a name="to-close-a-file"></a>Bir dosyayı kapatmak için  
  
1.  Kullanım **Kapat** üye işlevi. Bu işlev, dosya sistemi dosyasını kapatır ve gerekirse arabelleklerini alır.  
  
 Ayırdığınızda [CFile](../mfc/reference/cfile-class.md) çerçeve nesnesinde (gösterilen örnekte olduğu gibi [dosyaları açma](../mfc/opening-files.md)), nesne otomatik olarak ayarlanır kapatılacak ve kapsam dışına çıktığında sonra yok. Bu silme Not `CFile` nesnesi dosya sistemindeki fiziksel dosya silinmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosyaları](../mfc/files-in-mfc.md)

