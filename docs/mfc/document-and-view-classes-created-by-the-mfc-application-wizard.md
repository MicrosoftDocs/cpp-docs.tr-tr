---
title: MFC Uygulama Sihirbazından Oluşturulan Belge ve Görünüm Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
ms.openlocfilehash: 766fe4efb37c199c5babb75ce2cb08ebf676cca6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616045"
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>MFC Uygulama Sihirbazından Oluşturulan Belge ve Görünüm Sınıfları

MFC Uygulama Sihirbazı, sizin için iskelet belge ve Görünüm sınıfları oluşturup program geliştirme konusunda bir baş başlangıç sağlar. Daha sonra [bu sınıflara komutları ve iletileri eşleyebilir](reference/mapping-messages-to-functions.md) ve Visual C++ kaynak kodu düzenleyicisini kullanarak üye işlevlerini yazabilirsiniz.

MFC Uygulama Sihirbazı tarafından oluşturulan belge sınıfı [CDocument](reference/cdocument-class.md)sınıfından türetilir. Görünüm sınıfı [CView](reference/cview-class.md)'dan türetilir. Uygulama Sihirbazı 'nın bu sınıfları verdiği adlar ve bunları içeren dosyalar, uygulama Sihirbazı iletişim kutusunda sağladığınız proje adına dayalıdır. Uygulama sihirbazında, oluşturulan sınıflar sayfasını kullanarak varsayılan adları değiştirebilirsiniz.

Bazı uygulamaların birden fazla belge sınıfına, görünüm sınıfına veya çerçeve pencere sınıfına ihtiyacı bulunabilir. Daha fazla bilgi için bkz. [birden fazla belge türü, görünüm ve çerçeve pencereleri](multiple-document-types-views-and-frame-windows.md).

## <a name="see-also"></a>Ayrıca bkz.

[Belge/görünüm mimarisi](document-view-architecture.md)
