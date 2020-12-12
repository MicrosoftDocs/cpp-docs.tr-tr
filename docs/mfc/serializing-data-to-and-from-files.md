---
description: 'Hakkında daha fazla bilgi edinin: dosyalara ve dosyalardan verileri serileştirme'
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
ms.openlocfilehash: 58956b2f11b8f0131aae74a6c5b51715fe25c7e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217451"
---
# <a name="serializing-data-to-and-from-files"></a>Dosyalarda Verileri Seri Hale Getirme

Kalıcılığın temel fikri, bir nesnenin kendi üye değişkenlerinin değerleriyle belirtilen geçerli durumunu kalıcı depolamaya yazabilmesi gerektiği durumdur. Daha sonra nesne, kalıcı depolamadan nesnenin durumunu okuyarak veya "serisini kaldırarak" yeniden oluşturulabilir. Burada bir anahtar noktası, nesnenin kendisinin kendi durumunu okuyup yazmaktan sorumludur. Bu nedenle, bir sınıfın kalıcı olması için temel serileştirme işlemlerini uygulaması gerekir.

Framework, Dosya menüsündeki Kaydet ve farklı kaydet komutlarına yanıt olarak disk dosyalarına belge kaydetmek ve aç komutuna yanıt olarak disk dosyalarından belge yüklemek için varsayılan bir uygulama sağlar. Çok az iş sayesinde, bir belgenin verilerini bir dosyaya ve dosyadan yazma ve okuma yeteneğini uygulayabilirsiniz. Yapmanız gereken ana şey, belge sınıflarınızdaki [serileştirme](../mfc/reference/cobject-class.md#serialize) üye işlevini geçersiz kılmalıdır.

MFC Uygulama Sihirbazı, `CDocument` `Serialize` sizin için oluşturduğu belge sınıfındaki üye işlevine bir iskelet geçersiz kılma işlemi koyar. Uygulamanızın üye değişkenlerini uyguladıktan sonra, `Serialize` verileri bir dosyaya bağlı bir "Arşiv nesnesine" Gönderen kodla geçersiz kılma işlemini doldurabilirsiniz. [CArchive](../mfc/reference/carchive-class.md) nesnesi, C++ ıostream kitaplığından **cin** ve **cout** Input/Output nesnelerine benzer. Ancak, `CArchive` biçimli metin değil ikili biçimi yazar ve okur.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Serileştirme](../mfc/serialization-in-mfc.md)

- [Belgenin serileştirme içindeki rolü](#_core_the_document.92.s_role_in_serialization)

- [Verilerin serileştirme içindeki rolü](#_core_the_data.92.s_role_in_serialization)

- [Seri hale getirme mekanizmasını atlama](../mfc/bypassing-the-serialization-mechanism.md)

## <a name="the-documents-role-in-serialization"></a><a name="_core_the_document.92.s_role_in_serialization"></a> Belgenin serileştirme içindeki rolü

Çerçeve, uygulanmış olması durumunda belgenin üye işlevini çağırarak Dosya menüsünün aç, Kaydet ve farklı kaydet komutlarına otomatik olarak yanıt verir `Serialize` . Örneğin, bir ID_FILE_OPEN komutu, uygulama nesnesinde bir işleyici işlevi çağırır. Bu işlem sırasında Kullanıcı, dosya Aç iletişim kutusunu görür ve yanıt verir ve Framework kullanıcının seçtiği dosya adını alır. Çerçeve, `CArchive` belgeye veri yüklemek için ayarlanmış bir nesne oluşturur ve arşivi öğesine geçirir `Serialize` . Çerçeve zaten dosyayı açtı. Belgenizin `Serialize` üye işlevindeki kod, arşivdeki verileri okur, gerektiğinde veri nesnelerini yeniden oluşturur. Serileştirme hakkında daha fazla bilgi için bkz. [serileştirme](../mfc/serialization-in-mfc.md)makalesi.

## <a name="the-datas-role-in-serialization"></a><a name="_core_the_data.92.s_role_in_serialization"></a> Verilerin serileştirme içindeki rolü

Genel olarak, sınıf türü veriler kendisini seri hale getirmek için olmalıdır. Yani, bir nesneyi bir arşive geçirdiğinizde, nesne kendisini arşive nasıl yazacağınızı ve arşivden nasıl okunacağını bilmelidir. MFC, bu şekilde sınıfları seri hale getirmek için destek sağlar. Bir veri türünü tanımlamak için bir sınıf tasarlarsanız ve bu türdeki verileri seri hale getirmeyi düşünüyorsanız, serileştirme için tasarlayın.

## <a name="see-also"></a>Ayrıca bkz.

[Belgeleri kullanma](../mfc/using-documents.md)
