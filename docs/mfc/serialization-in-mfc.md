---
title: MFC'de Seri Hale Getirme
ms.date: 11/04/2016
helpviewer_keywords:
- collection classes [MFC], serialization
- bypassing serialization [MFC]
- MFC, serialization
- serialization [MFC], MFC
- serialization [MFC], bypassing
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
ms.openlocfilehash: eca4d0357977bc7ef21063718c738ae5bd8e7431
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372742"
---
# <a name="serialization-in-mfc"></a>MFC'de Seri Hale Getirme

Bu makalede, microsoft hazırlık sınıf kitaplığı (MFC) sağlanan serileştirme mekanizması, nesnelerin programınızın çalışır arasında devam etmesine izin açıklar.

Serileştirme, bir nesneyi disk dosyası gibi kalıcı bir depolama ortamına veya nesneden yazma veya okuma işlemidir. Serileştirme, bir programın yürütülmesi sırasında veya yürütülmesi nden sonra yapılandırılmış verilerin (C++ sınıfları veya yapıları gibi) durumunu korumak istendiği durumlar için idealdir. MFC tarafından sağlanan serileştirme nesnelerinin kullanılması, bunun standart ve tutarlı bir şekilde gerçekleşmesine olanak sağlayarak kullanıcıyı dosya işlemlerini elle gerçekleştirme gereksiniminden uzak tutar.

MFC, sınıfta `CObject`serileştirme için yerleşik destek sağlar. Böylece, türetilen `CObject` tüm sınıflar `CObject`'serileştirme protokolü yararlanabilir.

Serileştirmenin temel fikri, bir nesnenin genellikle üye değişkenlerin değeriyle gösterilen geçerli durumunu kalıcı depolamaya yazabilmesidir. Daha sonra, nesne, nesnenin durumunu depolamadan okuyarak veya deserializing tarafından yeniden oluşturulabilir. Serileştirme, nesne işaretçilerinin tüm ayrıntılarını ve bir nesneyi serileştirdiğinizde kullanılan nesnelere gelen dairesel başvuruları işler. Önemli bir nokta, nesnenin kendisinin kendi durumunu okuma ve yazmadan sorumlu olmasıdır. Bu nedenle, bir sınıfın serileştirilebilir olabilmesi için temel serileştirme işlemlerini uygulaması gerekir. Makalelerin Serileştirme grubunda gösterildiği gibi, bu işlevselliği bir sınıfa eklemek kolaydır.

MFC, `CArchive` seri hale getirilecek nesne ile depolama ortamı arasında aracı olarak sınıfın bir nesnesini kullanır. Bu nesne her zaman `CFile` dosya adı ve istenen işlemin okuma veya yazma olup olmadığı da dahil olmak üzere serileştirme için gerekli bilgileri aldığı bir nesneyle ilişkilidir. Serileştirme işlemini gerçekleştiren nesne, `CArchive` depolama ortamının yapısına bakılmaksızın nesneyi kullanabilir.

Bir `CArchive` nesne, yazma ve okuma**<** işlemlerini gerçekleştirmek**>>** için aşırı yüklü ekleme ( ) ve çıkarma ( ) işleçleri kullanır. Daha fazla bilgi için Serileştirme: Nesneyi Serileştirme makalesinde [bir Arşiv aracılığıyla CObjects](../mfc/storing-and-loading-cobjects-via-an-archive.md) Depolama ve Yükleme konusuna bakın.

> [!NOTE]
> `CArchive` Sınıfı yalnızca biçimlendirilmiş metin için olan genel amaçlı iostream sınıflarıyla karıştırmayın. Sınıf `CArchive` ikili biçimli serileştirilmiş nesneler içindir.

İsterseniz, kalıcı veri depolama için kendi mekanizmanızı oluşturmak için MFC serileştirmeyi atlayabilirsiniz. Kullanıcı nın komutuyla serileştirme başlatan sınıf üye işlevlerini geçersiz kılmanız gerekir. Tartışmayı ID_FILE_OPEN, ID_FILE_SAVE ve ID_FILE_SAVE_AS standart komutlarının [Teknik Not 22'sinde](../mfc/tn022-standard-commands-implementation.md) görün.

Aşağıdaki makaleler serileştirme için gerekli iki ana görevi kapsar:

- [Seri hale getirme: Seri Hale Getirilebilir Bir Sınıf Yapma](../mfc/serialization-making-a-serializable-class.md)

- [Seri hale getirme: Bir Nesneyi Seri Hale Getirme](../mfc/serialization-serializing-an-object.md)

Makale [Serialization: Serialization vs Veritabanı Giriş /Çıkış](../mfc/serialization-serialization-vs-database-input-output.md) ne zaman serileştirme veritabanı uygulamalarında uygun bir giriş / çıkış tekniği açıklanır.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../mfc/mfc-concepts.md)<br/>
[Genel MFC Konuları](../mfc/general-mfc-topics.md)<br/>
[CArchive Sınıfı](../mfc/reference/carchive-class.md)<br/>
[CObject Sınıfı](../mfc/reference/cobject-class.md)<br/>
[Kişniş Sınıfı](../mfc/reference/cdocument-class.md)<br/>
[CFile Sınıfı](../mfc/reference/cfile-class.md)
