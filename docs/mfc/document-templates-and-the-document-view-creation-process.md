---
title: Belge şablonları ve belge görünümü oluşturma Işlemi
ms.date: 11/19/2018
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
ms.openlocfilehash: b96a11926927e89890ca268dcff7d347079b25fb
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615770"
---
# <a name="document-templates-and-the-documentview-creation-process"></a>Belge Şablonları ve Belge/Görünüm Oluşturma İşlemi

İlişkili görünümleri ve çerçeve pencereleri ile belge oluşturma karmaşık sürecini yönetmek için Framework iki belge şablonu sınıfı kullanır: SDI uygulamaları için [CSingleDocTemplate](reference/csingledoctemplate-class.md) ve MDI uygulamaları Için [CMultiDocTemplate](reference/cmultidoctemplate-class.md) . Tek seferde bir `CSingleDocTemplate` türden bir belge oluşturup depolayabilirler. , `CMultiDocTemplate` Tek bir türdeki birçok açık belge listesini tutar.

Bazı uygulamalar birden çok belge türünü destekler. Örneğin, bir uygulama metin belgelerini ve grafik belgelerini destekleyebilir. Böyle bir uygulamada, Kullanıcı Dosya menüsünde Yeni komutu seçtiğinde bir iletişim kutusu açmak için olası yeni belge türlerinin bir listesini gösterir. Desteklenen her belge türü için, uygulama ayrı bir belge şablonu nesnesi kullanır. Aşağıdaki şekilde, iki belge türünü destekleyen ve çeşitli açık belgeleri gösteren bir MDI uygulamasının yapılandırması gösterilmektedir.

![İki belge türüne sahip MDI uygulaması](../mfc/media/vc387h1.gif "İki belge türüne sahip MDI uygulaması") <br/>
Iki belge türüne sahip bir MDI uygulaması

Belge şablonları, uygulama nesnesi tarafından oluşturulur ve sürdürülür. Uygulamanızın işlevi sırasında gerçekleştirilen anahtar görevlerden biri `InitInstance` , uygun türde bir veya daha fazla belge şablonu oluşturmak. Bu özellik [belge şablonu oluşturma](document-template-creation.md)bölümünde açıklanmaktadır. Uygulama nesnesi, Şablon listesindeki her belge şablonuna yönelik bir işaretçi depolar ve belge şablonları eklemek için bir arabirim sağlar.

İki veya daha fazla belge türünü desteklemeniz gerekiyorsa, her belge türü için [AddDocTemplate](reference/cwinapp-class.md#adddoctemplate) 'e ek bir çağrı eklemeniz gerekir.

Her belge şablonu için, uygulamanın belge şablonları listesindeki konumuna bağlı olarak bir simge kaydedilir. Belge şablonlarının sırası, çağrıları ile eklendikleri sıraya göre belirlenir `AddDocTemplate` . MFC uygulamadaki ilk simge kaynağının uygulama simgesi olduğunu varsayar, sonraki simgenin kaynağı ilk belge simgedir ve bu şekilde devam eder.

Örneğin, bir belge şablonu, uygulamanın üçüncü üç örneğidir. Uygulamada, Dizin 3 ' teki bir simge kaynağı varsa, bu simge belge şablonu için kullanılır. Aksi takdirde, 0 dizinindeki simge varsayılan olarak kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC Konuları](general-mfc-topics.md)<br/>
[Belge Şablonu Oluşturma](document-template-creation.md)<br/>
[Belge/görünüm oluşturma](document-view-creation.md)<br/>
[MFC Nesneleri Arasındaki İlişki](relationships-among-mfc-objects.md)<br/>
[Yeni belgeler, pencereler ve görünümler oluşturma](creating-new-documents-windows-and-views.md)
