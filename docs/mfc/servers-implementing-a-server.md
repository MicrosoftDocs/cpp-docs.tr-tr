---
description: 'Daha fazla bilgi edinin: sunucular: sunucu uygulama'
title: 'Sunucular: Sunucu Uygulama'
ms.date: 11/04/2016
helpviewer_keywords:
- servers, implementing
- OLE server applications [MFC], implementing OLE servers
ms.assetid: 5bd57e8e-3b23-4f23-9597-496fac2d24b5
ms.openlocfilehash: 3ced10f88ce062ab571841610ba4b000571835b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217386"
---
# <a name="servers-implementing-a-server"></a>Sunucular: Sunucu Uygulama

Bu makalede, MFC Uygulama Sihirbazı 'Nın bir görsel düzenlenme sunucusu uygulaması için oluşturduğu kod açıklanmaktadır. Uygulama sihirbazını kullanmıyorsanız, bu makalede bir sunucu uygulaması uygulamak için kod yazmanız gereken bölgeler listelenir.

Yeni bir sunucu uygulaması oluşturmak için uygulama Sihirbazı 'nı kullanıyorsanız, sizin için sunucuya özgü önemli bir kod sağlar. Var olan bir uygulamaya görsel olarak düzenlenen sunucu işlevselliği ekliyorsanız, gerekli sunucu kodunun geri kalanını eklemeden önce uygulama Sihirbazı 'nın sağlandığı kodu çoğaltmalısınız.

Uygulama sihirbazının sağladığı sunucu kodu birkaç kategoride yer almaktadır:

- Sunucu kaynaklarını tanımlama:

  - Sunucu, bir katıştırılmış öğeyi kendi penceresinde düzenlemekte kullanılan menü kaynağı.

  - Sunucu etkin olduğunda kullanılan menü ve araç çubuğu kaynakları.

  Bu kaynaklarla ilgili daha fazla bilgi için bkz. [menüler ve kaynaklar: sunucu eklemeleri](../mfc/menus-and-resources-server-additions.md).

- Öğesinden türetilmiş bir öğe sınıfını tanımlama `COleServerItem` . Sunucu öğeleri hakkında daha fazla bilgi için bkz. [sunucular: sunucu öğeleri](../mfc/servers-server-items.md).

- Belge sınıfının taban sınıfını olarak değiştirme `COleServerDoc` . Daha fazla ayrıntı için bkz. [sunucular: sunucu belgeleri uygulama](../mfc/servers-implementing-server-documents.md).

- Öğesinden türetilmiş bir çerçeve pencere sınıfı tanımlama `COleIPFrameWnd` . Daha fazla ayrıntı için bkz. [sunucular: In-Place çerçeve pencereleri uygulama](../mfc/servers-implementing-in-place-frame-windows.md).

- Windows kayıt veritabanında sunucu uygulaması için bir giriş oluşturma ve sunucunun yeni örneğini OLE sistemiyle kaydetme. Bu konu hakkında daha fazla bilgi için bkz. [kayıt](../mfc/registration.md).

- Sunucu uygulamasını başlatma ve başlatma. Bu konu hakkında daha fazla bilgi için bkz. [kayıt](../mfc/registration.md).

Daha fazla bilgi için bkz. *sınıf kitaplığı başvurusunda* [Copaserverıtem](../mfc/reference/coleserveritem-class.md), [Copaserverdoc](../mfc/reference/coleserverdoc-class.md)ve [cotaipframewnd](../mfc/reference/coleipframewnd-class.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Sunucular](../mfc/servers.md)<br/>
[Kapsayıcılar](../mfc/containers.md)<br/>
[Menüler ve kaynaklar (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Kaydını](../mfc/registration.md)
