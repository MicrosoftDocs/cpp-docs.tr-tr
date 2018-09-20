---
title: Belge-görünüm oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0deb187a6540af71a1dc72b730347374bc25f963
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423082"
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

