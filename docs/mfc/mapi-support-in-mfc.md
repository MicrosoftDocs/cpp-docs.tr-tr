---
title: MFC'de MAPI Desteği
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, MAPI support
- MAPI support in MFC
- CDocument class [MFC], and MAPI
- OnUpdateFileSendMail method [MFC]
- MAPI, MFC
- OnFileSendMail method [MFC]
ms.assetid: cafbecb1-0427-4077-b4b8-159bae5b49b8
ms.openlocfilehash: 564ce185758d25682a88f18a23b0b11afc84a4d0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567159"
---
# <a name="mapi-support-in-mfc"></a>MFC'de MAPI Desteği

MFC, Microsoft ileti uygulama programı arabirimi (MAPI) sınıfındaki bir alt kümesi için destek sağlayan `CDocument`. Özellikle, `CDocument` posta desteği son kullanıcı makinesinde mevcut olup olmadığını belirlemek üye işlevleri vardır ve bu durumda, standart komut Kimliğine sahip ID_FILE_SEND_MAIL posta Gönder komutu etkinleştirme. Bu komut için MFC işleyici işlevi, kullanıcı bir belgeyi elektronik posta yoluyla göndermeyi sağlar.

> [!TIP]
>  MFC kümesinin tümü MAPI işlevi kapsülleyen değil de doğrudan MFC programlarından Win32 API işlevleri çağırabilir gibi hala MAPI işlevleri doğrudan çağırabilirsiniz.

Posta Gönder sağlayan komut, uygulamanızda çok kolaydır. MFC belge paketlemek için bir uygulama sağlar (diğer bir deyişle, bir `CDocument`-türetilmiş bir nesneye) ek olarak ve posta gönderin. Bu ek kaydeder dosyasını kaydetmek bir komuta denktir (serileştiren) e-posta iletisi belgenin içeriği. Bu uygulama, kullanıcıya e-posta adresini ve posta iletisine konu ve ileti metni eklemek için bir fırsat vermek için posta istemci makinesi üzerinde bağlı çağırır. Kullanıcılar kendi tanıdık posta uygulamanın kullanıcı arabirimini görür. İki tarafından sağlanan bu işlevsellik `CDocument` üye işlevleri: `OnFileSendMail` ve `OnUpdateFileSendMail`.

MAPI eki göndermek için dosyayı okumak gerekir. Uygulama, veri dosyası açık sırasında tutarsa bir `OnFileSendMail` işlev çağrısı dosyanın dosyaya erişmek birden çok işlem sağlayan bir paylaşım modu ile açılması gerekiyor.

> [!NOTE]
>  Bir geçersiz kılma sürümünü `OnFileSendMail` sınıfı için `COleDocument` doğru tanıtıcıları belgeleri bileşik.

#### <a name="to-implement-a-send-mail-command-with-mfc"></a>MFC ile bir posta Gönder komutu uygulamak için

1. ID_FILE_SEND_MAIL komut Kimliğine sahip bir menü öğesi eklemek için Visual C++ menü düzenleyicisini kullanın.

   Bu komut kimliği AFXRES framework tarafından sağlanır. H Komut için herhangi bir menüsü eklenebilir, ancak genellikle eklenir **dosya** menüsü.

1. El ile belgenizin ileti eşlemesi için aşağıdakileri ekleyin:

   [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/cpp/mapi-support-in-mfc_1.cpp)]

    > [!NOTE]
    >  Öğesinden türetilen bir belge için bu ileti eşlemesi çalışır `CDocument` veya `COleDocument` — ileti eşlemesi türetilmiş belge sınıfınızda olsa bile, her iki durumda da doğru temel sınıfı alır.

1. Uygulamanızı oluşturun.

E-posta destek varsa, MFC, menü öğesiyle sağlar `OnUpdateFileSendMail` ve daha sonra bir komutla işler `OnFileSendMail`. E-posta desteği kullanılabilir durumda değilse, kullanıcı göremez şekilde MFC menü öğesine otomatik olarak kaldırır.

> [!TIP]
>  El ile daha önce açıklandığı gibi ileti eşlemesi girişleri eklemek yerine, İşlevler için ileti eşlemesi için sınıf Özellikler penceresini kullanabilirsiniz. Daha fazla bilgi için [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md).

İlgili bilgiler için bkz. [MAPI](../mfc/mapi.md) genel bakış.

Hakkında daha fazla bilgi için `CDocument` MAPI, etkinleştirme üye işlevleri bakın:

- [CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)

- [CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)

- [COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)

## <a name="see-also"></a>Ayrıca Bkz.

[MAPI](../mfc/mapi.md)

