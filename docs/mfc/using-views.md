---
title: "Görünümleri kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interacting with users and role of view class [MFC]
- drawing [MFC], data
- rendering data
- view classes [MFC], role in managing user interaction
- CView class [MFC], view architecture
- MFC, views
- views [MFC], using
- painting data
- user input [MFC], interpreting through view class [MFC]
- view classes [MFC], role in displaying application data
ms.assetid: dc3de6ad-5c64-4317-8f10-8bdcc38cdbd5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 99493657313d480559d232bf9033dfb7a7a585c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-views"></a>Görünümleri Kullanma
Görünümün sorumlulukları belgenin veri kullanıcıya grafik görüntüleme ve kabul edin ve belge üzerinde işlemler olarak kullanıcı girişini yorumlama üzeresiniz. View sınıfı yazma görevleri vardır:  
  
-   Görünüm sınıfınızın yazma [OnDraw](../mfc/reference/cview-class.md#ondraw) belgenin veri işler üye işlevi.  
  
-   View sınıfında ileti işleyicisi üye işlevleri uygun Windows iletileri ve menü öğeleri gibi kullanıcı arabirimi nesneleri bağlayın.  
  
-   Kullanıcı girişini yorumlama bu işleyicileri uygulayın.  
  
 Ayrıca, diğer geçersiz kılmanız gerekebilir `CView` türetilmiş görünüm sınıfınız içindeki üye işlevleri. Özellikle, geçersiz kılmak isteyebilirsiniz [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) özel başlatma için görünümü gerçekleştirmek için ve [in](../mfc/reference/cview-class.md#onupdate) görünümü kendisi yalnızca yeniden çizer önce gerekli herhangi bir özel işlem yapmak için. Birden çok belge için geçersiz kılmalısınız [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) yazdırmak için sayfa sayısı ve diğer bilgileri Yazdır iletişim kutusu başlatılamadı. Geçersiz kılma hakkında daha fazla bilgi için `CView` üye işlevleri bkz sınıfı [CView](../mfc/reference/cview-class.md) içinde *MFC başvurusu*.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [MFC'de kullanılabilen türetilmiş görünüm sınıfları](../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [Bir görünümde çizim yapma](../mfc/drawing-in-a-view.md)  
  
-   [Bir görünüm kullanıcı girişini yorumlama](../mfc/interpreting-user-input-through-a-view.md)  
  
-   [Yazdırmada görünümün rolü](../mfc/role-of-the-view-in-printing.md)  
  
-   [Görünümleri kaydırma ve ölçeklendirme](../mfc/scrolling-and-scaling-views.md)  
  
-   [Başlatma ve belgeleri ve görünümleri temizleme](../mfc/initializing-and-cleaning-up-documents-and-views.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge/görünüm mimarisi](../mfc/document-view-architecture.md)   
 [Cformview'yu sınıfı](../mfc/reference/cformview-class.md)   
 [Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)   
 [Seri Hale Getirme Mekanizmasını Atlama](../mfc/bypassing-the-serialization-mechanism.md)

