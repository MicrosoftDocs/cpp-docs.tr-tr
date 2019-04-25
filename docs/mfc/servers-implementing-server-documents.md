---
title: 'Sunucular: Sunucu belgeleri uygulama'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], managing server documents
- OLE server applications [MFC], implementing OLE servers
- servers, server documents
- server documents [MFC], implementing
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
ms.openlocfilehash: 17ced1cdb0b40b13fbda68150030efde5735ba7b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307919"
---
# <a name="servers-implementing-server-documents"></a>Sunucular: Sunucu belgeleri uygulama

Bu makalede Uygulama Sihirbazı'nda OLE sunucu seçeneği belirtmediyseniz sunucu belgesinin başarıyla uygulamak için gerçekleştirmeniz gereken adımlar açıklanmaktadır.

#### <a name="to-define-a-server-document-class"></a>Sunucu belge sınıfı tanımlamak için

1. Belge sınıfından türetilir `COleServerDoc` yerine `CDocument`.

1. Bir sunucu öğesi sınıfından türetilen oluşturma `COleServerItem`.

1. Uygulama `OnGetEmbeddedItem` sunucu belge sınıfının üye işlevi.

   `OnGetEmbeddedItem` bir kapsayıcı uygulamasının kullanıcı oluşturur veya düzenler gömülü bir öğe adı verilir. Tüm belgeyi temsil eden bir öğe döndürmesi gerekir. Bu nesnenin olmalıdır, `COleServerItem`-türetilmiş sınıf.

1. Geçersiz kılma `Serialize` belgesinin içeriğini serileştirmek için üye işlevi. Yerel veri belge içinde temsil etmek için kullanmıyorsanız sunucu öğelerin listesini seri hale gerekmez. Daha fazla bilgi için *uygulama sunucu öğeleri* makaledeki [sunucuları: Sunucu öğeleri](../mfc/servers-server-items.md).

Sunucu belgesinin oluşturulduğunda framework belge OLE sistem DLL'lerini otomatik olarak kaydeder. Bu sunucu belgeleri tanımlamak DLL'leri sağlar.

Daha fazla bilgi için [Coleserverıtem](../mfc/reference/coleserveritem-class.md) ve [COleServerDoc](../mfc/reference/coleserverdoc-class.md) içinde *sınıf kitaplığı başvurusu*.

## <a name="see-also"></a>Ayrıca bkz.

[Sunucular](../mfc/servers.md)<br/>
[Sunucular: Sunucu öğeleri](../mfc/servers-server-items.md)<br/>
[Sunucular: Sunucu uygulama](../mfc/servers-implementing-a-server.md)<br/>
[Sunucular: Yerinde çerçeve Windows uygulama](../mfc/servers-implementing-in-place-frame-windows.md)
