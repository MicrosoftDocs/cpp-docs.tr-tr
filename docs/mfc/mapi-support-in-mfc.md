---
description: "Daha fazla bilgi edinin: MFC 'de MAPI desteği"
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
ms.openlocfilehash: 289ad61894efd5c08d3a50d8c50e3ac6ee518a25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280761"
---
# <a name="mapi-support-in-mfc"></a>MFC'de MAPI Desteği

MFC, sınıfında Microsoft mesajlaşma uygulaması program arabirimi 'nin (MAPI) bir alt kümesi için destek sağlar `CDocument` . Özellikle, `CDocument` son kullanıcının makinesinde posta desteğinin bulunup bulunmadığını tespit eden üye işlevleri vardır ve bu durumda standart komut kimliği ID_FILE_SEND_MAIL olan posta Gönder komutunu etkinleştirin. Bu komut için MFC işleyici işlevi kullanıcının elektronik posta aracılığıyla belge göndermesini sağlar.

> [!TIP]
> MFC tüm MAPI işlev kümesini kapsüllemez olsa da, tıpkı doğrudan MFC programlarından Win32 API işlevleri çağırabilmeniz gibi doğrudan MAPI işlevlerini çağırabilirsiniz.

Uygulamanızda posta Gönder komutunun sağlanması çok kolaydır. MFC, bir belgeyi (yani, `CDocument` türetilmiş bir nesne) ek olarak paketleyip posta olarak gönderebilecek uygulamayı sağlar. Bu ek, belgenin içeriğini posta iletisine kaydeden (seri hale getirilen) bir dosya Kaydet komutuna eşdeğerdir. Bu uygulama, kullanıcıya e-posta adresine adres verme ve posta iletisine konu ve ileti metni ekleme fırsatını sağlamak için kullanıcının makinesinde posta istemcisini çağırır. Kullanıcılar kendi tanıdık posta uygulamalarının Kullanıcı arabirimini görür. Bu işlevsellik iki `CDocument` üye işlevi tarafından sağlanır: `OnFileSendMail` ve `OnUpdateFileSendMail` .

MAPI 'nin eki göndermek için dosyayı okuması gerekir. Uygulama, bir işlev çağrısı sırasında veri dosyasını açık olarak sakalıyorsa `OnFileSendMail` , dosyanın birden çok işlemin dosyaya erişmesine izin veren bir paylaşma modu ile açılması gerekir.

> [!NOTE]
> Sınıfının geçersiz kılma sürümü `OnFileSendMail` `COleDocument` bileşik belgeleri doğru şekilde işler.

#### <a name="to-implement-a-send-mail-command-with-mfc"></a>MFC ile posta Gönder komutunu uygulamak için

1. Komut KIMLIĞI ID_FILE_SEND_MAIL olan bir menü öğesi eklemek için Visual C++ menü düzenleyicisini kullanın.

   Bu komut KIMLIĞI, AFXRES. H içindeki Framework tarafından sağlanır. Komut herhangi bir menüye eklenebilir, ancak genellikle **Dosya** menüsüne eklenir.

1. Aşağıdakileri belgenizin ileti eşlemesine el ile ekleyin:

   [!code-cpp[NVC_MFCDocView#9](codesnippet/cpp/mapi-support-in-mfc_1.cpp)]

    > [!NOTE]
    >  Bu ileti eşlemesi ya da öğesinden türetilmiş bir belge için `CDocument` çalışır `COleDocument` ; ileti eşlemesi türetilmiş belge sınıfınız içinde olsa bile, her iki durumda da doğru temel sınıfı alır.

1. Uygulamanızı oluşturun.

Posta desteği varsa, MFC menü öğesini ile `OnUpdateFileSendMail` ve daha sonra komutunu ile işlem işlemlerine izin vermez `OnFileSendMail` . Posta desteği yoksa, MFC Kullanıcı onu görmemesi için menü öğesini otomatik olarak kaldırır.

> [!TIP]
> Daha önce açıklandığı gibi ileti eşleme girdilerini el ile eklemek yerine, iletileri işlevlere eşlemek için sınıf [sınıfı sihirbazını](reference/mfc-class-wizard.md) kullanabilirsiniz. Daha fazla bilgi için bkz. [Iletileri IŞLEVLERE eşleme](reference/mapping-messages-to-functions.md).

İlgili bilgiler için bkz. [MAPI](mapi.md) genel bakış.

`CDocument`MAPI 'yi etkinleştiren üye işlevleri hakkında daha fazla bilgi için bkz.:

- [CDocument:: OnFileSendMail](reference/cdocument-class.md#onfilesendmail)

- [CDocument:: OnUpdateFileSendMail](reference/cdocument-class.md#onupdatefilesendmail)

- [Cotadocument:: OnFileSendMail](reference/coledocument-class.md#onfilesendmail)

## <a name="see-also"></a>Ayrıca bkz.

[MAPI](mapi.md)
