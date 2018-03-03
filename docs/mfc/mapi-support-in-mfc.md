---
title: "MFC içinde MAPI desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC, MAPI support
- MAPI support in MFC
- CDocument class [MFC], and MAPI
- OnUpdateFileSendMail method [MFC]
- MAPI, MFC
- OnFileSendMail method [MFC]
ms.assetid: cafbecb1-0427-4077-b4b8-159bae5b49b8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6cc1670559354628127729724300399d5f003ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mapi-support-in-mfc"></a>MFC'de MAPI Desteği
MFC sağlayan bir alt kümesini, Microsoft ileti uygulama programı arabirimi (MAPI) sınıfında desteği **CDocument**. Özellikle, **CDocument** posta desteği son kullanıcının makinede mevcut olup olmadığını üye işlevleri vardır ve bu durumda, standart komut Kimliğine sahip bir posta Gönder komutu etkinleştirmek **ID_FILE_SEND_MAIL**. Bu komut için MFC işleyici işlevi bir belgeyi elektronik posta ile göndermek kullanıcının sağlar.  
  
> [!TIP]
>  MFC MAPI işlevi tamamına kapsülleyen değil de, Win32 API işlevlerini doğrudan MFC programlardan çağırabilirsiniz gibi hala MAPI işlevleri doğrudan çağırabilirsiniz.  
  
 Posta Gönder sağlayan komut, uygulamanızda çok kolaydır. MFC belge paketlemek için uygulama sağlar (diğer bir deyişle, bir **CDocument**-nesne türetilmiş) ek olarak posta gönderin. Bu ek kaydeder dosyasını kaydedin bir komutu eşdeğerdir (serileştiren) posta iletisi belgenin içeriği. Bu uygulama, kullanıcının posta adresini ve posta iletisine konu ve ileti metnini eklemek için Fırsat vermek için posta istemci kullanıcının makinesinde bağlı çağırır. Kullanıcılar kendi tanıdık posta uygulamanın kullanıcı arabiriminde bakın. Bu işlev iki tarafından sağlanan **CDocument** üye işlevleri: `OnFileSendMail` ve `OnUpdateFileSendMail`.  
  
 MAPI eki gönderilecek dosyanın okuması gerekir. Uygulamanın kendi veri dosyası sırasında açık tutar, bir `OnFileSendMail` işlev çağrısı, dosyanın gerekiyor dosyaya erişmek birden çok işlem sağlayan bir paylaşım modu ile açılacak.  
  
> [!NOTE]
>  Bir geçersiz kılma sürümü `OnFileSendMail` sınıfı için `COleDocument` doğru tanıtıcıları belgeleri bileşik.  
  
#### <a name="to-implement-a-send-mail-command-with-mfc"></a>MFC posta Gönder komutuyla uygulamak için  
  
1.  Komut Kimliğine sahip bir menü öğesi eklemek için Visual C++ Menü Düzenleyici kullanın **ID_FILE_SEND_MAIL**.  
  
     Bu komut kimliği AFXRES framework tarafından sağlanır. H. Tüm menü komutu eklenebilir, ancak genellikle eklendiğinden **dosya** menüsü.  
  
2.  El ile belgenizin ileti eşlemesi için aşağıdakileri ekleyin:  
  
     [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/cpp/mapi-support-in-mfc_1.cpp)]  
  
    > [!NOTE]
    >  Bu ileti eşlemesi herhangi birinden türetilmiş bir belge için çalışır **CDocument** veya **COleDocument** — ileti eşlemesi türetilmiş belge sınıfınızda olsa bile, her iki durumda da doğru temel sınıfı alır.  
  
3.  Uygulamanızı oluşturun.  
  
 Posta desteği varsa, MFC Menü öğesiyle etkinleştirir `OnUpdateFileSendMail` ve daha sonra komutuyla işler `OnFileSendMail`. Posta desteği kullanılabilir durumda değilse, kullanıcı bunu göremez için MFC menü öğesine otomatik olarak kaldırır.  
  
> [!TIP]
>  İleti eşleme girdilerini daha önce açıklandığı gibi el ile ekleme yerine iletileri işlevlere eşleme için sınıf Özellikler penceresini kullanabilirsiniz. Daha fazla bilgi için bkz: [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md).  
  
 İlgili bilgi için bkz: [MAPI](../mfc/mapi.md) genel bakış.  
  
 Hakkında daha fazla bilgi için **CDocument** MAPI, etkinleştirme üye işlevleri bakın:  
  
-   [CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)  
  
-   [CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)  
  
-   [COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MAPI](../mfc/mapi.md)

