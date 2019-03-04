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
ms.openlocfilehash: 66a951994a75cbd99debeb2c6511739411cdd470
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57266004"
---
# <a name="creating-document-frame-windows"></a>Belge Çerçeve Pencereleri Oluşturma

[Belge/görünüm oluşturma](../mfc/document-view-creation.md) gösterir nasıl [CDocTemplate](../mfc/reference/cdoctemplate-class.md) çerçeve penceresi, belge ve görünüm oluşturma ve bunları tüm birbirine bağlama nesnesi düzenler. Üç [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) bağımsız değişkenleri `CDocTemplate` Oluşturucusu belirtin çerçeve penceresi, belge ve görünüm sınıfları, belge şablonunu yanıt olarak yeni dosya komutu gibi kullanıcı komutları dinamik olarak oluşturur. menü veya bir MDI Pencere menüsünden Yeni bir pencere komutu. Bir görünümü ve belge çerçeve penceresi oluşturduğunda, belge şablonunu bu bilgiler daha sonra kullanmak için depolar.

İçin [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) mekanizması düzgün türetilmiş çalışmaya çerçeve penceresi sınıfları ile bildirilmelidir [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) makrosu. Belge çerçeve pencereleri sınıfın dinamik oluşturma mekanizması kullanarak oluşturmak framework gerekli olmasıdır `CObject`.

Kullanıcı bir belgeyi oluşturur bir komutu seçtiğinde framework görünümde görüntülenecek çerçeve penceresi belge nesnesi ve onun görünümü oluşturmak için belge şablonunu çağırır. Belge çerçeve penceresi oluşturur, belge şablonunu uygun sınıfın bir nesnesi oluşturur — öğesinden türetilmiş bir sınıf [CFrameWnd](../mfc/reference/cframewnd-class.md) bir SDI uygulaması veya gelen [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md) MDI için uygulama. Framework ardından çerçeve pencere çağıran [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) kaynaklardan oluşturma bilgileri edinin ve Windows penceresi oluşturmak için üye işlevi. Çerçeve pencere tanıtıcısı çerçeve pencere nesnesine iliştirir. Ardından belge çerçevesi penceresinin alt pencere olarak görünümü oluşturur.

Karar dikkatli olun [başlatılacağı zaman](../mfc/when-to-initialize-cwnd-objects.md) , `CWnd`-türetilmiş bir nesneye.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [(Kendi dinamik oluşturma mekanizması) CObject'ten sınıf türetme](../mfc/deriving-a-class-from-cobject.md)

- [Belge/görünüm oluşturma (şablon ve çerçeve penceresi oluşturma)](../mfc/document-view-creation.md)

- [Çerçeve pencerelerini yok etme](../mfc/destroying-frame-windows.md)

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve Pencerelerini Kullanma](../mfc/using-frame-windows.md)
