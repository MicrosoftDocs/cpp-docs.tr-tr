---
title: Belge şablonu oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document templates [MFC]
- constructors [MFC], document template
- document templates [MFC], creating
- MFC, document templates
- templates [MFC], document templates
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 36650e0ae1ce042a887c6a87d1bbe62d8b6d7fe4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="document-template-creation"></a>Belge Şablonu Oluşturma
Yanıt olarak yeni bir belge oluştururken, bir `New` veya **açık** komutunu **dosya** menüsünde Belge şablonu da belgeyi görüntülemek üzere aracılığıyla yeni bir çerçeve penceresi oluşturur.  
  
 Belge şablonu Oluşturucusu belgeler, pencereler ve görünümler şablonu oluşturmak için ne tür belirtir. Bu belge şablonu oluşturucuya geçirdiğiniz bağımsız değişkenleri tarafından belirlenir. Aşağıdaki kod oluşturulmasını gösterir bir [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) örnek bir uygulama için:  
  
 [!code-cpp[NVC_MFCDocView#7](../mfc/codesnippet/cpp/document-template-creation_1.cpp)]  
  
 Yeni bir işaretçi `CMultiDocTemplate` nesne bağımsız değişken olarak kullanılan [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate). Bağımsız değişkenleri `CMultiDocTemplate` Oluşturucusu belge tür menüleri ve Hızlandırıcıları ile ilişkili kaynak kimliği içerir ve üç kullanır [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) makrosu. `RUNTIME_CLASS` döndürür [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) bağımsız değişken olarak adlı C++ sınıfı için nesnesi. Üç `CRuntimeClass` belge şablonu oluşturucuya geçirilen nesneleri belge oluşturma işlemi sırasında belirtilen sınıfların yeni nesneler oluşturmak için gerekli bilgileri sağlayın. Örnek oluşturan bir belge şablonu oluşturulmasını gösterir `CScribDoc` nesnelerini `CScribView` iliştirilmiş nesne. Görünümler tarafından standart MDI alt çerçeve pencereleri Çerçeveli.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge şablonları ve belge/görünüm oluşturma işlemi](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Belge/görünüm oluşturma](../mfc/document-view-creation.md)   
 [MFC nesneleri arasındaki ilişki](../mfc/relationships-among-mfc-objects.md)   
 [Yeni Belgeler, Pencereler ve Görünümler Oluşturma](../mfc/creating-new-documents-windows-and-views.md)

