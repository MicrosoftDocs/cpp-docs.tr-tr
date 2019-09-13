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
ms.openlocfilehash: e46eaf2bd84d4cebd2215ab2752ce3bb8e1eb9b3
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907674"
---
# <a name="mapi-support-in-mfc"></a>MFC'de MAPI Desteği

MFC, sınıfında `CDocument`Microsoft mesajlaşma uygulaması program ARABIRIMI 'nin (MAPI) bir alt kümesi için destek sağlar. Özellikle, `CDocument` son kullanıcının makinesinde posta desteğinin bulunup bulunmadığını tespit eden üye işlevleri vardır ve bu durumda standart komut kimliği ID_FILE_SEND_MAIL olan posta Gönder komutunu etkinleştirin. Bu komut için MFC işleyici işlevi kullanıcının elektronik posta aracılığıyla belge göndermesini sağlar.

> [!TIP]
>  MFC tüm MAPI işlev kümesini kapsüllemez olsa da, tıpkı doğrudan MFC programlarından Win32 API işlevleri çağırabilmeniz gibi doğrudan MAPI işlevlerini çağırabilirsiniz.

Uygulamanızda posta Gönder komutunun sağlanması çok kolaydır. MFC, bir belgeyi (yani, `CDocument`türetilmiş bir nesne) ek olarak paketleyip posta olarak gönderebilecek uygulamayı sağlar. Bu ek, belgenin içeriğini posta iletisine kaydeden (seri hale getirilen) bir dosya Kaydet komutuna eşdeğerdir. Bu uygulama, kullanıcıya e-posta adresine adres verme ve posta iletisine konu ve ileti metni ekleme fırsatını sağlamak için kullanıcının makinesinde posta istemcisini çağırır. Kullanıcılar kendi tanıdık posta uygulamalarının Kullanıcı arabirimini görür. Bu işlevsellik iki `CDocument` üye işlevi tarafından sağlanır: `OnFileSendMail` ve `OnUpdateFileSendMail`.

MAPI 'nin eki göndermek için dosyayı okuması gerekir. Uygulama, bir `OnFileSendMail` işlev çağrısı sırasında veri dosyasını açık olarak sakalıyorsa, dosyanın birden çok işlemin dosyaya erişmesine izin veren bir paylaşma modu ile açılması gerekir.

> [!NOTE]
>  `OnFileSendMail` Sınıfının`COleDocument` geçersiz kılma sürümü bileşik belgeleri doğru şekilde işler.

#### <a name="to-implement-a-send-mail-command-with-mfc"></a>MFC ile posta Gönder komutunu uygulamak için

1. Komut KIMLIĞI ID_FILE_SEND_MAIL C++ olan bir menü öğesi eklemek için görsel menü düzenleyicisini kullanın.

   Bu komut KIMLIĞI, AFXRES içindeki Framework tarafından sağlanır. Olsun. Komut herhangi bir menüye eklenebilir, ancak genellikle **Dosya** menüsüne eklenir.

1. Aşağıdakileri belgenizin ileti eşlemesine el ile ekleyin:

   [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/cpp/mapi-support-in-mfc_1.cpp)]

    > [!NOTE]
    >  Bu ileti eşlemesi ya da `CDocument` `COleDocument` öğesinden türetilmiş bir belge için çalışır; ileti eşlemesi türetilmiş belge sınıfınız içinde olsa bile, her iki durumda da doğru temel sınıfı alır.

1. Uygulamanızı oluşturun.

Posta desteği varsa, mfc menü öğesini ile `OnUpdateFileSendMail` ve daha sonra komutunu ile `OnFileSendMail`işlem işlemlerine izin vermez. Posta desteği yoksa, MFC Kullanıcı onu görmemesi için menü öğesini otomatik olarak kaldırır.

> [!TIP]
>  Daha önce açıklandığı gibi ileti eşleme girdilerini el ile eklemek yerine, iletileri işlevlere eşlemek için sınıf [sınıfı sihirbazını](reference/mfc-class-wizard.md) kullanabilirsiniz. Daha fazla bilgi için bkz. [Iletileri IŞLEVLERE eşleme](../mfc/reference/mapping-messages-to-functions.md).

İlgili bilgiler için bkz. [MAPI](../mfc/mapi.md) genel bakış.

MAPI 'yi etkinleştiren `CDocument` üye işlevleri hakkında daha fazla bilgi için bkz.:

- [CDocument:: OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)

- [CDocument:: OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)

- [Cotadocument:: OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)

## <a name="see-also"></a>Ayrıca bkz.

[MAPI](../mfc/mapi.md)
