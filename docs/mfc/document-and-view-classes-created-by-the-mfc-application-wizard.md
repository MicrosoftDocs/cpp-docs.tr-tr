---
title: Belge ve MFC Uygulama Sihirbazı tarafından oluşturulan sınıflar görüntüleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb1a1fc6c35bfb9589e827d798cb112640fa9b2f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417624"
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>MFC Uygulama Sihirbazından Oluşturulan Belge ve Görünüm Sınıfları

MFC Uygulama Sihirbazı iskelet belge ve görünüm sınıfları, oluşturarak program geliştirme avantajlı bir başlangıç sağlar. Daha sonra [komutları ve iletileri bu sınıflara eşleme](../mfc/reference/mapping-messages-to-functions.md) ve kendi üye işlevleri yazmak için Visual C++ kaynak kod Düzenleyicisi'ni kullanın.

MFC Uygulama sihirbazından oluşturulan belge sınıfı sınıfından türetilir [CDocument](../mfc/reference/cdocument-class.md). Görünüm sınıfını türetilen [CView](../mfc/reference/cview-class.md). Uygulama Sihirbazı iletişim kutusunda sağladığınız adlarını Uygulama Sihirbazı'nı bu sınıfları sağlar ve bunları içeren dosyaları, proje adını temel alır. Uygulama Sihirbazı'nda varsayılan adlarını değiştirmek için oluşturulan sınıflar sayfasını kullanabilirsiniz.

Bazı uygulamalar, birden fazla belge sınıfı, görünüm sınıfı veya çerçeve penceresi sınıfında gerekebilir. Daha fazla bilgi için [birden çok belge türü, görünümler ve çerçeve Windows](../mfc/multiple-document-types-views-and-frame-windows.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Belge/görünüm mimarisi](../mfc/document-view-architecture.md)

