---
title: Belge-görünüm oluşturma
ms.date: 11/04/2016
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
ms.openlocfilehash: eccc65df784d000f8dccc244e295da522658b626
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633568"
---
# <a name="documentview-creation"></a>Belge/Görünüm Oluşturma

Framework uygulamalarında kaynakları **yeni** ve **açık** komutları (diğerlerinin arasında) üzerinde **dosya** menüsü. Yeni bir belge ve ilişkili görünüm ve çerçeve penceresi oluşturma, uygulama nesnesi, bir belge şablonu, yeni oluşturulan belge ve yeni oluşturulan çerçeve penceresi arasında işbirliği yapan bir işlemdir. Aşağıdaki tabloda, hangi nesnelerin ne oluşturma özetlenmektedir.

### <a name="object-creators"></a>Nesne oluşturucuları

|Oluşturucu|Oluşturur|
|-------------|-------------|
|Uygulama nesnesi|Belge şablonu|
|Belge şablonu|Belge|
|Belge şablonu|Çerçeve penceresi|
|Çerçeve penceresi|Görüntüle|

## <a name="see-also"></a>Ayrıca Bkz.

[Belge şablonları ve belge/görünüm oluşturma işlemi](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Belge Şablonu Oluşturma](../mfc/document-template-creation.md)<br/>
[FC Nesneleri Arasındaki İlişki](../mfc/relationships-among-mfc-objects.md)<br/>
[Yeni Belgeler, Pencereler ve Görünümler Oluşturma](../mfc/creating-new-documents-windows-and-views.md)

