---
title: Internet'te etkin belgeler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- active documents [MFC], creating
- application wizards [MFC], active documents
- active documents [MFC], programming steps
- application wizards [MFC]
- active documents [MFC], using application wizards
ms.assetid: a46bd8a0-e27a-4116-b1bf-dacdb7ae78d1
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 67fdedaf9b100ae85352b1514f96fe7e229e4f9f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="active-documents-on-the-internet"></a>Internet'te Etkin Belgeler
Etkin belgeler geleneksel katıştırılmış nesneler için uzantı sağlar. Etkin belgeler sayfalı olabilir ve tüm istemci alanında görüntülenir. Bunlar geleneksel menü anlaşma yapın ve yerinde yanı sıra sunucu uygulaması açık bir pencerede düzenlenebilir. Taranmış bir kenarlığı küçük bir dikdörtgen olarak görüntülemek yerine, etkin tam çerçeve ve her zaman yerinde etkin belgelerdir.  
  
 Etkin belgeler gibi Microsoft Office Word, Excel gibi farklı belge türlerinin oluşan bir bileşik belge oluşturmak için bir yol sağlayan bağlayıcı, bir kapsayıcı görüntülenebilir ve her biri olabilen özel belge türünüz tam çerçeve düzenlenebilir. Etkin belgeler, etkin belge kapsayıcı Microsoft Internet Explorer gibi bir tarayıcıda da görüntülenebilir.  
  
 **Etkin belge avantajları şunlardır:**  
  
-   Belgeleri görüntülenebilir tüm istemci penceresinde tam çerçeve.  
  
-   Belgeleri ayrı uygulama penceresinde açılabilir.  
  
     Belgenin açmak yardımcı uygulama istemcide mevcut olmalıdır veya uygulamayı çalıştırmadan önce ayrı olarak indirilmesi. Bir Görüntüleyici (Word, PowerPoint ve Excel için kendi belgeleri görüntüleyicileri sağlar) sınırlı işlevsellik sağlamak için yazılabilir. Uygulamanın tam sürümünü düzenleme için tam destek sağlar.  
  
-   Her zaman yerinde etkin belgelerdir.  
  
-   Menü komutları kapsayıcıdan çağrılan belgenize yönlendirilebilir.  
  
-   Belgeler, bir Web tarayıcısında görüntülenebilir. Bu, belgelerinizi ve diğer Web sayfaları arasında sorunsuz tümleştirme sağlar.  
  
     Bir kullanıcı bir Excel elektronik tablosuna sonra bir HTML Web sayfasını göz atın ve ardından MFC kullanılarak yazılmış bir belge etkin belgeler için destek. Kullanıcı, bir HTML sayfası, Excel ve uygulamanızın belge görünümlerini ve menüleri arasında sorunsuz bir şekilde tarayıcı anahtarları olarak bilinen Web arabirimi kullanarak gidebilirsiniz.  
  
-   Tüm uygulamaları, ortak bir çerçevede görüntülenir.  
  
## <a name="requirements-for-active-documents"></a>Etkin belgeler için gereksinimleri  
 Aşağıdaki tabloda listelenen arabirimler zaten ekli sunucuları için gerekli arabirimleri ve etkin belgeler için belirli birkaç yeni arabirimleri içerir. MFC sağlar çoğu bu arabirimleri için varsayılan uygulamaları [COleServerDoc](../mfc/reference/coleserverdoc-class.md) sınıfı.  
  
|Bir belge...|Bu arabirimlerini uygular|  
|-------------------------|---------------------------------|  
|Kullanım dosyalar kendi depolama mekanizması olarak bileşik.|`IPersistStorage`.|  
|Etkin belgeler, Dosyadan Oluştur dahil olmak üzere temel katıştırma özelliklerini destekler.|`IPersistFile`, `IOleObject`, ve `IDataObject`.|  
|Destekler yerinde etkinleştirme.|`IOleInPlaceObject`ve `IOleInPlaceActiveObject` (kapsayıcının kullanarak `IOleInPlaceSite` ve **IOleInPlaceFrame** arabirimleri).|  
|Bu yeni arabirimleri içeren etkin belgeyi uzantıları destekler. Bazı arabirimler isteğe bağlıdır.|`IOleDocument`, `IOleDocumentView`, `IOleCommandTarget`, ve `IPrint`.|  
  
 MFC etkin belgeler için varolan katıştırılmış sunucu desteği genişletmek için destek sağlar.  
  
## <a name="add-active-document-support-to-a-new-application"></a>Etkin belge desteği için yeni bir uygulama ekleyin  
 Etkin belge desteği ile yeni bir uygulama oluşturmak için: MFC Uygulama Sihirbazı, **birleşik belge desteği** sayfasında, "Select birleşik belge desteği altında" **tam sunucu** veya  **Kapsayıcı/tam sunucu**ve "Ek seçenekleri belirleyin altında" onay kutusunu seçin **etkin belge sunucusu**.  
  
##  <a name="_core_convert_an_existing_mfc_in.2d.process_server_to_an_activex_document_server"></a>Etkin belge sunucusu için varolan bir MFC işlemdeki sunucu Dönüştür  
 Uygulamanızı sürüm 4.2 önce Visual C++ sürümüyle oluşturuldu ve zaten bir işlem sunucusu ise, aşağıdaki sınıflar değişiklikler yaparak etkin belgeyi destek ekleyebilirsiniz:  
  
|Sınıf türü|Önceden türetilmiş|Öğesinden türetilen için Değiştir|  
|----------------|---------------------------|---------------------------|  
|Yerinde çerçeve|`COleIPFrameWnd`|**COleDocIPFrameWnd**|  
|Öğe|`COleServerItem`|`CDocObjectServerItem`|  
  
 Ayrıca bilgileri kayıt defterinde nasıl girildiğini değiştirin ve diğer birkaç değişiklik. Uygulamanız şu anda hiçbir COM bileşenleri desteği varsa, Uygulama Sihirbazı'nı çalıştırarak ve COM bileşeni özel kod mevcut uygulamanızla tümleştirmek sunucu desteği ekleyebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Internet programlama görevleri](../mfc/mfc-internet-programming-tasks.md)   
 [MFC Internet Programlama temelleri](../mfc/mfc-internet-programming-basics.md)

