---
description: 'Daha fazla bilgi edinin: sunucular: sunucu belgeleri uygulama'
title: 'Sunucular: Sunucu Belgeleri Uygulama'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], managing server documents
- OLE server applications [MFC], implementing OLE servers
- servers, server documents
- server documents [MFC], implementing
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
ms.openlocfilehash: b8843d3e2ac662cbb018a3063c9f04f5dd8d6f10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217334"
---
# <a name="servers-implementing-server-documents"></a>Sunucular: Sunucu Belgeleri Uygulama

Bu makalede, uygulama sihirbazında OLE sunucusu seçeneğini belirtmediyseniz bir sunucu belgesini başarıyla uygulamak için gerçekleştirmeniz gereken adımlar açıklanır.

#### <a name="to-define-a-server-document-class"></a>Bir sunucu belge sınıfı tanımlamak için

1. Yerine belge sınıfınızı türetebilirsiniz `COleServerDoc` `CDocument` .

1. Öğesinden türetilmiş bir sunucu öğesi sınıfı oluşturun `COleServerItem` .

1. `OnGetEmbeddedItem`Sunucu belge sınıfınızın üye işlevini uygulayın.

   `OnGetEmbeddedItem` bir kapsayıcı uygulamasının kullanıcısı katıştırılmış bir öğe oluşturduğunda veya düzenleayarlandığında çağrılır. Tüm belgeyi temsil eden bir öğe döndürmelidir. Bu, türetilmiş sınıfınızın bir nesnesi olmalıdır `COleServerItem` .

1. `Serialize`Belgenin içeriğini seri hale getirmek için üye işlevini geçersiz kılın. Belgenizde yerel verileri temsil etmek için kullanmadığınız durumlar dışında, sunucu öğelerinin listesini serileştirmek zorunda değilsiniz. Daha fazla bilgi için bkz. Makale [sunucuları: sunucu öğeleri](../mfc/servers-server-items.md)Içindeki *sunucu öğelerini uygulama* .

Bir sunucu belgesi oluşturulduğunda, çerçeve otomatik olarak belgeyi OLE sistem dll 'Leriyle kaydeder. Bu, dll 'Lerin sunucu belgelerini belirlemesine izin verir.

Daha fazla bilgi için bkz. *sınıf kitaplığı başvurusunda* [Copaserverıtem](../mfc/reference/coleserveritem-class.md) ve [copaserverdoc](../mfc/reference/coleserverdoc-class.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Sunucular](../mfc/servers.md)<br/>
[Sunucular: sunucu öğeleri](../mfc/servers-server-items.md)<br/>
[Sunucular: sunucu uygulama](../mfc/servers-implementing-a-server.md)<br/>
[Sunucular: In-Place çerçeve pencerelerini uygulama](../mfc/servers-implementing-in-place-frame-windows.md)
