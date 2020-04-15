---
title: C++ Standart Kitaplık Tabanlı Koleksiyonu Uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- ICollectionOnSTLImpl interface
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
ms.openlocfilehash: e80ce5e7bbc6b9c6be1615dad1ea43c18e03eb55
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319436"
---
# <a name="implementing-a-c-standard-library-based-collection"></a>C++ Standart Kitaplık Tabanlı Koleksiyonu Uygulama

ATL, `ICollectionOnSTLImpl` nesnelerinize C++ Standart Kitaplık tabanlı koleksiyon arabirimlerini hızla uygulamanızı sağlayacak arabirimi sağlar. Bu sınıfın nasıl çalıştığını anlamak için, Otomasyon istemcilerini hedefleyen salt okunur toplamayı uygulamak için bu sınıfı kullanan basit bir örnek (aşağıda) üzerinden çalışacaksınız.

Örnek kodu [ATLCollections örneğinden.](../overview/visual-cpp-samples.md)

Bu yordamı tamamlamak için şunları yapacaksınız:

- [Yeni bir Basit Nesne oluşturun.](#vccongenerating_an_object)

- Oluşturulan arabirim için [IDL dosyasını edin.](#vcconedit_the_idl)

- Koleksiyon öğelerinin nasıl depolanacağını ve COM arabirimleri aracılığıyla istemcilere nasıl maruz kaldıklarını açıklayan [beş typedefoluşturun.](#vcconstorage_and_exposure_typedefs)

- [Kopyalama ilkesi sınıfları için iki typedef oluşturun.](#vcconcopy_classes)

- [Numaralandırıcı ve toplama uygulamaları için typedefs oluşturun.](#vcconenumeration_and_collection)

- [Koleksiyon typedef'ini kullanmak için sihirbaz tarafından oluşturulan C++ kodunu edin.](#vcconedit_the_generated_code)

- [Koleksiyonu doldurmak için kod ekleyin.](#vcconpopulate_the_collection)

## <a name="generating-a-new-simple-object"></a><a name="vccongenerating_an_object"></a>Yeni Basit Nesne Oluşturma

Uygulama Ayarları altındaki Öznitelikler kutusunun temizlenmesini sağlayarak yeni bir proje oluşturun. ATL Sınıf Ekle iletişim kutusunu kullanın ve Basit Nesne Ekle `Words`Sihirbazı adlı basit bir nesne oluşturmak için. Adlı `IWords` çift arabirimin oluşturulduğundan emin olun. Oluşturulan sınıfın nesneleri bir sözcük koleksiyonunu (diğer bir deyişle dizeleri) temsil etmek için kullanılır.

## <a name="editing-the-idl-file"></a><a name="vcconedit_the_idl"></a>IDL Dosyasını Düzenleme

Şimdi, IDL dosyasını açın ve aşağıda `IWords` gösterildiği gibi salt okunur toplama arabirimine dönüştürmek için gereken üç özelliği ekleyin:

[!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/cpp/implementing-an-stl-based-collection_1.idl)]

Bu, Otomasyon istemcileri göz önünde bulundurularak tasarlanmış salt okunur toplama arabirimi için standart formdur. Bu arabirim tanımındaki numaralanmış yorumlar aşağıdaki yorumlara karşılık gelir:

1. Otomasyon istemcileri `_NewEnum` özelliğe . `IDispatch::Invoke` Ancak, Otomasyon istemcileri vtable üzerinden kalan yöntemlere erişebilir, bu nedenle ikili arabirimler dispinterfaces tercih edilir.

1. Çift arabirim veya dispinterface çalışma zamanında uzatılamayacaksa (diğer bir şekilde, fazladan `IDispatch::Invoke`yöntem veya özellik sağlamayacaksınız), tanımNıza **bitişik** özniteliği uygulamalısınız. Bu öznitelik, Otomasyon istemcilerinin derleme zamanında tam kod doğrulaması gerçekleştirmesini sağlar. Bu durumda, arabirim genişletilmemelidir.

1. Otomasyon istemcilerinin bu özelliği kullanabilmesini istiyorsanız, doğru DISPID önemlidir. (DISPID_NEWENUM'da yalnızca bir alt nokta olduğunu unutmayın.)

1. Herhangi bir değeri `Item` mülkün DISPID'i olarak sağlayabilirsiniz. Ancak, `Item` genellikle koleksiyonun varsayılan özelliği yapmak için DISPID_VALUE kullanır. Bu, Otomasyon istemcilerinin özelliğe açıkça isim vermeden başvurmasına olanak tanır.

1. `Item` Özelliğin geri dönüş değeri için kullanılan veri türü, COM istemcileri söz konusu olduğunda koleksiyonda depolanan maddenin türüdür. Arabirim dizeleri döndürür, bu nedenle standart COM dize türü, BSTR kullanmanız gerekir. Kısa bir süre içinde göreceğiniz verileri dahili olarak farklı bir biçimde depolayabilirsiniz.

1. `Count` Özelliğin DISPID için kullanılan değeri tamamen rasgele. Bu özellik için standart bir DISPID yok.

## <a name="creating-typedefs-for-storage-and-exposure"></a><a name="vcconstorage_and_exposure_typedefs"></a>Depolama ve Pozlama için Typedefs Oluşturma

Toplama arabirimi tanımlandıktan sonra, verilerin nasıl depolanacağına ve verilerin her yıl için nasıl açıkta kalınacağına karar vermeniz gerekir.

Bu soruların yanıtları, yeni oluşturulan sınıf için üstbilgi dosyasının en üstüne ekleyebileceğiniz bir dizi typedef şeklinde sağlanabilir:

[!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/cpp/implementing-an-stl-based-collection_2.h)]

Bu durumda, verileri std olarak **depolarsınız::std vektörü::string** s. **std::string** **std::vektör** yönetilen bir dizi gibi görünen bir C++ Standart Kitaplık kapsayıcı sınıfıdır. **std::string** C++ Standart Kitaplığı'nın string sınıfıdır. Bu sınıflar, bir dize koleksiyonuyla çalışmayı kolaylaştırır.

Visual Basic desteği bu arabirimin başarısı için hayati önem taşıdığından, `_NewEnum` özellik tarafından `IEnumVARIANT` döndürülen sayısallaştırıcı arabirimi desteklemelidir. Bu Visual Basic tarafından anlaşılan tek sayısal arayüzdür.

## <a name="creating-typedefs-for-copy-policy-classes"></a><a name="vcconcopy_classes"></a>Kopyalama İlkesi Sınıfları için Typedefs oluşturma

Şimdiye kadar oluşturduğunuz typedefs, sayısallaştırıcı ve koleksiyon tarafından kullanılacak kopya sınıfları için daha fazla typedef oluşturmak için ihtiyacınız olan tüm bilgileri sağlar:

[!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/cpp/implementing-an-stl-based-collection_3.h)]

Bu örnekte, `GenericCopy` [ATLCollections](../overview/visual-cpp-samples.md) örneğinden VCUE_Copy.h ve VCUE_CopyString.h'de tanımlanan özel sınıfı kullanabilirsiniz. Bu sınıfı başka kodlarda kullanabilirsiniz, ancak kendi koleksiyonlarınızda `GenericCopy` kullanılan veri türlerini desteklemek için daha fazla uzmanlık tanımlamanız gerekebilir. Daha fazla bilgi için [ATL Kopya İlkesi Sınıfları'na](../atl/atl-copy-policy-classes.md)bakın.

## <a name="creating-typedefs-for-enumeration-and-collection"></a><a name="vcconenumeration_and_collection"></a>Numaralandırma ve Toplama için Typedefoluşturma

Şimdi tüm şablon parametreleri ve `CComEnumOnSTL` `ICollectionOnSTLImpl` bu durum için sınıflar uzmanlaşmak için gerekli typedefs şeklinde sağlanmıştır. Uzmanlıkların kullanımını kolaylaştırmak için, aşağıda gösterildiği gibi iki yazı daha oluşturun:

[!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/cpp/implementing-an-stl-based-collection_4.h)]

Şimdi `CollectionType` daha önce tanımlanan `ICollectionOnSTLImpl` `IWords` arayüzü uygular ve destekleyen `IEnumVARIANT`bir sayısallaştırıcı sağlar bir uzmanlık için eşanlamlıdır.

## <a name="editing-the-wizard-generated-code"></a><a name="vcconedit_the_generated_code"></a>Sihirbaz Tarafından Oluşturulan Kodu Düzenleme

Şimdi, aşağıda `CWords` gösterildiği `IWords`gibi, typedef `CollectionType` yerine typedef tarafından temsil edilen arayüz uygulamasından türemelisiniz:

[!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/cpp/implementing-an-stl-based-collection_5.h)]

## <a name="adding-code-to-populate-the-collection"></a><a name="vcconpopulate_the_collection"></a>Koleksiyonu Doldurmak için Kod Ekleme

Geriye kalan tek şey vektörü verilerle doldurmak. Bu basit örnekte, sınıfın oluşturucusundaki koleksiyona birkaç sözcük ekleyebilirsiniz:

[!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/cpp/implementing-an-stl-based-collection_6.h)]

Şimdi, seçtiğiniz istemci ile kodu test edebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar ve Sayısallaştırıcılar](../atl/atl-collections-and-enumerators.md)<br/>
[ATLCollections Örnek](../overview/visual-cpp-samples.md)<br/>
[ATL Kopyalama İlkesi Sınıfları](../atl/atl-copy-policy-classes.md)
