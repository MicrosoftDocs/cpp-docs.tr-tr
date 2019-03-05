---
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
ms.openlocfilehash: 81668f7409f2b1a4480bde958dc06ce1156e03fe
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291177"
---
# <a name="using-views"></a>Görünümleri Kullanma

Görünümün sorumlulukları, belgenin verilerini grafik kullanıcıya göstermek ve kabul edin ve belge işlemleri olarak kullanıcı girişini yorumlama üzeresiniz. Görünüm sınıfınıza yazma görevleri vardır:

- Görünüm sınıfınızın yazma [OnDraw](../mfc/reference/cview-class.md#ondraw) belgenin verilerini işleyen üye işlevi.

- Uygun Windows iletilerini ve kullanıcı arabirimi nesneleri menü öğeleri gibi ileti işleyicisi üye işlevleri view sınıfında bağlanın.

- Kullanıcı girişini yorumlama bu işleyicileri uygulayın.

Ayrıca, diğer geçersiz kılmanız gerekebilir `CView` türetilmiş görünüm sınıfınızdaki üye işlevleri. Özellikle, geçersiz kılmak isteyebilirsiniz [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) görünüm için özel başlatma gerçekleştirme ve [OnUpdate](../mfc/reference/cview-class.md#onupdate) görünümü kendisi yalnızca yeniden çizer önce gerekli olan herhangi bir özel işlemi yapmak için. Birden fazla belge için geçersiz kılmalısınız [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) yazdırmak için sayfa sayısı ve diğer bilgileri Yazdır iletişim kutusu başlatılamadı. Geçersiz kılma hakkında daha fazla bilgi için `CView` üye işlevleri, bkz: sınıf [CView](../mfc/reference/cview-class.md) içinde *MFC başvurusu*.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [MFC'de kullanılabilen türetilmiş görünüm sınıfları](../mfc/derived-view-classes-available-in-mfc.md)

- [Bir görünümde çizim yapma](../mfc/drawing-in-a-view.md)

- [Bir görünüm aracılığıyla kullanıcı girişini yorumlama](../mfc/interpreting-user-input-through-a-view.md)

- [Yazdırmada görünümün rolü](../mfc/role-of-the-view-in-printing.md)

- [Görünümleri kaydırma ve ölçeklendirme](../mfc/scrolling-and-scaling-views.md)

- [Başlatma ve belgeleri ve görünümleri temizleme](../mfc/initializing-and-cleaning-up-documents-and-views.md)

## <a name="see-also"></a>Ayrıca bkz.

[Belge/görünüm mimarisi](../mfc/document-view-architecture.md)<br/>
[CFormView Sınıfı](../mfc/reference/cformview-class.md)<br/>
[Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)<br/>
[Seri Hale Getirme Mekanizmasını Atlama](../mfc/bypassing-the-serialization-mechanism.md)
