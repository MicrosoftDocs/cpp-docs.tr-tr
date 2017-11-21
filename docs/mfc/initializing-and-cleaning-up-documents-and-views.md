---
title: "Başlatma ve belgeleri ve görünümleri temizleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- initializing documents [MFC]
- views [MFC], cleaning up
- documents [MFC], initializing
- documents [MFC], cleaning up
- views [MFC], initializing
- initializing objects [MFC], document objects
- document objects [MFC], life cycle of
- initializing views [MFC]
ms.assetid: 95d6f09b-a047-4079-856a-ae7d0548e9d2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e193e2d6f32c60781a87620c6b955c1f646a5b44
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="initializing-and-cleaning-up-documents-and-views"></a>Belgeleri ve Görünümleri Başlatma ve Temizleme
Başlatma ve sonra belgeleri ve görünümleri Temizleme için aşağıdaki kılavuzları kullanın:  
  
-   MFC çerçevesi belgeler ve görünümler başlatır; bunları Ekle herhangi bir veri başlatır.  
  
-   Belgeleri olarak framework temizler ve görünümleri kapatın; yığınından bu belgeler ve görünümler üzerinde üye işlevleri içinde ayrılmış bellek ayırması gerekir.  
  
> [!NOTE]
>  Tüm uygulama geçersiz kılmada en iyi şekilde yapılır için o başlatma geri çağırma [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) sınıfının üye işlevini `CWinApp`, ve temizleme tüm uygulama için en iyi ,geçersizkılmadayapılır`CWinApp`üye işlevi [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance).  
  
 Bir belge (ve kendi çerçeve penceresi ve görünüm veya Görünüm) MDI yaşam döngüsünü uygulama aşağıdaki gibidir:  
  
1.  Dinamik oluşturma sırasında belge Oluşturucusu çağrılır.  
  
2.  Her yeni bir belgenin, belge için [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) veya [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) olarak adlandırılır.  
  
3.  Kullanıcı belge yaşam süresi boyunca ile etkileşim kurar. Genellikle kullanıcı belgeyi veri görünümü aracılığıyla seçme ve veri düzenleme çalışır gibi bu gerçekleşir. Görünümü açın ve belge depolama ve diğer görünümlere güncelleştirmek için değişiklikleri geçirir. Bu süre boyunca, belge ve görünüm komutları işleyebilirsiniz.  
  
4.  Framework çağrıları [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) bir belge için belirli veri silmek için.  
  
5.  Belgenin yıkıcı olarak adlandırılır.  
  
 Belge ilk oluşturulduğunda sonra SDI uygulamada 1. adım gerçekleştirilir. Ardından 2-4 arası adımlar sürekli olarak yeni bir belge her açıldığında gerçekleştirilir. Yeni belge varolan belge nesnesi yeniden kullanır. Son olarak, uygulama bittiğinde 5. adım gerçekleştirilir.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Belgeleri ve görünümleri başlatma](../mfc/initializing-documents-and-views.md)  
  
-   [Belgeleri ve görünümleri temizleme](../mfc/cleaning-up-documents-and-views.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge/görünüm mimarisi](../mfc/document-view-architecture.md)

