---
title: Dosyalarda Verileri Seri Hale Getirme
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], serialization
- documents [MFC], saving
- saving documents
- deserialization [MFC]
- serialization [MFC], role of document
- serialization [MFC], role of data
- data [MFC]
- data [MFC], serializing
- document data [MFC]
ms.assetid: b42a0c68-4bc4-4012-9938-5433a26d2c24
ms.openlocfilehash: 043ba019c6b5ad79db2cedb6314c9e65f14b14b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376929"
---
# <a name="serializing-data-to-and-from-files"></a>Dosyalarda Verileri Seri Hale Getirme

Kalıcılığın temel fikri, bir nesnenin üye değişkenlerin değerleriyle gösterilen geçerli durumunu kalıcı depolamaya yazabilmesidir. Daha sonra, nesne kalıcı depolama nesnenin durumu okuma veya "deserializing" tarafından yeniden oluşturulabilir. Burada önemli bir nokta, nesnenin kendisinin kendi durumunu okuma ve yazmadan sorumlu olmasıdır. Bu nedenle, bir sınıfın kalıcı olabilmesi için temel serileştirme işlemlerini uygulaması gerekir.

Çerçeve, Dosya menüsündeki Kaydet ve Kaydet komutlarına yanıt olarak belgeleri disk dosyalarına kaydetmek ve Belgeleri Açık komutuna yanıt olarak disk dosyalarından yüklemek için varsayılan bir uygulama sağlar. Çok az çalışmayla, bir belgenin verilerini dosyaya ve dosyadan yazma ve okuma yeteneğini uygulayabilirsiniz. Yapmanız gereken en önemli şey belge sınıfınızdaki [Serialize](../mfc/reference/cobject-class.md#serialize) üye işlevini geçersiz kılmaktır.

MFC Uygulama Sihirbazı, sizin için oluşturduğu `CDocument` belge `Serialize` sınıfına üye işlevin iskelet geçersiz kılmasını yerleştirir. Uygulamanızın üye değişkenlerini uyguladıktan sonra, geçersiz kılmanızı `Serialize` verileri bir dosyaya bağlı bir "arşiv nesnesine" gönderen kodla doldurabilirsiniz. [CArchive nesnesi,](../mfc/reference/carchive-class.md) C++ iostream kitaplığındaki **cin** ve **cout** giriş/çıkış nesnelerine benzer. Ancak, `CArchive` biçimlendirilmiş metin değil, ikili biçim yazar ve okur.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Serileştirme](../mfc/serialization-in-mfc.md)

- [Belgenin serileştirmedeki rolü](#_core_the_document.92.s_role_in_serialization)

- [Verilerin serileştirmedeki rolü](#_core_the_data.92.s_role_in_serialization)

- [Serileştirme mekanizmasını atlayarak](../mfc/bypassing-the-serialization-mechanism.md)

## <a name="the-documents-role-in-serialization"></a><a name="_core_the_document.92.s_role_in_serialization"></a>Belgenin Serileştirmedeki Rolü

Çerçeve, dosya nın Dosya menüsünün Aç, Kaydet ve Kaydet komutlarına, `Serialize` uygulandığı takdirde belgenin üye işlevini çağırarak otomatik olarak yanıt verir. Örneğin, bir ID_FILE_OPEN komutu uygulama nesnesinde bir işleyici işlevi çağırır. Bu işlem sırasında, kullanıcı Dosya Aç iletişim kutusunu görür ve yanıtverir ve çerçeve kullanıcının seçtiği dosya adını alır. Çerçeve, belgeye `CArchive` veri yüklemek için ayarlanmış bir nesne oluşturur `Serialize`ve arşivi ' ye geçirir. Çerçeve dosyayı zaten açtı. Belgenizin `Serialize` üye işlevindeki kod, arşivdeki verileri okur ve gerektiğinde veri nesnelerini yeniden yapılandırAr. Serileştirme hakkında daha fazla bilgi için [Serileştirme](../mfc/serialization-in-mfc.md)makalesine bakın.

## <a name="the-datas-role-in-serialization"></a><a name="_core_the_data.92.s_role_in_serialization"></a>Verilerin Serileştirmedeki Rolü

Genel olarak, sınıf türü verileri kendini seri hale getirmek gerekir. Diğer bir şey, bir nesneyi arşive geçtiğinde, nesnenin kendisini arşive nasıl yazacağını ve arşivden nasıl okunacağını bilmesi gerekir. MFC, sınıfları bu şekilde serileştirilebilir hale getirmek için destek sağlar. Bir veri türünü tanımlamak için bir sınıf tasarlarsanız ve bu tür verileri serihale etmeyi planlıyorsanız, serileştirme için tasarım.

## <a name="see-also"></a>Ayrıca bkz.

[Belgeleri Kullanma](../mfc/using-documents.md)
