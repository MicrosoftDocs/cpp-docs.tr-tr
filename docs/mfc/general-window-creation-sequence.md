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
ms.openlocfilehash: 9336e5fa19b373f07c54e758a6f939bbc63e50ec
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432795"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Pencereler Oluşturma](../mfc/creating-windows.md)

