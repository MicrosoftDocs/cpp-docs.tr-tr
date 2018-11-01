---
title: MFC Uygulama Sihirbazından Oluşturulan Belge ve Görünüm Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
ms.openlocfilehash: 0ef0da4ea738d02518fb68085afc194e219103cd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464593"
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>MFC Uygulama Sihirbazından Oluşturulan Belge ve Görünüm Sınıfları

MFC Uygulama Sihirbazı iskelet belge ve görünüm sınıfları, oluşturarak program geliştirme avantajlı bir başlangıç sağlar. Daha sonra [komutları ve iletileri bu sınıflara eşleme](../mfc/reference/mapping-messages-to-functions.md) ve kendi üye işlevleri yazmak için Visual C++ kaynak kod Düzenleyicisi'ni kullanın.

MFC Uygulama sihirbazından oluşturulan belge sınıfı sınıfından türetilir [CDocument](../mfc/reference/cdocument-class.md). Görünüm sınıfını türetilen [CView](../mfc/reference/cview-class.md). Uygulama Sihirbazı iletişim kutusunda sağladığınız adlarını Uygulama Sihirbazı'nı bu sınıfları sağlar ve bunları içeren dosyaları, proje adını temel alır. Uygulama Sihirbazı'nda varsayılan adlarını değiştirmek için oluşturulan sınıflar sayfasını kullanabilirsiniz.

Bazı uygulamalar, birden fazla belge sınıfı, görünüm sınıfı veya çerçeve penceresi sınıfında gerekebilir. Daha fazla bilgi için [birden çok belge türü, görünümler ve çerçeve Windows](../mfc/multiple-document-types-views-and-frame-windows.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Belge/görünüm mimarisi](../mfc/document-view-architecture.md)

