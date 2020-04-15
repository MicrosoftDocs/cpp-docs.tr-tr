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
ms.openlocfilehash: 3024f744407cf33c8dfad8a6f7af736e0f8061ef
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356995"
---
# <a name="mapi-support-in-mfc"></a>MFC'de MAPI Desteği

MFC, microsoft ileti uygulama programı arabiriminin (MAPI) sınıfındaki `CDocument`bir alt kümesi için destek sağlar. Özellikle, `CDocument` posta desteğinin son kullanıcının makinesinde bulunup bulunmadığını belirleyen ve varsa standart komut kimliği ID_FILE_SEND_MAIL olan bir Posta Gönder komutunu etkinleştiren üye işlevlere sahiptir. Bu komutun MFC işleyicisi işlevi, kullanıcının elektronik posta yoluyla belge göndermesine olanak tanır.

> [!TIP]
> MFC mapi işlev kümesinin tamamını kapsüllemese de, Win32 API işlevlerini doğrudan MFC programlarından çağırabileceğiniz gibi MAPI işlevlerini doğrudan arayabilirsiniz.

Uygulamanızda Posta Gönder komutunu sağlamak çok kolaydır. MFC, bir belgeyi (yani türetilmiş nesneyi) `CDocument`ek olarak paketlemek ve posta olarak göndermek için uygulama sağlar. Bu ek, belgenin içeriğini posta iletisine kaydeden (seri hale getiren) dosya kaydet komutuna eşdeğerdir. Bu uygulama, kullanıcının makinesindeki posta istemcisine, kullanıcıya postaadresine adres verme ve posta iletisine konu ve ileti metni ekleme fırsatı vermesini çağırır. Kullanıcılar tanıdık posta uygulamalarının kullanıcı arabirimini görürler. Bu işlevsellik iki `CDocument` üye işlev `OnFileSendMail` `OnUpdateFileSendMail`tarafından sağlanır: ve .

MAPI eki göndermek için dosyayı okumak gerekir. Uygulama bir `OnFileSendMail` işlev çağrısı sırasında veri dosyasını açık tutarsa, dosyanın birden çok işleme dosyaya erişmesine izin veren bir paylaşım moduyla açılması gerekir.

> [!NOTE]
> For sınıfının `OnFileSendMail` `COleDocument` geçersiz bir sürümü bileşik belgeleri doğru işler.

#### <a name="to-implement-a-send-mail-command-with-mfc"></a>MFC ile Posta Gönder komutu uygulamak için

1. Komut kimliği ID_FILE_SEND_MAIL bir menü öğesi eklemek için Visual C++ menü düzenleyicisini kullanın.

   Bu komut kimliği AFXRES çerçevesinde sağlanır. H. Komut herhangi bir menüye eklenebilir, ancak genellikle **Dosya** menüsüne eklenir.

1. Belgenizin ileti eşlemiiçin aşağıdakileri el ile ekleyin:

   [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/cpp/mapi-support-in-mfc_1.cpp)]

    > [!NOTE]
    >  Bu ileti eşlemi, türemiş belge sınıfınızda olsa bile, her iki durumda da doğru taban sınıfalır `CDocument` veya `COleDocument` türetilen bir belge için çalışır.

1. Uygulamanızı oluşturun.

Posta desteği varsa, MFC menü öğenizi `OnUpdateFileSendMail` etkinleştirir ve `OnFileSendMail`daha sonra komutu . Posta desteği kullanılamıyorsa, MFC menü öğenizi otomatik olarak kaldırır, böylece kullanıcı bunu görmez.

> [!TIP]
> İleti eşlemi girişlerini daha önce açıklandığı gibi el ile eklemek yerine, iletileri işlevlerle eşlemek için [Sınıf Sihirbazı'nı](reference/mfc-class-wizard.md) kullanabilirsiniz. Daha fazla bilgi için Bkz. [İşlevlerle İlgili İletileri Eşleme.](../mfc/reference/mapping-messages-to-functions.md)

İlgili bilgiler için [MAPI](../mfc/mapi.md) genel görünümüne bakın.

MAPI'yi `CDocument` etkinleştiren üye işlevler hakkında daha fazla bilgi için bkz:

- [Kdocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)

- [Kdocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)

- [COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)

## <a name="see-also"></a>Ayrıca bkz.

[MAPI](../mfc/mapi.md)
