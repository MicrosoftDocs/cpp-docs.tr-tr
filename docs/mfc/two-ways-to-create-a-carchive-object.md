---
title: CArchive Nesnesi Oluşturmanın İki Yolu
ms.date: 11/04/2016
helpviewer_keywords:
- CArchive class [MFC], closing CArchive objects
- CArchive objects [MFC], closing
- I/O [MFC], creating CArchive objects
- serialization [MFC], CArchive class
- CArchive objects [MFC]
- storage [MFC], CArchive class [MFC]
- data storage [MFC], CArchive class
- CArchive class [MFC], constructor
ms.assetid: aefa28ce-b55c-40dc-9e42-5f038030985d
ms.openlocfilehash: 71592584d4ecdd3169ad894861a97fa668c04ee8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370952"
---
# <a name="two-ways-to-create-a-carchive-object"></a>CArchive Nesnesi Oluşturmanın İki Yolu

Nesne oluşturmanın `CArchive` iki yolu vardır:

- [Çerçeve üzerinden bir CArchive nesnesinin örtülü oluşturulması](#_core_implicit_creation_of_a_carchive_object_via_the_framework)

- [CArchive nesnesinin açık oluşturulması](#_core_explicit_creation_of_a_carchive_object)

## <a name="implicit-creation-of-a-carchive-object-via-the-framework"></a><a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a>Çerçeve üzerinden CArchive Nesnesinin Örtülü Oluşturulması

En yaygın ve en kolay yol, çerçevenin `CArchive` Dosya menüsündeki Kaydet, Farklı Kaydet ve Aç komutları adına belgeniz için bir nesne oluşturmasına izin vermektir.

Uygulamanızın kullanıcısı Dosya menüsünden Kaydet komutunu verdiğinde çerçevenin yaptığı aşağıdaki gibidir:

1. **Kaydet** iletişim kutusunu sunar ve dosya adını kullanıcıdan alır.

1. Kullanıcı tarafından `CFile` nesne olarak adlandırılan dosyayı açar.

1. Bu `CArchive` `CFile` nesneyi işaret eden bir nesne oluşturur. Nesneyi `CArchive` oluştururken, çerçeve "yükleme" (okuma, deserialize) yerine "depolamak" (yazma, serileştirme) modunu ayarlar.

1. Türemiş `Serialize` sınıfınızda `CDocument`tanımlanan işlevi çağırarak `CArchive` nesneye bir başvuru da aktar.

Belgenizin `Serialize` işlevi daha sonra `CArchive` kısa bir süre açıklandığı gibi nesneye veri yazar. Işlevinizden `Serialize` döndükten sonra, çerçeve `CArchive` nesneyi ve `CFile` nesneyi yok eder.

Bu nedenle, çerçevenin belgeniz için `CArchive` nesne oluşturmasına izin verdiyseniz, tek `Serialize` yapmanız gereken belgenin arşive yazıyazan ve okuyan işlevini uygulamaktır. Ayrıca, belgenin `Serialize` `CObject` `Serialize` işlevinin doğrudan veya dolaylı olarak serihale ettiği türetilmiş nesneler için de uygulamanız gerekir.

## <a name="explicit-creation-of-a-carchive-object"></a><a name="_core_explicit_creation_of_a_carchive_object"></a>CArchive Nesnesinin Açık Oluşturulması

Bir belgeyi çerçeve üzerinden seri hale getirmenin yanı `CArchive` sıra, bir nesneye ihtiyaç duyabileceğiniz başka durumlar da vardır. Örneğin, bir `CSharedFile` nesne tarafından temsil edilen Pano'ya ve Panodan gelen verileri seri hale getirmek isteyebilirsiniz. Veya, çerçeve tarafından sunulandan farklı bir dosyayı kaydetmek için bir kullanıcı arabirimi kullanmak isteyebilirsiniz. Bu durumda, açıkça bir `CArchive` nesne oluşturabilirsiniz. Bunu, aşağıdaki yordamı kullanarak çerçevenin yaptığı şekilde yaparsınız.

#### <a name="to-explicitly-create-a-carchive-object"></a>CArchive nesnesini açıkça oluşturmak için

1. `CFile`Bir `CFile` nesne veya türetilen bir nesne oluşturma.

1. Nesneyi `CFile` aşağıdaki örnekte `CArchive`gösterildiği gibi oluşturucuya geçirin:

   [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]

   `CArchive` Oluşturucuya ikinci bağımsız değişken, arşivin dosyaya veya dosyadan veri depolamak veya yüklemek için kullanılıp kullanılmayacağını belirten numaralandırılmış bir değerdir. Bir `Serialize` nesnenin işlevi, arşiv nesnesi `IsStoring` için işlevi çağırarak bu durumu denetler.

`CArchive` Nesneye veya nesneye veri depolamayı veya yüklemeyi bitirdiğinizde, nesneyi kapatın. `CArchive` (ve) `CFile`nesneleri arşivi (ve dosyayı) otomatik olarak kapatsa da, hatalardan kurtarmayı kolaylaştırdığı için bunu açıkça yapmak iyi bir uygulamadır. Hata işleme hakkında daha fazla bilgi için, özel [durumlar makalesine bakın: Özel Durumları Yakalama ve Silme.](../mfc/exceptions-catching-and-deleting-exceptions.md)

#### <a name="to-close-the-carchive-object"></a>CArchive nesnesini kapatmak için

1. Aşağıdaki örnek, nesnenin nasıl `CArchive` kapatılabildiğini göstermektedir:

   [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Seri hale getirme: Bir Nesneyi Seri Hale Getirme](../mfc/serialization-serializing-an-object.md)
