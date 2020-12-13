---
description: 'Hakkında daha fazla bilgi edinin: C++ standart Library-Based koleksiyonu uygulama'
title: C++ standart Library-Based koleksiyonu uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- ICollectionOnSTLImpl interface
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
ms.openlocfilehash: 4a403885a6fe66bf8e8578deeab05c7fc08e88a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152860"
---
# <a name="implementing-a-c-standard-library-based-collection"></a>C++ standart Library-Based koleksiyonu uygulama

ATL, `ICollectionOnSTLImpl` nesnelerinizde C++ standart kitaplık tabanlı koleksiyon arabirimlerini hızlıca uygulamanızı sağlamak için arabirim sağlar. Bu sınıfın nasıl çalıştığını anlamak için, otomasyon istemcilerine yönelik salt okunurdur bir koleksiyon uygulamak üzere bu sınıfı kullanan basit bir örnek (aşağıda) üzerinden çalışırsınız.

Örnek kod, [ATLCollections örneğinden](../overview/visual-cpp-samples.md)yapılır.

Bu yordamı gerçekleştirmek için şunları yapmanız gerekir:

- [Yeni bir basit nesne oluşturun](#vccongenerating_an_object).

- Oluşturulan arabirim için [IDL dosyasını düzenleyin](#vcconedit_the_idl) .

- Koleksiyon öğelerinin nasıl depolandığını ve COM arabirimleri aracılığıyla istemcilere nasıl sunularımı açıklayan [beş tür tanımları oluşturun](#vcconstorage_and_exposure_typedefs) .

- [Kopyalama ilkesi sınıfları için iki tür tanımları oluşturun](#vcconcopy_classes).

- [Numaralandırıcı ve koleksiyon uygulamaları için tür tanımları oluşturun](#vcconenumeration_and_collection).

- [Sihirbaz tarafından oluşturulan C++ kodunu, typedef koleksiyonunu kullanmak üzere düzenleyin](#vcconedit_the_generated_code).

- [Koleksiyonu doldurmak için kod ekleyin](#vcconpopulate_the_collection).

## <a name="generating-a-new-simple-object"></a><a name="vccongenerating_an_object"></a> Yeni basit nesne oluşturma

Uygulama ayarları altındaki öznitelikler kutusunun temizlenmiş olduğundan emin olmak için yeni bir proje oluşturun. ATL Sınıf Ekle iletişim kutusunu ve basit nesne ekleme Sihirbazı 'Nı kullanarak adlı basit bir nesne oluşturun `Words` . Adlı bir çift arabirimin oluşturulduğundan emin olun `IWords` . Oluşturulan sınıfın nesneleri, bir sözcük koleksiyonunu (yani dizeler) göstermek için kullanılacaktır.

## <a name="editing-the-idl-file"></a><a name="vcconedit_the_idl"></a> IDL dosyasını düzenleniyor

Şimdi, IDL dosyasını açın ve `IWords` aşağıda gösterildiği gibi, salt okunurdur bir koleksiyon arabirimine açmak için gereken üç özelliği ekleyin:

[!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/cpp/implementing-an-stl-based-collection_1.idl)]

Bu, Otomasyon istemcileri göz önünde bulundurularak tasarlanan salt okunurdur bir koleksiyon arabirimine yönelik standart bir formdur. Bu arabirim tanımındaki numaralandırılmış açıklamalar aşağıdaki açıklamalara karşılık gelir:

1. Automation istemcileri özelliği aracılığıyla özelliğine eriştiği için koleksiyon arabirimleri genellikle çift olur `_NewEnum` `IDispatch::Invoke` . Ancak, Otomasyon istemcileri kalan yöntemlere vtable aracılığıyla erişebilir, bu nedenle çift arabirimlerin dispınterfaces için tercih edilir.

1. Çift arabirim veya dispınterface çalışma zamanında uzatılmazsa (yani, aracılığıyla ek yöntemler veya özellikler sağlamayacağınızı `IDispatch::Invoke` ), tanımınıza **genişletilebilen olmayan** özniteliği uygulamanız gerekir. Bu öznitelik, Otomasyon istemcilerinin derleme zamanında tam kod doğrulaması gerçekleştirmesini sağlar. Bu durumda, arabirim genişletilmemelidir.

1. Otomasyon istemcilerinin bu özelliği kullanabiliyor olması için doğru DISPID önemlidir. (DISPID_NEWENUM içinde yalnızca bir alt çizgi olduğunu unutmayın.)

1. Özelliğin DISPID değeri olarak herhangi bir değer sağlayabilirsiniz `Item` . Ancak, `Item` genellikle koleksiyonun varsayılan özelliği yapmak için DISPID_VALUE kullanır. Bu, Otomasyon istemcilerinin özelliği açıkça adlandırmadan özelliğe başvurmasını sağlar.

1. Özelliğin dönüş değeri için kullanılan veri türü, `Item` com istemcilerinin endişeleri olduğu sürece koleksiyonda depolanan öğenin türüdür. Arabirim dizeleri döndürür, bu yüzden standart COM dize türü olan BSTR 'yi kullanmanız gerekir. Kısa süre içinde gördüğünüz gibi verileri farklı bir biçimde kaydedebilirsiniz.

1. Özelliğin DISPID değeri için kullanılan değer `Count` tamamen rastgele. Bu özellik için standart bir DISPID yok.

## <a name="creating-typedefs-for-storage-and-exposure"></a><a name="vcconstorage_and_exposure_typedefs"></a> Depolama ve pozlama için Typedefs oluşturma

Koleksiyon arabirimi tanımlandıktan sonra, verilerin nasıl depolanacağını ve verilerin Numaralandırıcı aracılığıyla nasıl sunulamayacağına karar vermeniz gerekir.

Bu soruların yanıtları, yeni oluşturulan sınıfınız için üst bilgi dosyasının en üstüne ekleyebileceğiniz bir dizi Typedefs biçiminde temin edilebilir:

[!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/cpp/implementing-an-stl-based-collection_2.h)]

Bu durumda, verileri **std::** STRING of std:: **String** s olarak depolayacaksınız. **std:: vector** , yönetilen bir dizi gibi davranan bir C++ standart kitaplık kapsayıcı sınıfıdır. **std:: String** , C++ standart kitaplığının dize sınıfıdır. Bu sınıflar, dizelerin bir koleksiyonuyla çalışmayı kolaylaştırır.

Visual Basic desteği bu arabirimin başarısı için önemli olduğundan, özelliği tarafından döndürülen Numaralandırıcı `_NewEnum` `IEnumVARIANT` arabirimi desteklemelidir. Bu, Visual Basic tarafından anlaşılan tek Numaralandırıcı arabirimidir.

## <a name="creating-typedefs-for-copy-policy-classes"></a><a name="vcconcopy_classes"></a> Kopyalama Ilkesi sınıfları için Typedefs oluşturma

Şimdiye kadar oluşturduğunuz tür tanımları, Numaralandırıcı ve koleksiyon tarafından kullanılacak kopya sınıfları için daha fazla tür tanımları oluşturmak için gereken tüm bilgileri sağlayın:

[!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/cpp/implementing-an-stl-based-collection_3.h)]

Bu örnekte, `GenericCopy` [ATLCollections](../overview/visual-cpp-samples.md) örneğindeki VCUE_Copy. h ve VCUE_CopyString. h içinde tanımlanan özel sınıfı kullanabilirsiniz. Bu sınıfı başka bir kodda kullanabilirsiniz, ancak `GenericCopy` kendi Koleksiyonlarınızdan kullanılan veri türlerini desteklemek için daha fazla özelleştirilmiş ' ı tanımlamanız gerekebilir. Daha fazla bilgi için bkz. [ATL kopyalama Ilkesi sınıfları](../atl/atl-copy-policy-classes.md).

## <a name="creating-typedefs-for-enumeration-and-collection"></a><a name="vcconenumeration_and_collection"></a> Numaralandırma ve koleksiyon için Typedefs oluşturma

Artık bu durum için ve sınıflarını özelleştirmek için gereken tüm şablon parametreleri, `CComEnumOnSTL` `ICollectionOnSTLImpl` Typedefs biçiminde sunulmaktadır. Uzmanlık kullanımını basitleştirmek için, aşağıda gösterildiği gibi iki tür daha daha oluşturun:

[!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/cpp/implementing-an-stl-based-collection_4.h)]

Şimdi, `CollectionType` `ICollectionOnSTLImpl` `IWords` daha önce tanımlanan arabirimi uygulayan ve tarafından desteklenen bir Numaralandırıcı sağlayan bir özelleşmenin eşanlamlısıdır `IEnumVARIANT` .

## <a name="editing-the-wizard-generated-code"></a><a name="vcconedit_the_generated_code"></a> Wizard-Generated kodu düzenleniyor

Şimdi `CWords` `CollectionType` `IWords` aşağıda gösterildiği gibi, TypeDef ile temsil edilen arabirim uygulamasından türemeniz gerekir:

[!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/cpp/implementing-an-stl-based-collection_5.h)]

## <a name="adding-code-to-populate-the-collection"></a><a name="vcconpopulate_the_collection"></a> Koleksiyonu doldurmak için kod ekleme

Kalan tek şey, vektörü verilerle doldurmaktır. Bu basit örnekte, sınıfının oluşturucusunda, koleksiyona birkaç sözcük ekleyebilirsiniz:

[!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/cpp/implementing-an-stl-based-collection_6.h)]

Artık kodu tercih ettiğiniz istemciyle test edebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar ve Numaralandırıcılar](../atl/atl-collections-and-enumerators.md)<br/>
[ATLCollections örneği](../overview/visual-cpp-samples.md)<br/>
[ATL kopyalama Ilkesi sınıfları](../atl/atl-copy-policy-classes.md)
