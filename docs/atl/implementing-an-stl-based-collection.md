---
title: Bir C++ Standart Kitaplığı temelli koleksiyon uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- ICollectionOnSTLImpl interface
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
ms.openlocfilehash: 609ec2547cf7a8ab93ef757f7a8e460542c9de28
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779254"
---
# <a name="implementing-a-c-standard-library-based-collection"></a>Bir C++ Standart Kitaplığı temelli koleksiyon uygulama

ATL sağlar `ICollectionOnSTLImpl` hızla, nesneler üzerinde arabirimlerini C++ Standart Kitaplığı temelli koleksiyon uygulama sağlamak için arabirim. Bu sınıf nasıl çalıştığını anlamak için Otomasyon istemcileri amaçlayan bir salt okunur koleksiyon uygulamak için bu sınıfı kullanan basit bir örnek (aşağıda) üzerinden çalışır.

Örnek kod dandır [ATLCollections örnek](../overview/visual-cpp-samples.md).

Bu yordamı tamamlamak için şunları yapacaksınız:

- [Yeni, basit bir nesne oluşturmak](#vccongenerating_an_object).

- [IDL dosyası Düzenle](#vcconedit_the_idl) oluşturulan arabirimi.

- [Beş tür tanımları oluşturma](#vcconstorage_and_exposure_typedefs) koleksiyon öğelerini nasıl depolandığını ve nasıl bunlar istemcilere COM arabirimleri aracılığıyla sunulur.

- [İki tür tanımları kopyalama İlkesi sınıfları oluşturma](#vcconcopy_classes).

- [Numaralandırıcı ve koleksiyon uygulamaları için tür tanımları oluşturma](#vcconenumeration_and_collection).

- [Koleksiyon typedef kullanmak için sihirbaz tarafından oluşturulan C++ kodu düzenleme](#vcconedit_the_generated_code).

- [Koleksiyonu doldurmak için kod ekleme](#vcconpopulate_the_collection).

##  <a name="vccongenerating_an_object"></a> Yeni, basit bir nesne oluşturma

Uygulama ayarları öznitelikleri kutusunun temizlenmiş olduğundan emin olduktan yeni bir proje oluşturun. ATL Sınıf Ekle iletişim kutusunu kullanın ve ekleme Basit Nesne basit bir nesne oluşturmak için Sihirbazı adlı `Words`. Çift arabirim adlı emin `IWords` oluşturulur. Oluşturulan sınıfın nesneleri bir sözcük (diğer bir deyişle, diziler) koleksiyonunu temsil etmek için kullanılır.

##  <a name="vcconedit_the_idl"></a> IDL dosyası düzenleme

Şimdi, IDL dosyasını açın ve etkinleştirmek için gereken üç özellik Ekle `IWords` aşağıda gösterildiği gibi bir salt okunur koleksiyon arabirim uygulamasına:

[!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/cpp/implementing-an-stl-based-collection_1.idl)]

Otomasyon istemcileri düşünülerek tasarlanan bir salt okunur koleksiyon arabirimi için standart biçimidir. Bu arabirim tanımı numaralı açıklamaları aşağıdaki açıklamalar karşılık gelir:

1. Otomasyon istemcilerine erişir çünkü koleksiyon arabirimleri genellikle çift `_NewEnum` özelliği aracılığıyla `IDispatch::Invoke`. Ancak, ikili arabirimler görüntüleme için tercih edilir, böylece Otomasyon istemcileri kalan yöntemler vtable aracılığıyla erişebilirsiniz.

1. Çift arabirim veya dispinterface çalışma zamanında genişletilmiş değil, (diğer bir deyişle, ek yöntemleri veya özellikleri aracılığıyla sağlamayacak `IDispatch::Invoke`), uygulamanız gerekir **nonextensible** tanımınıza özniteliği. Bu öznitelik, derleme zamanında tam kod doğrulama gerçekleştirmek Otomasyon istemcileri sağlar. Bu durumda, genişletilmiş arabirimi değil.

1. Bu özelliği kullanabilmek için Otomasyon istemcileri istiyorsanız doğru DISPID önemlidir. (DISPID_NEWENUM içinde yalnızca bir alt çizgi olduğuna dikkat edin.)

1. Herhangi bir değer DISPID sağlayabilirsiniz `Item` özelliği. Ancak, `Item` koleksiyon öğesinin varsayılan özelliği yapmak için genellikle DISPID_VALUE kullanır. Bu açıkça adlandırma olmadan özelliğine başvurmak Otomasyon istemcileri sağlar.

1. Dönüş değeri için kullanılan veri türünü `Item` COM istemcileri endişe kadar bir koleksiyonda depolanan öğenin türünü bir özelliktir. BSTR standart COM dize türü kullanması gereken şekilde arabirimi dizeyi döndürür. Kısa bir süre içinde anlatıldığı gibi verileri farklı bir biçimde dahili olarak depolayabilirsiniz.

1. DISPID için kullanılan değer `Count` özelliği tamamen isteğe bağlı. Bu özellik için standart hiçbir DISPID yoktur.

##  <a name="vcconstorage_and_exposure_typedefs"></a> Depolama ve Etkilenme için tür tanımları oluşturma

Koleksiyon arabirimi tanımlandıktan sonra veriler nasıl depolanır ve veriler Numaralandırıcı nasıl sunulur karar vermeniz gerekir.

Bu soruların yanıtlarını tür tanımları, yeni oluşturulan sınıfı için üst bilgi dosyasının en üstüne ekleyebileceğiniz bir dizi biçiminde sağlanabilir:

[!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/cpp/implementing-an-stl-based-collection_2.h)]

Bu durumda, verileri depolayacak bir **std::vector** , **std::string**s. **Std::Vector** yönetilen bir dizi gibi davranır bir C++ Standart Kitaplığı kapsayıcı sınıfıdır. **Std::String** C++ Standart Kitaplığı'nın dize sınıfıdır. Bu sınıfların dizelerden oluşan bir koleksiyon ile çalışmak kolaylaştırır.

Visual Basic desteği bu arabirimin başarısı için önemli olduğundan, numaralandırıcı tarafından döndürülen `_NewEnum` özelliği desteklemelidir `IEnumVARIANT` arabirimi. Bu, Visual Basic tarafından anlaşılan tek Numaralandırıcı arabirimidir.

##  <a name="vcconcopy_classes"></a> Kopyalama İlkesi sınıfları için tür tanımları oluşturma

Şu ana kadar oluşturulmuş tür tanımları, daha fazla koleksiyon ve Numaralandırıcı kullanılacak kopyalama sınıflar için tür tanımları oluşturmak gereken tüm bilgileri sağlayın:

[!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/cpp/implementing-an-stl-based-collection_3.h)]

Bu örnekte, özel kullanabileceğiniz `GenericCopy` VCUE_Copy.h ve gelen VCUE_CopyString.h tanımlanmış sınıf [ATLCollections](../overview/visual-cpp-samples.md) örnek. Bu sınıf diğer kodda kullanabilirsiniz, ancak daha da uzmanlıkları da tanımlamanız gerekebilir `GenericCopy` kendi koleksiyonlarında kullanılan veri türlerini desteklemek için. Daha fazla bilgi için [ATL kopyalama İlkesi sınıfları](../atl/atl-copy-policy-classes.md).

##  <a name="vcconenumeration_and_collection"></a> Sabit listesi ve koleksiyon için tür tanımları oluşturma

Artık tüm şablon parametreleri özelleştirmek üzere gerekli `CComEnumOnSTL` ve `ICollectionOnSTLImpl` sınıflar bu durum için tür tanımları biçiminde sağlanmıştır. Uzmanlıkları kullanımını kolaylaştırmak için aşağıda gösterildiği gibi iki daha fazla tür tanımları oluşturun:

[!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/cpp/implementing-an-stl-based-collection_4.h)]

Artık `CollectionType` özelleştirmesi eşanlamlıdır `ICollectionOnSTLImpl` uygulayan `IWords` arabirimi daha önce tanımlanan ve destekleyen bir numaralandırıcı sağlar `IEnumVARIANT`.

##  <a name="vcconedit_the_generated_code"></a> Sihirbazın ürettiği kod düzenleme

Türetilmesi gerekir artık `CWords` tarafından temsil edilen arabirimi uygulamasından `CollectionType` typedef yerine `IWords`, aşağıda gösterildiği gibi:

[!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/cpp/implementing-an-stl-based-collection_5.h)]

##  <a name="vcconpopulate_the_collection"></a> Koleksiyonu doldurmak için kod ekleme

Vektör verilerle doldurmak için kalan gereken tek şey var. Bu basit örnekte, sınıf için oluşturucu koleksiyona birkaç sözcük ekleyebilirsiniz:

[!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/cpp/implementing-an-stl-based-collection_6.h)]

Artık, seçtiğiniz istemci ile kodu test edebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar ve numaralandırmalar](../atl/atl-collections-and-enumerators.md)<br/>
[ATLCollections örnek](../overview/visual-cpp-samples.md)<br/>
[ATL Kopyalama İlkesi Sınıfları](../atl/atl-copy-policy-classes.md)
