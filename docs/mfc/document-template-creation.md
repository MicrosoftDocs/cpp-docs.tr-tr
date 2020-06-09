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
ms.openlocfilehash: 952a383792eb3a4d0a4ed1b3e24dd82f7fa644cf
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615795"
---
# <a name="document-template-creation"></a>Belge Şablonu Oluşturma

**Dosya** menüsünde **Yeni** veya **Açık** bir komuta yanıt olarak yeni bir belge oluştururken belge şablonu ayrıca belgenin görüntüleneceği yeni bir çerçeve penceresi oluşturur.

Belge şablonu Oluşturucusu, şablonun oluşturabileceğiniz belge, pencere ve görünüm türlerini belirtir. Bu, belge şablonu oluşturucusuna geçirdiğiniz bağımsız değişkenlerle belirlenir. Aşağıdaki kod bir örnek uygulama için [CMultiDocTemplate](reference/cmultidoctemplate-class.md) oluşturmayı gösterir:

[!code-cpp[NVC_MFCDocView#7](codesnippet/cpp/document-template-creation_1.cpp)]

Yeni bir nesne işaretçisi, `CMultiDocTemplate` [AddDocTemplate](reference/cwinapp-class.md#adddoctemplate)bağımsız değişkeni olarak kullanılır. Oluşturucunun bağımsız değişkenleri, `CMultiDocTemplate` belge türü menülerinin ve Hızlandırıcılar ile ilişkili kaynak kimliğini ve [RUNTIME_CLASS](reference/run-time-object-model-services.md#runtime_class) makrosunun üç kullanımını içerir. `RUNTIME_CLASS`bağımsız değişkeni olarak adlandırılan C++ sınıfı için [CRuntimeClass](reference/cruntimeclass-structure.md) nesnesini döndürür. `CRuntimeClass`Belge şablonu oluşturucusuna geçirilen üç nesne, belge oluşturma işlemi sırasında belirtilen sınıfların yeni nesnelerini oluşturmak için gereken bilgileri sağlar. Örnek, nesneleri ekli nesneler oluşturan bir belge şablonu oluşturmayı gösterir `CScribDoc` `CScribView` . Görünümler standart MDI alt çerçeve pencereleri tarafından çerçevelenmiş.

## <a name="see-also"></a>Ayrıca bkz.

[Belge Şablonları ve Belge/Görünüm Oluşturma İşlemi](document-templates-and-the-document-view-creation-process.md)<br/>
[Belge/görünüm oluşturma](document-view-creation.md)<br/>
[MFC Nesneleri Arasındaki İlişki](relationships-among-mfc-objects.md)<br/>
[Yeni belgeler, pencereler ve görünümler oluşturma](creating-new-documents-windows-and-views.md)
