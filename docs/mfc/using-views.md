---
description: 'Hakkında daha fazla bilgi edinin: görünümleri kullanma'
title: Görünümleri Kullanma
ms.date: 11/04/2016
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
ms.openlocfilehash: f17855c1389da44630a21830033c4457db6e3703
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236652"
---
# <a name="using-views"></a>Görünümleri Kullanma

Görünümün sorumlulukları, belgenin verilerini kullanıcı için grafiksel olarak görüntülemek ve Kullanıcı girişini belgede işlem olarak kabul etmek ve yorumlamak için kullanılır. Görünüm sınıfınızı yazarken görevleriniz şunlardır:

- Belge verilerini işleyen Görünüm sınıfınızın [OnDraw](../mfc/reference/cview-class.md#ondraw) üye işlevini yazın.

- Uygun Windows iletilerini ve menü öğeleri gibi kullanıcı arabirimi nesnelerini görünüm sınıfındaki ileti işleyici üye işlevlerine bağlayın.

- Kullanıcı girişini yorumlamak için bu işleyicileri uygulayın.

Ayrıca, `CView` türetilmiş Görünüm sınıfınızın diğer üye işlevlerini geçersiz kılmanız gerekebilir. Özellikle, görünümün kendisini yeniden yazdırmadan önce gerekli özel işlemleri yapmak için görünüm ve [OnUpdate](../mfc/reference/cview-class.md#onupdate) için özel başlatma gerçekleştirmek üzere [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) 'i geçersiz kılmak isteyebilirsiniz. Çok sayfalı belgeler için, Yazdır iletişim kutusunu yazdırılacak sayfa sayısı ve diğer bilgiler ile başlatmak için [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) 'i geçersiz kılmanız gerekir. Üye işlevlerini geçersiz kılma hakkında daha fazla bilgi için `CView` *MFC başvurusunda* sınıf [CView](../mfc/reference/cview-class.md) bölümüne bakın.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [MFC'de kullanılabilen türetilmiş görünüm sınıfları](../mfc/derived-view-classes-available-in-mfc.md)

- [Bir görünümde çizim yapma](../mfc/drawing-in-a-view.md)

- [Bir görünümü kullanarak kullanıcı girişini yorumlama](../mfc/interpreting-user-input-through-a-view.md)

- [Yazdırmada görünümün rolü](../mfc/role-of-the-view-in-printing.md)

- [Görünümleri kaydırma ve ölçeklendirme](../mfc/scrolling-and-scaling-views.md)

- [Belgeleri ve görünümleri başlatma ve temizleme](../mfc/initializing-and-cleaning-up-documents-and-views.md)

## <a name="see-also"></a>Ayrıca bkz.

[Belge/görünüm mimarisi](../mfc/document-view-architecture.md)<br/>
[CFormView sınıfı](../mfc/reference/cformview-class.md)<br/>
[Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)<br/>
[Serileştirme mekanizmasını atlama](../mfc/bypassing-the-serialization-mechanism.md)
