---
description: 'Daha fazla bilgi edinin: belge/görünüm oluşturma'
title: Document-View oluşturma
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
ms.openlocfilehash: 128b68eb53bd596ba2e4b4df4f2c5e865452fe2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326441"
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

[Belge şablonları ve belge/görünüm oluşturma Işlemi](document-templates-and-the-document-view-creation-process.md)<br/>
[Belge şablonu oluşturma](document-template-creation.md)<br/>
[MFC nesneleri arasındaki ilişkiler](relationships-among-mfc-objects.md)<br/>
[Yeni belgeler, pencereler ve görünümler oluşturma](creating-new-documents-windows-and-views.md)
