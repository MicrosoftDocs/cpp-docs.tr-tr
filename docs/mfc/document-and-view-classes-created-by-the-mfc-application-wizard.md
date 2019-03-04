---
title: MFC Uygulama Sihirbazından Oluşturulan Belge ve Görünüm Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
ms.openlocfilehash: 95b50e34d612c3b8f5dea2f8b469bd6c65182d41
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271456"
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>MFC Uygulama Sihirbazından Oluşturulan Belge ve Görünüm Sınıfları

MFC Uygulama Sihirbazı iskelet belge ve görünüm sınıfları, oluşturarak program geliştirme avantajlı bir başlangıç sağlar. Daha sonra [komutları ve iletileri bu sınıflara eşleme](../mfc/reference/mapping-messages-to-functions.md) ve kendi üye işlevleri yazmak için Visual C++ kaynak kod Düzenleyicisi'ni kullanın.

MFC Uygulama sihirbazından oluşturulan belge sınıfı sınıfından türetilir [CDocument](../mfc/reference/cdocument-class.md). Görünüm sınıfını türetilen [CView](../mfc/reference/cview-class.md). Uygulama Sihirbazı iletişim kutusunda sağladığınız adlarını Uygulama Sihirbazı'nı bu sınıfları sağlar ve bunları içeren dosyaları, proje adını temel alır. Uygulama Sihirbazı'nda varsayılan adlarını değiştirmek için oluşturulan sınıflar sayfasını kullanabilirsiniz.

Bazı uygulamalar, birden fazla belge sınıfı, görünüm sınıfı veya çerçeve penceresi sınıfında gerekebilir. Daha fazla bilgi için [birden çok belge türü, görünümler ve çerçeve Windows](../mfc/multiple-document-types-views-and-frame-windows.md).

## <a name="see-also"></a>Ayrıca bkz.

[Belge/görünüm mimarisi](../mfc/document-view-architecture.md)
