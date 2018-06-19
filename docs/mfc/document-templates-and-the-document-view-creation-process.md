---
title: Belge şablonları ve belge görünüm oluşturma işlemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- icons, for multiple document templates
- document templates [MFC], and views
- document/view architecture [MFC], creating document/view
- single document template
- MFC, document templates
- multiple document template
- CDocTemplate class [MFC]
- templates [MFC], document templates
ms.assetid: 311ce4cd-fbdf-4ea1-a51b-5bb043abbcee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2d8308e69cf53db4be51f6ce742df41edaa89ea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348097"
---
# <a name="document-templates-and-the-documentview-creation-process"></a>Belge Şablonları ve Belge/Görünüm Oluşturma İşlemi
Belgeler, ilişkili görünümler ve çerçeve pencereleri oluşturma karmaşık işlemini yönetmek için iki belge şablonu sınıfları framework kullanır: [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) SDI uygulamaları için ve [CMultiDocTemplate ](../mfc/reference/cmultidoctemplate-class.md) MDI uygulamaları için. A `CSingleDocTemplate` oluşturabilir ve aynı anda bir türdeki bir belge depolayabilir. A `CMultiDocTemplate` bir tür birçok açık belgelerin listesini tutar.  
  
 Bazı uygulamalar, birden çok belge türü destekler. Örneğin, bir uygulama, metin ve grafik belgeler desteklemiyor olabilir. Kullanıcı yeni bir komut dosyası menüsünde seçtiğinde bu tür bir uygulamada bir iletişim kutusu açmak için olası yeni belge türlerinin bir listesini gösterir. Her desteklenen belge türü için ayrı bir belge şablonu nesnesi uygulama kullanır. Aşağıdaki şekilde iki belge türlerini destekler ve birden fazla açık belgeleri gösterir MDI uygulamanın yapılandırma gösterilmektedir.  
  
 ![İki belge türü olan MDI uygulama](../mfc/media/vc387h1.gif "vc387h1")  
MDI uygulamayla iki belge türü  
  
 Belge şablonları oluşturulur ve uygulama nesnesi tarafından korunur. Anahtar görevlerden birini uygulamanızın sırasında gerçekleştirilen `InitInstance` işlevidir uygun türde bir veya daha fazla belge şablonları oluşturmak için. Bu özellik açıklanan [belge şablonu oluşturma](../mfc/document-template-creation.md). Uygulama nesnesi şablon listesinde bulunan her belge şablonu için bir işaretçi depolar ve belge şablonları eklemek için bir arabirim sağlar.  
  
 İki veya daha fazla belge türü desteklemeniz gerekiyorsa, ek bir çağrı eklemelisiniz [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) her belge türü için.  
  
 Simge kendi konumuna belge şablonları uygulama listesindeki bağlı her belge şablonu için kayıtlı değil. Belge şablonları sırasını çağrıları ile eklenirler sıraya göre belirlenir `AddDocTemplate`. MFC Uygulama ilk simge kaynak uygulama simgesi, sonraki simge kaynak ilk belge simgesi vb. olduğunu varsayar.  
  
 Örneğin, bir belge üç uygulama için üçüncüsü şablonudur. Uygulama 3 dizinindeki bir simge kaynak ise, bu simgeyi belge şablonu için kullanılır. Aksi durumda, dizin 0 konumunda simgesi varsayılan olarak kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel MFC konuları](../mfc/general-mfc-topics.md)   
 [Belge şablonu oluşturma](../mfc/document-template-creation.md)   
 [Belge/görünüm oluşturma](../mfc/document-view-creation.md)   
 [MFC nesneleri arasındaki ilişki](../mfc/relationships-among-mfc-objects.md)   
 [Yeni Belgeler, Pencereler ve Görünümler Oluşturma](../mfc/creating-new-documents-windows-and-views.md)

