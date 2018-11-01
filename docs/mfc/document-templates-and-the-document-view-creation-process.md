---
title: Belge şablonları ve belge-görünüm oluşturma işlemi
ms.date: 11/04/2016
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
ms.openlocfilehash: 544a9bf60ee2066688703faa7e430e2337454e66
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606355"
---
# <a name="document-templates-and-the-documentview-creation-process"></a>Belge Şablonları ve Belge/Görünüm Oluşturma İşlemi

Çerçeve karmaşık kendi ilişkili görünümler ve çerçeve penceresi ile belge oluşturma işlemini yönetmek için iki belge şablonu sınıfları kullanır: [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) SDI uygulamaları için ve [CMultiDocTemplate ](../mfc/reference/cmultidoctemplate-class.md) MDI uygulamaları için. A `CSingleDocTemplate` oluşturabilir ve aynı anda tek bir belge depolayabilir. A `CMultiDocTemplate` bir türdeki çok sayıda açık belgelerin listesini tutar.

Bazı uygulamalar birden çok belge türlerini destekler. Örneğin, bir uygulama, metin ve grafikleri belgeler desteklemiyor olabilir. Kullanıcı Dosya menüsündeki yeni komutu seçtiğinde bu tür bir uygulamada, bir iletişim kutusu açmak için olası yeni belge türlerinin bir listesini gösterir. Her bir desteklenen belge türü için ayrı bir belge şablonu nesnesi uygulama kullanır. Aşağıdaki şekil iki belge türlerini destekleyen ve çeşitli açık belgeleri gösteren bir MDI Uygulaması yapılandırmasını gösterir.

![İki belge türleri içeren MDI uygulaması](../mfc/media/vc387h1.gif "vc387h1") iki belge türleri ile bir MDI uygulaması

Belge şablonları oluşturulur ve uygulama nesnesi tarafından korunur. Anahtar görevlerinden birini ve uygulamanızın sırasında gerçekleştirilen `InitInstance` işlev, uygun türde bir veya daha fazla belge şablonları oluşturmak için. Bu özellik anlatıldığı [belge şablonu oluşturma](../mfc/document-template-creation.md). Uygulama nesnesi, şablon listesinde bulunan her bir belge şablonu için bir işaretçi depolar ve şablonların eklemek için bir arabirim sağlar.

İki veya daha fazla belge türlerini desteklemeniz gerekiyorsa, ek bir çağrı eklemeniz gerekir [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) her belge türü için.

Bir simge kendi konumuna belge şablonları uygulama listesinde bağlı her bir belge şablonu için kaydedilir. Belge şablonları sırasını çağrılarıyla eklendiği sıraya göre belirlenir `AddDocTemplate`. MFC uygulamada ilk simge kaynağı uygulama simgesi, sonraki simge kaynağı ilk belge simgesini ve benzeri olduğunu varsayar.

Örneğin, üç uygulama için üçüncü bir belge şablonu olur. Bu simge, uygulama 3 dizinindeki bir simge kaynağı ise belge şablonunu kullanılır. Aksi takdirde dizin 0 konumunda simgesi varsayılan olarak kullanılır.

## <a name="see-also"></a>Ayrıca Bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)<br/>
[Belge Şablonu Oluşturma](../mfc/document-template-creation.md)<br/>
[Belge/görünüm oluşturma](../mfc/document-view-creation.md)<br/>
[FC Nesneleri Arasındaki İlişki](../mfc/relationships-among-mfc-objects.md)<br/>
[Yeni Belgeler, Pencereler ve Görünümler Oluşturma](../mfc/creating-new-documents-windows-and-views.md)

