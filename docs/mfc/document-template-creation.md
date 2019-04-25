---
title: Belge Şablonu Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- document templates [MFC]
- constructors [MFC], document template
- document templates [MFC], creating
- MFC, document templates
- templates [MFC], document templates
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
ms.openlocfilehash: 85ff6ad47b37d85c812608dbee918f0543730eae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219814"
---
# <a name="document-template-creation"></a>Belge Şablonu Oluşturma

Yanıt olarak yeni bir belge oluştururken bir **yeni** veya **açık** komutunu **dosya** menüsünde, belge şablonunu da görüntülemek, yeni bir çerçeve penceresi oluşturur Belge.

Belge şablonu Oluşturucu, belgeler, pencereler ve görünümler şablonu oluşturmak için hangi türlerini belirtir. Bu belge şablonu oluşturucusuna geçirmeniz bağımsız değişkenleri tarafından belirlenir. Aşağıdaki kod oluşturulmasını gösterir. bir [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) örnek bir uygulama için:

[!code-cpp[NVC_MFCDocView#7](../mfc/codesnippet/cpp/document-template-creation_1.cpp)]

Yeni bir işaretçi `CMultiDocTemplate` nesnesi bağımsız değişkeni olarak kullanılır [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate). Bağımsız değişkenleri `CMultiDocTemplate` Oluşturucusu belge türün menülerini ve Hızlandırıcı ile ilişkili kaynak Kimliğini içerir ve üç kullanır [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) makrosu. `RUNTIME_CLASS` döndürür [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) bağımsız değişken olarak adlandırılan C++ sınıfı için nesne. Üç `CRuntimeClass` belge şablonu oluşturucuya geçirilen nesneleri belge oluşturma işlemi sırasında belirtilen sınıfların yeni nesneler oluşturmak için gerekli bilgileri sağlayın. Örnek, oluşturur bir belge şablonu oluşturulmasını gösterir. `CScribDoc` nesnelerini `CScribView` bağlı nesneler. Görünümler, standart MDI alt çerçeve pencereleri tarafından çerçevelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Belge şablonları ve belge/görünüm oluşturma işlemi](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Belge/görünüm oluşturma](../mfc/document-view-creation.md)<br/>
[FC Nesneleri Arasındaki İlişki](../mfc/relationships-among-mfc-objects.md)<br/>
[Yeni Belgeler, Pencereler ve Görünümler Oluşturma](../mfc/creating-new-documents-windows-and-views.md)
