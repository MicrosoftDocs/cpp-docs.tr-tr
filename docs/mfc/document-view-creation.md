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
ms.openlocfilehash: 5441827188f5bff98638cc85cd29e2efd79f8ae8
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620335"
---
# <a name="documentview-creation"></a>Belge/Görünüm Oluşturma

Framework, **Dosya** menüsünde **Yeni** ve **Açık** komutların (diğerleri arasında) uygulamalarını sağlar. Yeni bir belge ve onunla ilişkili görünüm ve çerçeve penceresi oluşturma, uygulama nesnesi, belge şablonu, yeni oluşturulan belge ve yeni oluşturulan çerçeve penceresi arasındaki bir yardımcı çaba. Aşağıdaki tabloda hangi nesnelerin ne yaptığını özetlenmektedir.

### <a name="object-creators"></a>Nesne oluşturucuları

|Oluşturucu|Oluşturduğundan|
|-------------|-------------|
|Uygulama nesnesi|Belge şablonu|
|Belge şablonu|Belge|
|Belge şablonu|Çerçeve penceresi|
|Çerçeve penceresi|Görüntüle|

## <a name="see-also"></a>Ayrıca bkz.

[Belge Şablonları ve Belge/Görünüm Oluşturma İşlemi](document-templates-and-the-document-view-creation-process.md)<br/>
[Belge Şablonu Oluşturma](document-template-creation.md)<br/>
[MFC Nesneleri Arasındaki İlişki](relationships-among-mfc-objects.md)<br/>
[Yeni belgeler, pencereler ve görünümler oluşturma](creating-new-documents-windows-and-views.md)
