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
ms.openlocfilehash: af3cde9445ae4b128e7e54a5f154db01b2eecd3b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308080"
---
# <a name="serializing-data-to-and-from-files"></a>Dosyalarda Verileri Seri Hale Getirme

Bir nesneyi kalıcı depolama için üye değişkenlerinin değerleri tarafından belirtilen geçerli durumuna yazabiliyor olmalıdır Kalıcılık temel fikri değildir. Daha sonra nesneyi okuyarak ya da "seri durumdan çıkarılırken," nesnenin durumu kalıcı depolama alanından yeniden oluşturulabilir. Burada temel nokta, nesnenin kendisini kendi durumunu yazma ve okuma için sorumlu olmasıdır. Bu nedenle, kalıcı olması bir sınıf için temel serileştirme işlemleri uygulamalıdır.

Yanıt olarak kaydetme disk dosyalarına belgeleri kaydetmek için varsayılan bir uygulama çerçevesini sağlar ve Farklı Kaydet komutlarının Dosya menüsündeki ve açık komutuna yanıt olarak disk dosyalarından belgelerinin yüklenmesinde. Çok az iş ile belge özelliği için ve bir dosyadan verileri okuyup yazmak uygulayabilirsiniz. Yapması gerekir ana geçersiz kılma şeydir [serileştirme](../mfc/reference/cobject-class.md#serialize) belge sınıfınızdaki üye işlevi.

MFC Uygulama Sihirbazı iskelet bir geçersiz kılma yerleştirir `CDocument` üye işlevi `Serialize` belge sınıfında sizin için oluşturur. Uygulamanızın üye değişkenleri uyguladıysanız sonra doldurabilirsiniz, `Serialize` "bir arşiv nesneye bağlı bir dosyaya" veri gönderen kodu geçersiz. A [CArchive](../mfc/reference/carchive-class.md) nesne benzer **cin** ve **cout** giriş/çıkış C++ iostream Kitaplığı nesneleri. Ancak, `CArchive` ikili biçimi, biçimlendirilmemiş metin okur ve yazar.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Serileştirme](../mfc/serialization-in-mfc.md)

- [Belgenin rolünde seri hale getirme](#_core_the_document.92.s_role_in_serialization)

- [Serileştirme sırasında veri rolü](#_core_the_data.92.s_role_in_serialization)

- [Seri hale getirme mekanizmasını atlama](../mfc/bypassing-the-serialization-mechanism.md)

##  <a name="_core_the_document.92.s_role_in_serialization"></a> Belgenin rolünde seri hale getirme

Otomatik olarak yanıt veren Dosya menüsünün açık olarak framework kaydedin ve komutları belgenin çağırarak `Serialize` uygulanmışsa, bu üye işlevi. Bir ıd_fıle_open komutu, örneğin, uygulama nesnesinde bir işleyici işlevi çağırır. Bu işlem sırasında kullanıcı görür ve Dosya Aç iletişim kutusuna yanıt verir ve framework kullanıcının seçtiği dosya adını alır. Framework oluşturur bir `CArchive` nesne için ayarlanmış verileri dokumentu yükleme ve arşive geçirir `Serialize`. Framework, dosyanın zaten açıldı. Belgenizin kodda `Serialize` üye işlevi yoluyla veri nesneleri gerektiği gibi yeniden oluşturuluyor, arşiv verileri okur. Seri hale getirme hakkında daha fazla bilgi için bkz [serileştirme](../mfc/serialization-in-mfc.md).

##  <a name="_core_the_data.92.s_role_in_serialization"></a> Serileştirme sırasında veri rolü

Genel olarak, sınıf türü verilerini kendisini seri hale getiremiyor olmalıdır. Diğer bir deyişle, bir nesne için bir arşiv geçirdiğinizde, nesnenin kendisini arşive yazma ve kendisini arşivden okuma bilmeniz gerekir. MFC sınıfları bu şekilde serileştirilebilir yapmak için destek sağlar. Bir veri türü tanımlamak için bir sınıf tasarlamak ve bu tür veriler seri hale getirmek istediğinize, seri hale getirme için tasarlayın.

## <a name="see-also"></a>Ayrıca bkz.

[Belgeleri Kullanma](../mfc/using-documents.md)
