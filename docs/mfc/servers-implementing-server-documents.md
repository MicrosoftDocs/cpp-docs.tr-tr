---
title: 'Sunucular: Sunucu belgeleri uygulama | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE server applications [MFC], managing server documents
- OLE server applications [MFC], implementing OLE servers
- servers, server documents
- server documents [MFC], implementing
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5d2a3f42522ecceb09261de7437446f0d5be2d6f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="servers-implementing-server-documents"></a>Sunucular: Sunucu Belgeleri Uygulama
Bu makalede, Uygulama Sihirbazı'nda OLE sunucu seçeneği belirtmediyseniz server Belge başarıyla uygulamak için gerçekleştirmeniz gereken adımlar açıklanmaktadır.  
  
#### <a name="to-define-a-server-document-class"></a>Sunucu belge sınıfı tanımlamak için  
  
1.  Belge sınıfından türetilen `COleServerDoc` yerine **CDocument**.  
  
2.  Türetilen bir sunucu öğe sınıfı oluşturmak `COleServerItem`.  
  
3.  Uygulama `OnGetEmbeddedItem` server belge sınıfınızın üye işlevi.  
  
     `OnGetEmbeddedItem`bir kapsayıcı uygulama kullanıcı oluşturduğunda veya katıştırılmış bir öğe düzenler olarak adlandırılır. Tüm belgeyi temsil eden bir öğe döndürmelidir. Bu bir nesne olmalıdır, `COleServerItem`-türetilmiş sınıf.  
  
4.  Geçersiz kılma `Serialize` belgesinin içeriğini serileştirmek için üye işlevi. Yerel veri belgenizi temsil etmek için kullanmıyorsanız sunucu öğeleri listesi serileştirmek gerekmez. Daha fazla bilgi için bkz: *uygulama sunucusu öğeleri* makalede [sunucular: sunucu öğeleri](../mfc/servers-server-items.md).  
  
 Bir sunucu belge oluşturulduğunda framework belge OLE sistem DLL'leri ile otomatik olarak kaydeder. Bu sunucu belgeleri tanımlamak DLL'leri sağlar.  
  
 Daha fazla bilgi için bkz: [COleServerItem](../mfc/reference/coleserveritem-class.md) ve [COleServerDoc](../mfc/reference/coleserverdoc-class.md) içinde *sınıf kitaplığı başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sunucuları](../mfc/servers.md)   
 [Sunucular: Sunucu öğeleri](../mfc/servers-server-items.md)   
 [Sunucular: sunucu uygulama](../mfc/servers-implementing-a-server.md)   
 [Sunucular: Yerinde çerçeve pencereleri uygulama](../mfc/servers-implementing-in-place-frame-windows.md)

