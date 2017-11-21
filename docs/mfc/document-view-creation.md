---
title: "Belge görünüm oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- documents [MFC], creating
- views [MFC], and frame windows
- views [MFC], creating
- tables [MFC]
- MFC, views
- document/view architecture [MFC], creating document/view
- object creators
- MFC, documents
- tables [MFC], objects each MFC object creates
ms.assetid: bda14f41-ed50-439d-af9e-591174e7dd64
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e98f6e4b1b9ecd5848c2701043aa9b0b7dcea7d4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="documentview-creation"></a>Belge/Görünüm Oluşturma
Uygulamaları framework sağlayan `New` ve **açık** komutları (diğerlerinin arasında) üzerinde **dosya** menüsü. Yeni bir belge ve ilişkili görünüm ve çerçeve penceresi oluşturma işbirlikçi çaba uygulama nesnesi, bir belge şablonu, yeni oluşturulan belge ve yeni oluşturulan çerçeve penceresi arasında ' dir. Aşağıdaki tabloda, hangi nesnelerin ne oluşturmak özetler.  
  
### <a name="object-creators"></a>Nesne oluşturucuları  
  
|Oluşturucu|Oluşturur|  
|-------------|-------------|  
|Uygulama nesnesi|Belge şablonu|  
|Belge şablonu|Belge|  
|Belge şablonu|Çerçeve penceresi|  
|Çerçeve penceresi|Görüntüle|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge şablonları ve belge/görünüm oluşturma işlemi](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Belge şablonu oluşturma](../mfc/document-template-creation.md)   
 [MFC nesneleri arasındaki ilişki](../mfc/relationships-among-mfc-objects.md)   
 [Yeni belgeler, pencereler ve görünümler oluşturma](../mfc/creating-new-documents-windows-and-views.md)

