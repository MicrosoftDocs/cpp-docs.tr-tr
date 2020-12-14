---
description: 'Daha fazla bilgi edinin: CArchive nesnesi oluşturmanın Iki yolu'
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
ms.openlocfilehash: 21a4321eef2d93cf0b37d157f57e12fa1ba940c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263861"
---
# <a name="two-ways-to-create-a-carchive-object"></a>CArchive Nesnesi Oluşturmanın İki Yolu

Bir nesne oluşturmanın iki yolu vardır `CArchive` :

- [Framework aracılığıyla bir CArchive nesnesinin örtük olarak oluşturulması](#_core_implicit_creation_of_a_carchive_object_via_the_framework)

- [CArchive nesnesinin açık olarak oluşturulması](#_core_explicit_creation_of_a_carchive_object)

## <a name="implicit-creation-of-a-carchive-object-via-the-framework"></a><a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a> Framework aracılığıyla bir CArchive nesnesinin örtük olarak oluşturulması

En yaygın ve en kolay yöntem, Framework 'ün `CArchive` Dosya menüsündeki Kaydet, farklı Kaydet ve aç komutlarını adına bir nesne oluşturmasını sağlar.

Bu, uygulamanızın kullanıcısı Dosya menüsünden farklı Kaydet komutunu öğrendikünüzde şu şekildedir:

1. **Farklı kaydet** iletişim kutusunu gösterir ve kullanıcının dosya adını alır.

1. Kullanıcı tarafından bir nesne olarak adlandırılan dosyayı açar `CFile` .

1. `CArchive`Bu nesneyi işaret eden bir nesne oluşturur `CFile` . `CArchive`Nesne oluştururken, çerçeve "Load" (okuma, seri durumdan çıkarma) aksine modu "depola" (yazma, serileştirme) olarak ayarlar.

1. `Serialize` `CDocument` Türetilmiş sınıfınıza tanımlanan işlevi çağırarak nesneye bir başvuru geçirerek bunu çağırır `CArchive` .

`Serialize`Daha sonra belgenizin işlevi verileri `CArchive` nesneye yazar ve kısa süre içinde açıklanacaktır. İşlevinizden geri döndüğünüzde `Serialize` çerçeve `CArchive` nesneyi ve sonra nesnesini yok eder `CFile` .

Bu nedenle, Framework 'ün `CArchive` belgeniz için nesne oluşturmasına izin verirseniz, tek yapmanız gereken, `Serialize` Arşiv 'e ve arşivden yazan ve okuyan belgenin işlevini uygular. Ayrıca `Serialize` `CObject` , belgenin `Serialize` işlevinin de doğrudan veya dolaylı olarak serileştirtiği tüm türetilmiş nesneler için de uygulamanız gerekir.

## <a name="explicit-creation-of-a-carchive-object"></a><a name="_core_explicit_creation_of_a_carchive_object"></a> CArchive nesnesinin açık olarak oluşturulması

Bir belgeyi Framework aracılığıyla serileştirmenin yanı sıra, bir nesneye ihtiyacınız olabilecek başka durumlar da vardır `CArchive` . Örneğin, bir nesneyle temsil edilen ve Panodan veri seri hale getirmek isteyebilirsiniz `CSharedFile` . Ya da, Framework tarafından sunulan bir dosyayı kaydetmek için bir kullanıcı arabirimi kullanmak isteyebilirsiniz. Bu durumda, açıkça bir `CArchive` nesne oluşturabilirsiniz. Bunu, aşağıdaki yordamı kullanarak Framework ile aynı şekilde yapabilirsiniz.

#### <a name="to-explicitly-create-a-carchive-object"></a>Açıkça bir CArchive nesnesi oluşturmak için

1. `CFile`Öğesinden türetilmiş bir nesne veya nesne oluşturun `CFile` .

1. `CFile` `CArchive` Aşağıdaki örnekte gösterildiği gibi, nesnesini oluşturucuya geçirin:

   [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]

   Oluşturucunun ikinci bağımsız değişkeni, `CArchive` arşivin dosya üzerinde veya dosyadan veri depolamak veya dosyaya yüklemek için kullanılıp kullanılmayacağını belirten numaralandırılmış bir değerdir. `Serialize`Bir nesnenin işlevi, `IsStoring` Arşiv nesnesi için işlevini çağırarak bu durumu denetler.

Verileri bir veya nesnesine depolamayı veya veri yüklemeyi bitirdiğinizde `CArchive` kapatın. `CArchive`(Ve `CFile` ) nesneleri otomatik olarak Arşivi (ve dosyasını) kapatacak olsa da, hatalardan kurtarma yaptığından daha kolay bir şekilde yapmak iyi bir uygulamadır. Hata işleme hakkında daha fazla bilgi için bkz. özel durumlar [: özel durumları yakalama ve silme](../mfc/exceptions-catching-and-deleting-exceptions.md).

#### <a name="to-close-the-carchive-object"></a>CArchive nesnesini kapatmak için

1. Aşağıdaki örnek, nesnesinin nasıl kapandığını göstermektedir `CArchive` :

   [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Serileştirme: bir nesneyi seri hale getirme](../mfc/serialization-serializing-an-object.md)
