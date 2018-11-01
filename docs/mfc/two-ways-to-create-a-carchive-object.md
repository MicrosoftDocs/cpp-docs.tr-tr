---
title: CArchive Nesnesi Oluşturmanın İki Yolu
ms.date: 11/04/2016
f1_keywords:
- CArchive
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
ms.openlocfilehash: a97223602e9994647a8af16cc68de5394494c1ca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659933"
---
# <a name="two-ways-to-create-a-carchive-object"></a>CArchive Nesnesi Oluşturmanın İki Yolu

Oluşturmanın iki yolu vardır. bir `CArchive` nesnesi:

- [CArchive nesnesi framework aracılığıyla örtük oluşturma](#_core_implicit_creation_of_a_carchive_object_via_the_framework)

- [CArchive nesnesi açık oluşturma](#_core_explicit_creation_of_a_carchive_object)

##  <a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a> CArchive nesnesi Framework aracılığıyla örtük oluşturma

En yaygın ve kolay bir şekilde oluşturma framework izin vermek için olan bir `CArchive` kaydetme, Farklı Kaydet ve Aç komutları Dosya menüsündeki adına belgeniz için nesne.

İşte, uygulamanızın kullanıcı Dosya menüsünden Kaydet komutunu verdiğinde framework yapar:

1. Sunan **Kaydet** iletişim kutusu ve kullanıcıdan dosya adını alır.

1. Kullanıcı tarafından adlı dosyayı açar bir `CFile` nesne.

1. Oluşturur bir `CArchive` için işaret eden bir nesne `CFile` nesne. Oluşturma `CArchive` framework "Mağaza" modunu ayarlar nesnesi (yazma, seri hale getirmek), "Yükle" ın aksine (okuma, seri durumdan).

1. Çağrıları `Serialize` tanımlanan işlevi, `CDocument`-türetilmiş sınıf başvurusu geçirme, `CArchive` nesne.

Belgenizin `Serialize` işlevi sonra verileri Yazar `CArchive` kısa süre içinde açıklandığı gibi nesne. Geri döndürme işlevi üzerine, `Serialize` işlevi, framework yok eder `CArchive` nesnesi ve ardından `CFile` nesne.

Bu nedenle, oluşturma framework izin verirseniz `CArchive` belgeniz için tüm yapmanız gereken belgenin uygulamak olan nesne `Serialize` yazar ve okur ve Arşiv gelen işlevi. Uygulamak de `Serialize` herhangi `CObject`-türetilmiş nesneler, belgenin `Serialize` işlevi sırayla doğrudan veya dolaylı olarak serileştirir.

##  <a name="_core_explicit_creation_of_a_carchive_object"></a> CArchive nesnesi açık oluşturma

Bir belge çerçevesi aracılığıyla serileştirmek yanı sıra, ne zaman ihtiyacınız olabilecek başka durumlar vardır bir `CArchive` nesne. Örneğin, verilerini ve panodan tarafından temsil edilen seri hale getirmek isteyebilirsiniz bir `CSharedFile` nesne. Veya, bir kullanıcı arabirimi çerçevesi tarafından sunulan olandan farklı bir dosyaya kaydetmek için kullanmak isteyebilirsiniz. Bu durumda, açıkça oluşturabileceğiniz bir `CArchive` nesne. Bu, framework mu, aynı şekilde, aşağıdaki yordamı kullanarak yapın.

#### <a name="to-explicitly-create-a-carchive-object"></a>CArchive nesnesi açıkça oluşturmak için

1. Oluşturmak bir `CFile` veya nesneyi türetilen `CFile`.

1. Geçirmek `CFile` için oluşturucusuna `CArchive`, aşağıdaki örnekte gösterildiği gibi:

   [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]

   İkinci bağımsız değişkeni `CArchive` oluşturucudur arşiv depolama ve veri ya da yükleme dosyasından kullanılıp kullanılmayacağını belirten bir numaralandırılmış değeri. `Serialize` Bir nesnenin işlev çağırarak bu durumu denetler `IsStoring` arşiv nesne için işlevi.

Depolama veya veri yüklemeyi tamamladıktan sonra `CArchive` nesne, kapatın. Ancak `CArchive` (ve `CFile`) nesneleri otomatik olarak kapatılır arşiv (ve dosya), açıkça kurtarma hataları kolaylaştırır olduğundan Bunu yapmak için iyi bir uygulamadır. Hata işleme hakkında daha fazla bilgi için bkz [özel durumlar: çalýþýrçalýþma yakalama ve silme özel durumları](../mfc/exceptions-catching-and-deleting-exceptions.md).

#### <a name="to-close-the-carchive-object"></a>CArchive nesnesi kapatmak için

1. Aşağıdaki örnekte nasıl kapatılacağını `CArchive` nesnesi:

   [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Seri hale getirme: Bir Nesneyi Seri Hale Getirme](../mfc/serialization-serializing-an-object.md)

