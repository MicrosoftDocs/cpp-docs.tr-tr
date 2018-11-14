---
title: 'Sunucular: Sunucu Uygulama'
ms.date: 11/04/2016
helpviewer_keywords:
- servers, implementing
- OLE server applications [MFC], implementing OLE servers
ms.assetid: 5bd57e8e-3b23-4f23-9597-496fac2d24b5
ms.openlocfilehash: a5c89ff1256d557ef417b9e53ce76bbf1b5d6196
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518970"
---
# <a name="servers-implementing-a-server"></a>Sunucular: Sunucu Uygulama

Bu makalede, MFC Uygulama Sihirbazı görsel düzenleme sunucu uygulaması için oluşturduğu kodu açıklanmaktadır. Uygulama Sihirbazı'nı kullanmıyorsanız, bu makalede burada sunucu uygulaması uygulamak için kod yazmanız gereken alanları listeler.

Yeni bir sunucu uygulaması oluşturmak için Uygulama Sihirbazı'nı kullanıyorsanız, sizin için sunucu özgü kodu önemli ölçüde sağlar. Görsel düzenleme sunucusu işlevselliği varolan bir uygulamaya ekliyorsanız, gerekli sunucu kodun geri kalanını eklemeden önce Uygulama Sihirbazı'nı sağlamış kodu yinelenen gerekir.

Uygulama Sihirbazı'nı sağlayan sunucu kodu birkaç kategoride toplanabilir:

- Sunucu kaynaklarını tanımlama:

  - Sunucunun kendi penceresinde gömülü bir öğe düzenlenirken kullanılan menü kaynağı.

  - Sunucu yerinde etkin olduğunda kullanılan menü ve araç çubuğu kaynakları.

  Bu kaynaklar hakkında daha fazla bilgi için bkz. [menüler ve kaynaklar: sunucu ekleme](../mfc/menus-and-resources-server-additions.md).

- Bir öğe sınıfı tanımlayarak türetilen `COleServerItem`. Sunucu öğeleri hakkında daha ayrıntılı bilgi için bkz. [sunucular: sunucu öğeleri](../mfc/servers-server-items.md).

- Belge sınıfına temel sınıfını değiştirmek `COleServerDoc`. Daha fazla ayrıntı için bkz. [sunucular: sunucu belgeleri uygulama](../mfc/servers-implementing-server-documents.md).

- Çerçeve pencere sınıfını tanımlama türetilen `COleIPFrameWnd`. Daha fazla ayrıntı için bkz. [sunucular: yerinde çerçeve Windows uygulama](../mfc/servers-implementing-in-place-frame-windows.md).

- Windows kayıt defteri veritabanındaki sunucu uygulaması için bir giriş oluşturmak ve yeni bir sunucu örneğini OLE sistemiyle kaydediliyor. Bu konu hakkında daha fazla bilgi için bkz: [kayıt](../mfc/registration.md).

- Başlatma ve sunucu uygulaması başlatma. Bu konu hakkında daha fazla bilgi için bkz: [kayıt](../mfc/registration.md).

Daha fazla bilgi için [Coleserverıtem](../mfc/reference/coleserveritem-class.md), [COleServerDoc](../mfc/reference/coleserverdoc-class.md), ve [Coleıpframewnd](../mfc/reference/coleipframewnd-class.md) içinde *sınıf kitaplığı başvurusu*.

## <a name="see-also"></a>Ayrıca Bkz.

[Sunucular](../mfc/servers.md)<br/>
[Kapsayıcılar](../mfc/containers.md)<br/>
[Menüler ve Kaynaklar (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Kayıt](../mfc/registration.md)

