---
title: C++ Standart Kitaplığı tabanlı bir koleksiyon uygulama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ICollectionOnSTLImpl interface
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14a09f54598b525346a65b56a335711f114878cb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="implementing-a-c-standard-library-based-collection"></a>C++ Standart Kitaplığı tabanlı bir koleksiyon uygulama
ATL sağlar `ICollectionOnSTLImpl` C++ Standart Kitaplığı tabanlı koleksiyon arabirimleri nesneleriniz hızlıca uygulamak etkinleştirmek için arabirim. Bu sınıf nasıl çalıştığını anlamak için Otomasyon istemcilerinde amaçlayan bir salt okunur koleksiyonun uygulamak için bu sınıf kullanan basit bir örnek (aşağıda) üzerinden çalışır.  
  
 Örnek kod arasındadır [ATLCollections örnek](../visual-cpp-samples.md).  
  
 Bu yordamı tamamlamak için şunları yapacaksınız:  
  
-   [Yeni Basit bir nesne oluştur](#vccongenerating_an_object).  
  
-   [IDL dosyasını düzenleyin](#vcconedit_the_idl) oluşturulan arabirimi.  
  
-   [Beş tür tanımları oluşturma](#vcconstorage_and_exposure_typedefs) koleksiyon öğeleri nasıl depolanır ve nasıl bunlar COM arabirimleri aracılığıyla istemcilere sunulur açıklayan.  
  
-   [Kopyalama için iki tür tanımları İlkesi sınıfları oluşturmak](#vcconcopy_classes).  
  
-   [Numaralandırıcı ve koleksiyon uygulamaları için tür tanımları oluşturma](#vcconenumeration_and_collection).  
  
-   [Koleksiyon typedef kullanmak için sihirbaz tarafından oluşturulan C++ kodu düzenleme](#vcconedit_the_generated_code).  
  
-   [Koleksiyon doldurmak için kodu ekleyin](#vcconpopulate_the_collection).  
  
##  <a name="vccongenerating_an_object"></a> Yeni Basit bir nesne oluşturma  
 Uygulama ayarları öznitelikleri kutusunun temizlenmiş olduğundan emin olduktan yeni bir proje oluşturun. ATL Sınıf Ekle iletişim kutusunu kullanın ve ekleme Basit Nesne basit bir nesne oluşturmak için Sihirbazı adlı `Words`. Çift arabirim adlı emin olun `IWords` oluşturulur. Oluşturulan sınıfın nesnelerini sözcükler (dize) koleksiyonunu temsil etmek için kullanılır.  
  
##  <a name="vcconedit_the_idl"></a> IDL dosya düzenleme  
 Şimdi, IDL dosyasını açın ve etkinleştirmek için gereken üç özellik eklemek `IWords` aşağıda gösterildiği gibi bir salt okunur koleksiyonun arabirimi içine:  
  
 [!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/cpp/implementing-an-stl-based-collection_1.idl)]  
  
 Bu Otomasyon istemcileri aklınızda tasarlanan bir salt okunur koleksiyonun arabiriminin standart formdur. Bu arabirim tanımı numaralı açıklamaları aşağıdaki açıklamaları karşılık gelir:  
  
1.  Otomasyon istemcileri eriştiği için koleksiyon arabirimleri genellikle çift `_NewEnum` özelliği aracılığıyla **IDispatch::Invoke**. Ancak, çift arabirimler dispinterfaces için tercih edilir şekilde Otomasyon istemcileri kalan yöntemleri vtable aracılığıyla erişebilirsiniz.  
  
2.  Bir çift arabirim veya görüntüleme arabirimi çalışma zamanında genişletilmiş değil, (diğer bir deyişle, ek yöntemleri veya özellikleri aracılığıyla sağlamayacak **IDispatch::Invoke**), uygulamanız gerekir **nonextensible** özniteliğini tanımınızı. Bu öznitelik, derleme zamanında tam kod doğrulama gerçekleştirmek Otomasyonu istemcilerin sağlar. Bu durumda, genişletilmiş arabirimi değil.  
  
3.  Otomasyon istemcilerin bu özelliği kullanmak istiyorsanız, doğru DISPID önemlidir. (Yalnızca bir alt çizgi, olduğuna dikkat edin **DISPID_NEWENUM**.)  
  
4.  Herhangi bir değer DISPID sağlayabilir **öğesi** özelliği. Ancak, **öğesi** genellikle kullandığı **DISPID_VALUE** koleksiyonun varsayılan özelliği yapma. Bu, açıkça adlandırma olmadan özelliğine başvurmak Otomasyon istemcileri sağlar.  
  
5.  Dönüş değeri için kullanılan veri türünü **öğesi** COM istemcileri endişe kadar bir koleksiyonda depolanan öğesi türü bir özelliktir. Standart COM dize türü kullanması gereken şekilde arabirimi dizeler, döndürüyor `BSTR`. Kısa süre içinde anlatıldığı gibi verileri farklı bir biçimde dahili olarak depolayabilirsiniz.  
  
6.  DISPID için kullanılan değer **sayısı** özelliği tamamen rastgele. Bu özellik için standart hiçbir DISPID yoktur.  
  
##  <a name="vcconstorage_and_exposure_typedefs"></a> Depolama ve Etkilenme için tür tanımları oluşturma  
 Koleksiyon arabirimi tanımlandıktan sonra veriler nasıl depolanır ve nasıl veri Numaralandırıcı sunulur karar vermeniz gerekir.  
  
 Bu sorulara verdiğiniz yanıtlar, yeni oluşturulan sınıfınız için üstbilgi dosyanın en üstüne ekleyebilmeniz için tür tanımları sayısı biçiminde sağlanabilir:  
  
 [!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/cpp/implementing-an-stl-based-collection_2.h)]  
  
 Bu durumda, verileri olarak depolayacak bir **std::vector** , **std::string**s. **Std::Vector** yönetilen bir dizi gibi davranan bir C++ Standart Kitaplığı kapsayıcı sınıftır. **Std::String** C++ Standart Kitaplığı'nın dize sınıfıdır. Bu sınıfların dizeleri koleksiyonu ile çalışmak kolaylaştırır.  
  
 Visual Basic desteği bu arabirim başarısı için önemli olduğundan, numaralandırıcı tarafından döndürülen `_NewEnum` özelliği desteklemelidir **IEnumVARIANT** arabirimi. Bu, Visual Basic tarafından anlaşılan yalnızca Numaralandırıcı arabirimidir.  
  
##  <a name="vcconcopy_classes"></a> Kopya İlkesi sınıflar için tür tanımları oluşturma  
 Şu ana kadar oluşturduğunuz tür tanımları daha Numaralandırıcı ve koleksiyon tarafından kullanılacak kopyalama sınıfları için tür tanımları oluşturmak gereken tüm bilgileri sağlayın:  
  
 [!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/cpp/implementing-an-stl-based-collection_3.h)]  
  
 Bu örnekte, özel kullanabilirsiniz `GenericCopy` VCUE_Copy.h ve VCUE_CopyString.h gelen tanımlanmış sınıf [ATLCollections](../visual-cpp-samples.md) örnek. Bu sınıf diğer kodda kullanabilirsiniz, ancak daha fazla özelleştirmeleri, tanımlamanız gerekebilir `GenericCopy` kendi koleksiyonlarınızı kullanılan veri türlerini desteklemek için. Daha fazla bilgi için bkz: [ATL kopyalama İlkesi sınıfları](../atl/atl-copy-policy-classes.md).  
  
##  <a name="vcconenumeration_and_collection"></a> Numaralandırma ve koleksiyon için tür tanımları oluşturma  
 Şimdi tüm şablon parametreleri özelleştirmek üzere gerekli `CComEnumOnSTL` ve `ICollectionOnSTLImpl` sınıflar bu durum için tür tanımları formunda sağlandı. Özelleştirmeleri kullanımını kolaylaştırmak için aşağıda gösterildiği gibi iki daha fazla tür tanımları oluşturun:  
  
 [!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/cpp/implementing-an-stl-based-collection_4.h)]  
  
 Şimdi `CollectionType` bir alt uzmanlaşması eşanlamlısı olan `ICollectionOnSTLImpl` uygulayan `IWords` arabirimi, daha önce tanımlanan ve destekleyen bir numaralandırıcı sağlar **IEnumVARIANT**.  
  
##  <a name="vcconedit_the_generated_code"></a> Sihirbaz tarafından oluşturulan kod düzenleme  
 Türetilmesi gerekir artık `CWords` tarafından temsil edilen arabirimi uygulamadan `CollectionType` typedef yerine `IWords`, aşağıda gösterildiği gibi:  
  
 [!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/cpp/implementing-an-stl-based-collection_5.h)]  
  
##  <a name="vcconpopulate_the_collection"></a> Koleksiyon doldurmak için kod ekleme  
 Vektör verilerle doldurmak için kalan tek şey. Bu basit örnekte koleksiyonuna sınıfa ilişkin oluşturucuda birkaç sözcük ekleyebilirsiniz:  
  
 [!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/cpp/implementing-an-stl-based-collection_6.h)]  
  
 Şimdi, tercih ettiğiniz istemcisiyle sınayabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koleksiyonlar ve numaralandırmalar](../atl/atl-collections-and-enumerators.md)   
 [ATLCollections örnek](../visual-cpp-samples.md)   
 [ATL Kopyalama İlkesi Sınıfları](../atl/atl-copy-policy-classes.md)

