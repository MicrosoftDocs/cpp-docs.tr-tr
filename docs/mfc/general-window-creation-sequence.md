---
title: Genel Pencere Oluşturma Dizisi
ms.date: 11/04/2016
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
ms.openlocfilehash: fb10ced78e230316a6e2982f24c1fb6e2e52ed8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364265"
---
# <a name="general-window-creation-sequence"></a>Genel Pencere Oluşturma Dizisi

Alt pencere gibi kendi pencerenizi oluşturduğunuzda, çerçeve [Belge/Görünüm Oluşturma'da](../mfc/document-view-creation.md)açıklananla aynı işlemi kullanır.

MFC tarafından sağlanan tüm pencere sınıfları [iki aşamalı inşaat](../mfc/one-stage-and-two-stage-construction-of-objects.md)kullanır. Diğer bir deyişle, C++ **yeni** işlecinin çağrılması sırasında, oluşturucu bir C++ nesnesini ayırır ve aparat eder, ancak karşılık gelen bir Windows penceresi oluşturmaz. Bu daha sonra pencere nesnesinin Üye [Oluştur](../mfc/reference/cwnd-class.md#create) işlevini çağırarak yapılır.

Üye `Create` işlev Windows penceresini yapar `HWND` ve c++ nesnesinin genel veri üyesi [m_hWnd](../mfc/reference/cwnd-class.md#m_hwnd)depolar. `Create`oluşturma parametreleri üzerinde tam esneklik sağlar. Aramadan `Create`önce, çerçeve için simge ve sınıf stilleri ayarlamak için global işlevi [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) ile bir pencere sınıfı kaydetmek isteyebilirsiniz.

Çerçeve pencereleri için [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) üye işlevini `Create`'' yerine kullanabilirsiniz. `LoadFrame`daha az parametre kullanarak Windows penceresini yapar. Çerçevenin resim yazısı, simge, hızlandırıcı tablosu ve menü dahil olmak üzere kaynaklardan birçok varsayılan değer alır.

> [!NOTE]
> Simgenizin, hızlandırıcı tablonuzun ve menü kaynaklarınızın LoadFrame tarafından yüklenmesi için **IDR_MAINFRAME**gibi ortak bir kaynak kimliğine sahip olması gerekir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Pencere nesneleri](../mfc/window-objects.md)

- [Pencere "sınıflar" kaydetme](../mfc/registering-window-classes.md)

- [Pencere nesnelerini yok etme](../mfc/destroying-window-objects.md)

- [Belge çerçevesi pencereleri oluşturma](../mfc/creating-document-frame-windows.md)

## <a name="see-also"></a>Ayrıca bkz.

[Windows Oluşturma](../mfc/creating-windows.md)
