---
title: Menüler ve Kaynaklar (OLE)
ms.date: 11/04/2016
helpviewer_keywords:
- OLE visual editing servers [MFC]
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- string tables [MFC], visual editing applications
- OLE containers [MFC], menus and resources
- OLE applications [MFC], menus and resources
- OLE server applications [MFC], menus and resources
- toolbars [MFC], OLE document applications
- string editing [MFC], visual editing applications
- server applications [MFC], OLE menus and resources
- applications [OLE], menus and resources
- menus [MFC], OLE document applications
- in-place activation [MFC], OLE menus and resources
- containers [MFC], OLE container applications
- OLE menus and resources [MFC]
ms.assetid: 52bfa086-7d3d-466f-94c7-c7061f3bdb3a
ms.openlocfilehash: 4e8f8c7fa8e24349a741b99822f13d5473373e17
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268531"
---
# <a name="menus-and-resources-ole"></a>Menüler ve Kaynaklar (OLE)

Bu grubu makaleler, menüler ve kaynaklar MFC OLE belge uygulamaları içinde kullanılmasını açıklar.

OLE görsel düzenleme ek gereksinimler menü ve hangi iki kapsayıcı modlarında sayısı olduğundan OLE belge uygulamaları tarafından sağlanan diğer kaynakları yerleştirir ve sunucu (bileşen için) uygulamaları kullanmaya ve kullanılır. Örneğin, bir tam sunucu uygulaması aşağıdaki üç modun herhangi birinde çalıştırabilirsiniz:

- Tek başına duramaz.

- Yerinde düzenleme bağlamı içinde bir öğe kapsayıcı.

- Açık, genellikle ayrı bir pencerede onun kapsayıcısının bağlamı dışındaki bir öğeyi düzenlemek için kullanılır.

Bu, bir uygulamanın olası her modu için üç ayrı menü düzenlerini gerektirir. Hızlandırıcı tablolarını, ayrıca her yeni modu için gereklidir. Kapsayıcılı bir uygulama olabilir veya yerinde etkinleştirme desteklemiyor olabilir; varsa, yeni bir menüsü yapısı gerekir ve Hızlandırıcı tablolarını ilişkili.

Yerinde etkinleştirme kapsayıcı ve sunucu uygulamaları için menüsü araç çubuğu ve durum çubuğu alanı anlaşmaları gerekir gerektirir. Tüm kaynaklar bunu aklınızda tasarlanmalıdır. Makaleyi [menüler ve kaynaklar: Menü birleştirme](../mfc/menus-and-resources-menu-merging.md) bu konuda ayrıntılı ele alınmıştır.

Bu sorunları nedeniyle uygulama Sihirbazı ile oluşturulan OLE belge uygulamaları en fazla dört ayrı menülerini ve Hızlandırıcı tablo kaynaklarını olabilir. Bunlar, aşağıdaki nedenlerden dolayı kullanılır:

|Kaynak adı|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------------|---------|
|IDR_MAINFRAME|Hiçbir dosya açık değilse bir MDI uygulamasında veya bir SDI uygulamasında açık dosyalar bağımsız olarak kullanılır. OLE dışı uygulamalarda kullanılan standart menü budur.|
|IDR_\<Proje > türü|Bir MDI uygulamasında açık dosya varsa kullanılır. Bir uygulama bağımsız olarak çalışırken kullanılır. OLE dışı uygulamalarda kullanılan standart menü budur.|
|IDR_\<Proje > TYPE_SRVR_IP|Bir nesne yerinde açık olduğunda sunucu ya da kapsayıcı tarafından kullanılır.|
|IDR_\<Proje > TYPE_SRVR_EMB|Yerinde etkinleştirme kullanmadan bir nesne açıldığında bir sunucu uygulaması tarafından kullanılır.|

Bu kaynak adlarının her biri bir menü ve genellikle Hızlandırıcı tablosunu temsil eder. Benzer bir düzen Uygulama Sihirbazı'nı oluşturulmaz MFC uygulamalarında kullanılması gerekir.

Aşağıdaki makaleler, kapsayıcılar, sunucuları ve menü yerinde etkinleştirme uygulamak için gerekli birleştirme ile ilgili konular açıklanmaktadır:

- [Menüler ve kaynaklar: Kapsayıcı ekleme](../mfc/menus-and-resources-container-additions.md)

- [Menüler ve kaynaklar: Sunucu ekleme](../mfc/menus-and-resources-server-additions.md)

- [Menüler ve kaynaklar: Menü birleştirme](../mfc/menus-and-resources-menu-merging.md)

## <a name="see-also"></a>Ayrıca bkz.

[OLE](../mfc/ole-in-mfc.md)
