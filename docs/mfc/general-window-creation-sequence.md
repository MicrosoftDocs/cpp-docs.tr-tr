---
title: "Genel pencere oluşturma dizisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 59bed4387a6b8e6edeb504e29d221e76a0b39d18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="general-window-creation-sequence"></a>Genel Pencere Oluşturma Dizisi
Kendi alt gibi penceresinin bir pencere oluşturduğunuzda framework kadar aynı işlem içinde açıklanan olarak kullanır. [belge/görünüm oluşturma](../mfc/document-view-creation.md).  
  
 MFC employ tarafından sağlanan tüm pencere sınıfları [iki aşamalı yapımı](../mfc/one-stage-and-two-stage-construction-of-objects.md). Diğer bir deyişle, C++, bir çağrı sırasında **yeni** işleci, Oluşturucusu ayırır ve C++ nesnesini başlatır, ancak karşılık gelen bir Windows penceresi oluşturmaz. Yapılır daha sonra çağırarak [oluşturma](../mfc/reference/cwnd-class.md#create) üye işlevini pencere nesnesi.  
  
 **Oluşturma** üye işlevi Windows penceresi yapar ve depolar, `HWND` C++ nesnenin ortak veri üyesi olarak [m_hWnd](../mfc/reference/cwnd-class.md#m_hwnd). **Oluşturma** oluşturma parametreleri tam esneklik sağlar. Çağırmadan önce **oluşturma**, pencere sınıfı genel işleviyle kaydetmek isteyebilirsiniz [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) çerçeve simgesini ve sınıf stilleri ayarlamak için.  
  
 Çerçeve pencereleri için kullandığınız [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) üye işlevi yerine **oluşturma**. `LoadFrame`daha az parametrelerini kullanarak Windows penceresi yapar. Çerçeve resim yazısı simgesi, Hızlandırıcı tablosu ve menü çeşitli kaynaklardan birçok varsayılan değerleri alır.  
  
> [!NOTE]
>  Simge, Hızlandırıcı tablosu ve menü kaynakları ortak bir kaynak kimliği gibi olmalı **IDR_MAINFRAME**, bunların LoadFrame tarafından yüklenebilir.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Pencere nesneleri](../mfc/window-objects.md)  
  
-   [Pencere "sınıflarını" kaydetme](../mfc/registering-window-classes.md)  
  
-   [Pencere nesnelerini yok etme](../mfc/destroying-window-objects.md)  
  
-   [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencereler Oluşturma](../mfc/creating-windows.md)

