---
title: "Pano: Veri kopyalama ve yapıştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Clipboard, copying data to
- Clipboard, pasting
ms.assetid: 580e10be-241f-4f9f-94cf-8302edc5beef
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d76be3bd3863826391cc812f17dca88cb3a5457
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="clipboard-copying-and-pasting-data"></a>Pano: Veri Kopyalama ve Yapıştırma
Bu konu, kopyalama ve OLE uygulamanızda panodan yapıştırma uygulanması için gerekli en düşük iş açıklar. Okumanız önerilir [veri nesneleri ve veri kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md) devam etmeden önce konuları.  
  
 Kopyalama veya yapıştırarak uygulamadan önce kopyalama, kesme ve yapıştırma seçenekleri Düzen menüsünde işlemek için işlevleri sağlamanız gerekir.  
  
##  <a name="_core_copying_or_cutting_data"></a>Kopyalama veya kesme verileri  
  
#### <a name="to-copy-data-to-the-clipboard"></a>Verileri panoya kopyalamak için  
  
1.  Kopyalanacak verileri yerel veriler katıştırılmış veya bağlantılı bir öğe olup olmadığını belirlemek.  
  
    -   Veri katıştırılmış ya da bağlantılı bir işaretçi elde `COleClientItem` seçilmiş nesnesi.  
  
    -   Verileri yerel ve uygulamayı bir sunucu ise, türetilen yeni nesne oluşturma `COleServerItem` seçilen verileri içeren. Aksi takdirde, oluşturun bir `COleDataSource` veri nesnesi.  
  
2.  Seçilen öğenin çağrı `CopyToClipboard` üye işlevi.  
  
3.  Kullanıcı bir kopyalama işlemi yerine bir kesme işlemi seçerseniz, seçilen verileri uygulamanızdan silin.  
  
 Bu sıranın bir örnek görmek için bkz **OnEditCut** ve **OnEditCopy** işlevlerde MFC OLE örnek programlar [OCLIENT](../visual-cpp-samples.md) ve [HIERSVR](../visual-cpp-samples.md). 1. adım zaten eksiksiz olması için bu örnekleri şu anda seçili veri için bir işaretçi korumak unutmayın.  
  
##  <a name="_core_pasting_data"></a>Veri yapıştırma  
 Veri yapıştırma, verileri uygulamanıza yapıştırma içinde kullanılacak biçimi seçin gerektiğinden kopyalamak daha çok daha karmaşıktır.  
  
#### <a name="to-paste-data-from-the-clipboard"></a>Pano'dan veri yapıştırmak için  
  
1.  Görünüm sınıfınızda uygulamak **OnEditPaste** Düzen menüsünden Yapıştır seçeneğini belirleyerek kullanıcıların işlemek için.  
  
2.  İçinde **OnEditPaste** işlev, oluşturma bir `COleDataObject` nesne ve çağrı kendi `AttachClipboard` Panodaki veriler için bu nesneyi bağlamak için üye işlevi.  
  
3.  Çağrı `COleDataObject::IsDataAvailable` belirli bir biçimde kullanılabilir olup olmadığını denetlemek için.  
  
     Alternatif olarak, kullanabileceğiniz `COleDataObject::BeginEnumFormats` bir uygulamanız için en uygun bulana kadar diğer biçimlere için aranacak.  
  
4.  Biçim Yapıştır gerçekleştirin.  
  
 Bunun nasıl çalıştığı bir örnek için bkz: **OnEditPaste** MFC OLE örnek programlar içinde tanımlanan görünüm sınıflardaki üye işlevleri [OCLIENT](../visual-cpp-samples.md) ve [HIERSVR](../visual-cpp-samples.md).  
  
> [!TIP]
>  Yapıştırma işlemi kendi işlevine ayırma ana avantajı veri sürükle ve bırak işlemi sırasında uygulamanızda bırakıldığında aynı Yapıştır kodu kullanılabilir olur. OCLIENT ve HIERSVR, olduğu gibi `OnDrop` işlevi de çağırabilir **DoPasteItem**, yapıştırma işlemleri uygulamak için yazılan kodu yeniden kullanma.  
  
 Düzen menüsünde Özel Yapıştır seçeneği işlemek için Ek Yardım konusuna [ole'deki iletişim kutuları](../mfc/dialog-boxes-in-ole.md).  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Diğer biçimleri ekleme](../mfc/clipboard-adding-other-formats.md)  
  
-   [OLE veri nesneleri ve veri kaynakları ve Tekdüzen veri aktarımı](../mfc/data-objects-and-data-sources-ole.md)  
  
-   [OLE sürükleme ve bırakma](../mfc/drag-and-drop-ole.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pano: OLE Pano Mekanizmasını Kullanma](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

