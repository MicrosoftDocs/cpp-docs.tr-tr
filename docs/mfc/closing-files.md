---
title: Dosyaları kapatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97bd910ae4cb514cda07dd319f37a05a32712909
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341032"
---
# <a name="closing-files"></a>Dosyaları Kapatma
Bir dosyayla tamamladıktan sonra her zamanki gibi g/ç işlemlerinde, onu kapatmanız gerekir.  
  
#### <a name="to-close-a-file"></a>Bir dosyayı kapatmak için  
  
1.  Kullanım **Kapat** üye işlevi. Bu işlev, dosya sistemi dosyasını kapatır ve gerekirse arabelleklerini alır.  
  
 Ayırdığınızda [CFile](../mfc/reference/cfile-class.md) çerçeve nesnesinde (gösterilen örnekte olduğu gibi [dosyaları açma](../mfc/opening-files.md)), nesne otomatik olarak ayarlanır kapatılacak ve kapsam dışına çıktığında sonra yok. Bu silme Not `CFile` nesnesi dosya sistemindeki fiziksel dosya silinmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosyalar](../mfc/files-in-mfc.md)

