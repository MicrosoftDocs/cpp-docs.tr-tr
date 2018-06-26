---
title: Genel pencere oluşturma dizisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3a4b67ccbba97405678985e6412cc56911bd184
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929698"
---
# <a name="general-window-creation-sequence"></a>Genel Pencere Oluşturma Dizisi
Kendi alt gibi penceresinin bir pencere oluşturduğunuzda framework kadar aynı işlem içinde açıklanan olarak kullanır. [belge/görünüm oluşturma](../mfc/document-view-creation.md).  
  
 MFC employ tarafından sağlanan tüm pencere sınıfları [iki aşamalı yapımı](../mfc/one-stage-and-two-stage-construction-of-objects.md). Diğer bir deyişle, C++, bir çağrı sırasında **yeni** işleci, Oluşturucusu ayırır ve C++ nesnesini başlatır, ancak karşılık gelen bir Windows penceresi oluşturmaz. Yapılır daha sonra çağırarak [oluşturma](../mfc/reference/cwnd-class.md#create) üye işlevini pencere nesnesi.  
  
 `Create` Üye işlevi Windows penceresi yapar ve depolar, `HWND` C++ nesnenin ortak veri üyesi olarak [m_hWnd](../mfc/reference/cwnd-class.md#m_hwnd). `Create` verir esneklik oluşturma parametreleri tamamlayın. Çağırmadan önce `Create`, pencere sınıfı genel işleviyle kaydetmek isteyebilirsiniz [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) çerçeve simgesini ve sınıf stilleri ayarlamak için.  
  
 Çerçeve pencereleri için kullandığınız [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) üye işlevi yerine `Create`. `LoadFrame` daha az parametrelerini kullanarak Windows penceresi yapar. Çerçeve resim yazısı simgesi, Hızlandırıcı tablosu ve menü çeşitli kaynaklardan birçok varsayılan değerleri alır.  
  
> [!NOTE]
>  Simge, Hızlandırıcı tablosu ve menü kaynakları ortak bir kaynak kimliği gibi olmalı **IDR_MAINFRAME**, bunların LoadFrame tarafından yüklenebilir.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Pencere nesneleri](../mfc/window-objects.md)  
  
-   [Pencere "sınıflarını" kaydetme](../mfc/registering-window-classes.md)  
  
-   [Pencere nesnelerini yok etme](../mfc/destroying-window-objects.md)  
  
-   [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencereler Oluşturma](../mfc/creating-windows.md)

