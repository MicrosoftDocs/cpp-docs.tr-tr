---
title: Genel Pencere Oluşturma Dizisi
ms.date: 11/04/2016
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
ms.openlocfilehash: 949cf72910654b502ca4b57be72bedc2db63c315
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269233"
---
# <a name="general-window-creation-sequence"></a>Genel Pencere Oluşturma Dizisi

Bir pencerenin kendi gibi bir alt pencere oluşturduğunuzda, framework kadar aynı işlem içinde açıklanan olarak kullanır. [belge/görünüm oluşturma](../mfc/document-view-creation.md).

MFC kullanan tarafından sağlanan tüm pencere sınıflarının [iki aşamalı yapımı](../mfc/one-stage-and-two-stage-construction-of-objects.md). Diğer bir deyişle, C++'ın bir çağrı sırasında **yeni** işleci, oluşturucu ayırır ve bir C++ nesnesi başlatır ancak karşılık gelen bir Windows penceresi oluşturmaz. Bu yapılır sonradan çağırarak [Oluştur](../mfc/reference/cwnd-class.md#create) pencere nesnesi üye işlevi.

`Create` Windows penceresi üye işlevini sağlar ve depolar, `HWND` C++ nesnesinin genel veri üyesi içinde [m_hWnd](../mfc/reference/cwnd-class.md#m_hwnd). `Create` size esneklik oluşturma parametreleri tamamlayın. Çağırmadan önce `Create`, pencere sınıfı ile genel işlev kaydetmek isteyebilirsiniz [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) çerçevesi için simge ve sınıf stilleri ayarlamak için.

Çerçeve pencereleri için kullanabileceğiniz [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) üye işlevi yerine `Create`. `LoadFrame` daha az parametre kullanılarak Windows penceresi sağlar. Çerçevenin başlık, simgesi, Hızlandırıcı tablosu ve menü gibi kaynaklardan birçok varsayılan değerleri alır.

> [!NOTE]
>  Ortak bir kaynak kimliği gibi simge, Hızlandırıcı tablosu ve menüsü kaynaklarını olmalıdır **IDR_MAINFRAME**, bunların LoadFrame tarafından yüklenebilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Pencere nesneleri](../mfc/window-objects.md)

- [Pencere "sınıflarını" kaydetme](../mfc/registering-window-classes.md)

- [Pencere nesnelerini yok etme](../mfc/destroying-window-objects.md)

- [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)

## <a name="see-also"></a>Ayrıca bkz.

[Pencereler Oluşturma](../mfc/creating-windows.md)
