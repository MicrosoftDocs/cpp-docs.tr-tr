---
title: '#içeri aktarma öznitelikleri (C++)'
ms.date: 11/04/2016
helpviewer_keywords:
- '#import directive, attributes'
ms.assetid: 2a5085e3-82ee-4f83-892b-0aa6cc13863b
ms.openlocfilehash: 954dfec50db75c0e3d11f0924b0ee398cd211fe1
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59036146"
---
# <a name="import-attributes-c"></a>#import Öznitelikleri (C++)
İle kullanılan öznitelikler için bağlantılar sağlar `#import` yönergesi.

**Microsoft'a özgü**

Aşağıdaki öznitelikler kullanılabilir `#import` yönergesi.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[auto_rename](../preprocessor/auto-rename.md)|Olası ad çakışmalarını çözmek için değişken adına iki alt çizgi (__) ekleyerek C++ ayrılmış sözcüklerini yeniden adlandırır.|
|[auto_search](../preprocessor/auto-search.md)|Tür kitaplığına #import ile başvurulduğunda ve kitaplığın kendisi başka bir tür kitaplığına başvurduğunda, derleyicinin diğer tür kitaplığı için örtük bir #import yapabileceğini belirtir.|
|[embedded_idl](../preprocessor/embedded-idl.md)|Tür kitaplığı .tlh dosyasına, öznitelik tarafından oluşturulan kod korunarak yazıldığını belirtir.|
|[Hariç tutma](../preprocessor/exclude-hash-import.md)|Öğeleri, oluşturulan tür kitaplığı üstbilgi dosyalarından çıkarır.|
|[high_method_prefix](../preprocessor/high-method-prefix.md)|Üst düzey özelliklere ve yöntemlere adlandırma olarak kullanılacak bir ön ekini belirtir.|
|[high_property_prefixes](../preprocessor/high-property-prefixes.md)|Diğer özellik yöntemi için alternatif önekler belirtir.|
|[implementation_only](../preprocessor/implementation-only.md)|.Tlh üst bilgi dosyası (birincil üstbilgi dosyası) oluşturulmasını engeller.|
|[include()](../preprocessor/include-parens.md)|Otomatik dışlama devre dışı bırakır.|
|[inject_statement](../preprocessor/inject-statement.md)|Bağımsız değişkenini tür kitaplığı üstbilgisine kaynak metin olarak ekler.|
|[named_guids](../preprocessor/named-guids.md)|Tanımlamak ve formun eski stilde GUID değişkenlerini başlatmak için derleyiciye `LIBID_MyLib`, `CLSID_MyCoClass`, `IID_MyInterface`, ve `DIID_MyDispInterface`.|
|[no_auto_exclude](../preprocessor/no-auto-exclude.md)|Otomatik dışlama devre dışı bırakır.|
|[no_dual_interfaces](../preprocessor/no-dual-interfaces.md)|Değişiklikleri derleyici yolu çift arabirim yöntemleri için sarmalayıcı işlevleri oluşturur.|
|[no_implementation](../preprocessor/no-implementation.md)|Kapsayıcı üye işlevleri uygulamalarını içeren .tli başlık oluşturulmasını bastırır.|
|[no_namespace](../preprocessor/no-namespace.md)|Ad alanı adı derleyici tarafından oluşturulmayan belirtir.|
|[no_registry](../preprocessor/no-registry.md)|Tür kitaplıkları için kayıt defterini aranmayacak derleyiciye bildirir.|
|[no_search_namespace](../preprocessor/no-search-namespace.md)|Aynı işlevlere sahip [no_namespace](../preprocessor/no-namespace.md) #import yönergesi ile kullandığınız tür kitaplıklarını kullanılır ancak öznitelik [auto_search](../preprocessor/auto-search.md) özniteliği.|
|[no_smart_pointers](../preprocessor/no-smart-pointers.md)|Tür kitaplığındaki tüm arabirimler için akıllı işaretçiler oluşturulmasını engeller.|
|[raw_dispinterfaces](../preprocessor/raw-dispinterfaces.md)|Dispinterface yöntemleri ve arama özellikleri için alt düzey sarmalayıcı işlevleri oluşturmak üzere derleyiciye `IDispatch::Invoke` ve HRESULT hata kodunu döndürür.|
|[raw_interfaces_only](../preprocessor/raw-interfaces-only.md)|Hata işleme sarmalayıcı işlevleri oluşturulmasını engeller ve [özelliği](../cpp/property-cpp.md) bu sarmalayıcı işlevleri bildirimleri.|
|[raw_method_prefix](../preprocessor/raw-method-prefix.md)|Ad çakışmalarını önlemek için farklı bir ön ekini belirtir.|
|[raw_native_types](../preprocessor/raw-native-types.md)|COM desteği sınıfları üst düzey sarmalayıcı işlevlerindeki kullanımını devre dışı bırakır ve bunun yerine alt düzey veri türleri kullanılmasını zorlar.|
|[raw_property_prefixes](../preprocessor/raw-property-prefixes.md)|Diğer özellik yöntemi için alternatif önekler belirtir.|
|[Yeniden adlandırma](../preprocessor/rename-hash-import.md)|Ad çakışması sorunlarını geçici olarak çalışır.|
|[rename_namespace](../preprocessor/rename-namespace.md)|Tür kitaplığı içeriğini içeren ad uzayı yeniden adlandırır.|
|[rename_search_namespace](../preprocessor/rename-search-namespace.md)|Aynı işlevlere sahip [rename_namespace](../preprocessor/rename-namespace.md) #import yönergesi ile kullandığınız tür kitaplıklarını kullanılır ancak öznitelik [auto_search](../preprocessor/auto-search.md) özniteliği.|
|[tlbid](../preprocessor/tlbid.md)|Birincil tür kitaplığı dışında kitaplıklarını yüklemek için sağlar.|

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)