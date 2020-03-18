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
ms.openlocfilehash: 38642906b0973730149ed0de5381519f06d69fe5
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442030"
---
# <a name="two-ways-to-create-a-carchive-object"></a>CArchive Nesnesi Oluşturmanın İki Yolu

`CArchive` nesnesi oluşturmanın iki yolu vardır:

- [Framework aracılığıyla bir CArchive nesnesinin örtük olarak oluşturulması](#_core_implicit_creation_of_a_carchive_object_via_the_framework)

- [CArchive nesnesinin açık olarak oluşturulması](#_core_explicit_creation_of_a_carchive_object)

##  <a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a>Framework aracılığıyla bir CArchive nesnesinin örtük olarak oluşturulması

En yaygın ve en kolay yöntem, Framework 'ün Dosya menüsündeki Kaydet, farklı Kaydet ve aç komutlarını adına bir `CArchive` nesne oluşturmasını sağlar.

Bu, uygulamanızın kullanıcısı Dosya menüsünden farklı Kaydet komutunu öğrendikünüzde şu şekildedir:

1. **Farklı kaydet** iletişim kutusunu gösterir ve kullanıcının dosya adını alır.

1. Kullanıcı tarafından `CFile` nesne olarak adlandırılan dosyayı açar.

1. Bu `CFile` nesnesine işaret eden bir `CArchive` nesnesi oluşturur. `CArchive` nesnesini oluştururken Framework, "Load" (okuma, seri durumdan çıkarma) aksine modu "depola" (yazma, serileştirme) olarak ayarlar.

1. `CDocument`türetilmiş sınıfınıza tanımlanan `Serialize` işlevini çağırarak `CArchive` nesnesine bir başvuru geçirerek.

Belgenizin `Serialize` işlevi, kısa süre içinde açıklandığı gibi `CArchive` nesnesine veri yazar. `Serialize` işlevinizden geri döndüğünüzde Framework, `CArchive` nesnesini ve `CFile` nesnesini yok eder.

Bu nedenle, Framework 'ün belgeniz için `CArchive` nesnesini oluşturmasına izin verirseniz, tüm yapmanız gereken, dosyanın arşive yazma ve arşivi okuyan `Serialize` işlevini uygulamaktır. Ayrıca, belgenin `Serialize` işlevinin doğrudan veya dolaylı olarak serileştirtiği `CObject`türetilmiş tüm nesneler için `Serialize` uygulamanız gerekir.

##  <a name="_core_explicit_creation_of_a_carchive_object"></a>CArchive nesnesinin açık olarak oluşturulması

Bir belgeyi Framework aracılığıyla serileştirmenin yanı sıra, bir `CArchive` nesnesine ihtiyacınız olabilecek başka durumlar da vardır. Örneğin, `CSharedFile` nesne ile temsil edilen verileri panodan ve Panodan seri hale getirmek isteyebilirsiniz. Ya da, Framework tarafından sunulan bir dosyayı kaydetmek için bir kullanıcı arabirimi kullanmak isteyebilirsiniz. Bu durumda, açıkça bir `CArchive` nesnesi oluşturabilirsiniz. Bunu, aşağıdaki yordamı kullanarak Framework ile aynı şekilde yapabilirsiniz.

#### <a name="to-explicitly-create-a-carchive-object"></a>Açıkça bir CArchive nesnesi oluşturmak için

1. `CFile` nesne veya `CFile`türetilmiş bir nesne oluşturun.

1. Aşağıdaki örnekte gösterildiği gibi `CFile` nesnesini `CArchive`oluşturucusuna geçirin:

   [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]

   `CArchive` oluşturucusunun ikinci bağımsız değişkeni, arşivin dosya üzerinde veya dosyadan veri depolamak veya dosyaya yüklemek için kullanılıp kullanılmayacağını belirten numaralandırılmış bir değerdir. Bir nesnenin `Serialize` işlevi, Arşiv nesnesi için `IsStoring` işlevini çağırarak bu durumu denetler.

`CArchive` nesnesine veri depolamayı veya bu verileri yüklemeyi bitirdiğinizde kapatın. `CArchive` (ve `CFile`) nesneleri otomatik olarak Arşivi (ve dosyasını) kapatacak olsa da, hatalardan kurtarma yaptığından daha kolay bir şekilde yapmak iyi bir uygulamadır. Hata işleme hakkında daha fazla bilgi için bkz. özel durumlar [: özel durumları yakalama ve silme](../mfc/exceptions-catching-and-deleting-exceptions.md).

#### <a name="to-close-the-carchive-object"></a>CArchive nesnesini kapatmak için

1. Aşağıdaki örnek `CArchive` nesnesinin nasıl kapandığını göstermektedir:

   [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Seri hale getirme: Bir Nesneyi Seri Hale Getirme](../mfc/serialization-serializing-an-object.md)
