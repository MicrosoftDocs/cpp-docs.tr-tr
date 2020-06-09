---
title: Belge Çerçeve Pencereleri Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], creating
- document templates [MFC], and document frame windows
- windows [MFC], creating
- runtime, class information
- run-time class [MFC], and document frame window creation
- document frame windows [MFC], creating
- MFC, frame windows
ms.assetid: 8671e239-b76f-4dea-afa8-7024e6e58ff5
ms.openlocfilehash: e15a2a6bc016bf23bc0decf529b4c3ffeecc3a4c
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621957"
---
# <a name="creating-document-frame-windows"></a>Belge Çerçeve Pencereleri Oluşturma

[Belge/görünüm oluşturma](document-view-creation.md) , [CDocTemplate](reference/cdoctemplate-class.md) nesnesinin çerçeve penceresi, belge ve görüntüleme ve bunların tümünü birlikte nasıl oluşturup birbirine bağlama şeklini gösterir. Oluşturucuya yapılan üç [CRuntimeClass](reference/cruntimeclass-structure.md) bağımsız değişkeni, `CDocTemplate` belge şablonunun Dosya menüsündeki yeni komut veya bir MDI Pencere menüsünde yeni pencere komutu gibi Kullanıcı komutlarına yanıt olarak dinamik olarak oluşturduğu çerçeve penceresini, belge ve görünüm sınıflarını belirler. Belge şablonu, bir görünüm ve belge için bir çerçeve penceresi oluşturduğunda bu bilgileri daha sonra kullanmak üzere depolar.

[RUNTIME_CLASS](reference/run-time-object-model-services.md#runtime_class) mekanizmanın doğru çalışması için, türetilmiş çerçeve pencere sınıflarınız [DECLARE_DYNCREATE](reference/run-time-object-model-services.md#declare_dyncreate) makroyla bildirilmelidir. Bunun nedeni, Framework 'ün sınıfının dinamik oluşturma mekanizmasını kullanarak belge çerçevesi pencerelerini oluşturması gereksinimidir `CObject` .

Kullanıcı bir belge oluşturan bir komut seçtiğinde, çerçeve belge şablonunu, görünümünü ve görünümünü görüntüleyen çerçeve penceresini oluşturmak için belge şablonu üzerinde çağırır. Belge çerçevesi penceresi oluşturduğunda, belge şablonu bir SDI uygulaması için [CFrameWnd](reference/cframewnd-class.md) 'den türetilmiş bir sınıf veya bir MDI uygulaması Için [Cmdictepdwnd](reference/cmdichildwnd-class.md) öğesinden bir nesne oluşturur. Daha sonra Framework, kaynaklardan oluşturma bilgilerini almak ve Windows penceresini oluşturmak için çerçeve pencere nesnesinin [LoadFrame](reference/cframewnd-class.md#loadframe) üye işlevini çağırır. Framework pencere tanıtıcısını çerçeve pencere nesnesine iliştirir. Ardından, görünümü belge çerçevesi penceresinin alt penceresi olarak oluşturur.

Türetilmiş nesnenizin [ne zaman başlatılacağını seçerken](when-to-initialize-cwnd-objects.md) dikkatli olun `CWnd` .

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [CObject 'ten sınıf türetme (dinamik oluşturma mekanizması)](deriving-a-class-from-cobject.md)

- [Belge/görünüm oluşturma (Şablonlar ve çerçeve penceresi oluşturma)](document-view-creation.md)

- [Çerçeve pencerelerini yok etme](destroying-frame-windows.md)

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve pencerelerini kullanma](using-frame-windows.md)
