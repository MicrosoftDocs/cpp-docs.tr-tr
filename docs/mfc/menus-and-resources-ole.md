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
ms.openlocfilehash: e705f28476df7b594f9648aee8317759211c66c9
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626207"
---
# <a name="menus-and-resources-ole"></a>Menüler ve Kaynaklar (OLE)

Bu makale grubunda, MFC OLE belge uygulamalarında menülerin ve kaynakların kullanımı açıklanmaktadır.

OLE görsel düzenlemesi, hem kapsayıcı hem de sunucu (bileşen) uygulamalarının başlatılabileceği ve kullanılabileceği birçok mod olduğundan, menü ve OLE belge uygulamaları tarafından sunulan diğer kaynaklara ek gereksinimler koyar. Örneğin, bir tam sunucu uygulaması şu üç moddan birinde çalıştırılabilir:

- Tek başına.

- Yerinde, bir kapsayıcı bağlamı içindeki bir öğeyi düzenlemeniz için.

- Öğesini, kapsayıcının bağlamı dışında, genellikle ayrı bir pencerede düzenlenmek üzere açın.

Bu, uygulamanın her olası modu için birer tane olmak üzere üç ayrı menü düzeni gerektirir. Hızlandırma tabloları her yeni mod için de gereklidir. Bir kapsayıcı uygulaması yerinde etkinleştirmeyi destekleyebilir veya desteklemiyor olabilir; varsa, yeni bir menü yapısına ve ilişkili Hızlandırıcı tablolarına ihtiyaç duyuyor.

Yerinde etkinleştirme, kapsayıcı ve sunucu uygulamalarının menü, araç çubuğu ve durum çubuğu alanı için anlaşmalıdır. Tüm kaynaklar bu şekilde göz önünde bulundurularak tasarlanmalıdır. [Menüler ve kaynaklar: menü birleştirme](menus-and-resources-menu-merging.md) , bu konuyu ayrıntılı bir şekilde ele alır.

Bu sorunlar nedeniyle, uygulama sihirbazıyla oluşturulan OLE belge uygulamaları en fazla dört ayrı menü ve Hızlandırıcı tablo kaynağına sahip olabilir. Bunlar aşağıdaki nedenlerle kullanılır:

|Kaynak adı|Kullanım|
|-------------------|---------|
|IDR_MAINFRAME|Açık dosyalar ne olursa olsun bir MDI uygulamasında veya bir SDI uygulamasında kullanılabilir. Bu, OLE olmayan uygulamalarda kullanılan standart bir menü olur.|
|IDR_ \<project> türü|Dosyalar açıksa MDI uygulamasında kullanılır. Bir uygulama tek başına çalıştırıldığında kullanılır. Bu, OLE olmayan uygulamalarda kullanılan standart bir menü olur.|
|IDR_ \<project> TYPE_SRVR_IP|Bir nesne yerinde açıldığında sunucu veya kapsayıcı tarafından kullanılır.|
|IDR_ \<project> TYPE_SRVR_EMB|Bir nesne yerinde etkinleştirme kullanılmadan açılırsa bir sunucu uygulaması tarafından kullanılır.|

Bu kaynak adlarından her biri, bir menüyü ve genellikle bir Hızlandırıcı tablosunu temsil eder. Benzer bir düzen, uygulama Sihirbazı ile oluşturulmamış MFC uygulamalarında kullanılmalıdır.

Aşağıdaki makalelerde kapsayıcılar, sunucular ve yerinde etkinleştirmeyi uygulamak için gereken menü birleştirme ile ilgili konular ele alınmaktadır:

- [Menüler ve Kaynaklar: Kapsayıcı Ekleme](menus-and-resources-container-additions.md)

- [Menüler ve Kaynaklar: Sunucu Ekleme](menus-and-resources-server-additions.md)

- [Menüler ve Kaynaklar: Menü Birleştirme](menus-and-resources-menu-merging.md)

## <a name="see-also"></a>Ayrıca bkz.

[OLE](ole-in-mfc.md)
