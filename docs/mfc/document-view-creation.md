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
ms.workload: cplusplus
ms.openlocfilehash: c6997189f23ea7599dde0a1b19ba9f0ea350378d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Yeni Belgeler, Pencereler ve Görünümler Oluşturma](../mfc/creating-new-documents-windows-and-views.md)

