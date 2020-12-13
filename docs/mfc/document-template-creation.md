---
description: 'Daha fazla bilgi edinin: belge şablonu oluşturma'
title: Belge Şablonu Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- document templates [MFC]
- constructors [MFC], document template
- document templates [MFC], creating
- MFC, document templates
- templates [MFC], document templates
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
ms.openlocfilehash: 60f85cf0a1c16e1aaa6057160c5b986001e18d84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330267"
---
# <a name="document-template-creation"></a>Belge Şablonu Oluşturma

**Dosya** menüsünde **Yeni** veya **Açık** bir komuta yanıt olarak yeni bir belge oluştururken belge şablonu ayrıca belgenin görüntüleneceği yeni bir çerçeve penceresi oluşturur.

Belge şablonu Oluşturucusu, şablonun oluşturabileceğiniz belge, pencere ve görünüm türlerini belirtir. Bu, belge şablonu oluşturucusuna geçirdiğiniz bağımsız değişkenlerle belirlenir. Aşağıdaki kod bir örnek uygulama için [CMultiDocTemplate](reference/cmultidoctemplate-class.md) oluşturmayı gösterir:

[!code-cpp[NVC_MFCDocView#7](codesnippet/cpp/document-template-creation_1.cpp)]

Yeni bir nesne işaretçisi, `CMultiDocTemplate` [AddDocTemplate](reference/cwinapp-class.md#adddoctemplate)bağımsız değişkeni olarak kullanılır. Oluşturucunun bağımsız değişkenleri, `CMultiDocTemplate` belge türü menülerinin ve Hızlandırıcılar ile ilişkili kaynak kimliğini ve [RUNTIME_CLASS](reference/run-time-object-model-services.md#runtime_class) makrosunun üç kullanımını içerir. `RUNTIME_CLASS` bağımsız değişkeni olarak adlandırılan C++ sınıfı için [CRuntimeClass](reference/cruntimeclass-structure.md) nesnesini döndürür. `CRuntimeClass`Belge şablonu oluşturucusuna geçirilen üç nesne, belge oluşturma işlemi sırasında belirtilen sınıfların yeni nesnelerini oluşturmak için gereken bilgileri sağlar. Örnek, nesneleri ekli nesneler oluşturan bir belge şablonu oluşturmayı gösterir `CScribDoc` `CScribView` . Görünümler standart MDI alt çerçeve pencereleri tarafından çerçevelenmiş.

## <a name="see-also"></a>Ayrıca bkz.

[Belge şablonları ve belge/görünüm oluşturma Işlemi](document-templates-and-the-document-view-creation-process.md)<br/>
[Belge/görünüm oluşturma](document-view-creation.md)<br/>
[MFC nesneleri arasındaki ilişkiler](relationships-among-mfc-objects.md)<br/>
[Yeni belgeler, pencereler ve görünümler oluşturma](creating-new-documents-windows-and-views.md)
