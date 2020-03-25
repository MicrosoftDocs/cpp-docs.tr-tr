---
title: '#import öznitelikleri (C++)'
ms.date: 08/29/2019
helpviewer_keywords:
- '#import directive, attributes'
ms.assetid: 2a5085e3-82ee-4f83-892b-0aa6cc13863b
ms.openlocfilehash: fc2af69025d47a9ea6cea0e2c9e1423151b01606
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80215299"
---
# <a name="import-attributes-c"></a>#import öznitelikleri (C++)

`#import` yönergesinde kullanılan özniteliklere bağlantılar sağlar.

**Microsoft 'a özgü**

Aşağıdaki öznitelikler `#import` yönergesinde kullanılabilir.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[auto_rename](../preprocessor/auto-rename.md)|Olası ad çakışmalarını çözmek için değişken adına iki alt çizgi (__) ekleyerek C++ ayrılmış sözcüklerini yeniden adlandırır.|
|[auto_search](../preprocessor/auto-search.md)|Tür kitaplığına #import ile başvurulduğunda ve kitaplığın kendisi başka bir tür kitaplığına başvurduğunda, derleyicinin diğer tür kitaplığı için örtük bir #import yapabileceğini belirtir.|
|[embedded_idl](../preprocessor/embedded-idl.md)|Tür kitaplığının. tlh dosyasına yazıldığını ve bu kodun korunmayacağını belirtir.|
|[amaz](../preprocessor/exclude-hash-import.md)|Öğeleri, oluşturulan tür kitaplığı üstbilgi dosyalarından çıkarır.|
|[high_method_prefix](../preprocessor/high-method-prefix.md)|Üst düzey özellikleri ve yöntemleri adlandırırken kullanılacak ön eki belirtir.|
|[high_property_prefixes](../preprocessor/high-property-prefixes.md)|Diğer özellik yöntemi için alternatif önekler belirtir.|
|[implementation_only](../preprocessor/implementation-only.md)|. Tlh üst bilgi dosyasının (birincil üstbilgi dosyası) oluşturulmasını engeller.|
|[include()](../preprocessor/include-parens.md)|Otomatik dışlamayı devre dışı bırakır.|
|[inject_statement](../preprocessor/inject-statement.md)|Bağımsız değişkenini tür kitaplığı üstbilgisine kaynak metin olarak ekler.|
|[named_guids](../preprocessor/named-guids.md)|Derleyiciye, `LIBID_MyLib`, `CLSID_MyCoClass`, `IID_MyInterface`ve `DIID_MyDispInterface`biçiminde eski stilde GUID değişkenleri tanımlayıp başlatmasını söyler.|
|[no_auto_exclude](../preprocessor/no-auto-exclude.md)|Otomatik dışlamayı devre dışı bırakır.|
|[no_dual_interfaces](../preprocessor/no-dual-interfaces.md)|Derleyicinin çift arabirim yöntemleri için sarmalayıcı işlevleri üretme şeklini değiştirir.|
|[no_implementation](../preprocessor/no-implementation.md)|Sarmalayıcı üye işlevlerinin uygulamalarını içeren. TLI üst bilgisinin oluşturulmasını engeller.|
|[no_namespace](../preprocessor/no-namespace.md)|Ad alanı adının derleyici tarafından oluşturulduğunu belirtir.|
|[no_registry](../preprocessor/no-registry.md)|Derleyiciye tür kitaplıkları için kayıt defterinde arama olmadığını söyler.|
|[no_search_namespace](../preprocessor/no-search-namespace.md)|[No_namespace](../preprocessor/no-namespace.md) özniteliğiyle aynı işlevselliğe sahiptir, ancak #import yönergesini [auto_search](../preprocessor/auto-search.md) özniteliğiyle kullandığınız tür kitaplıklarında kullanılır.|
|[no_smart_pointers](../preprocessor/no-smart-pointers.md)|Tür kitaplığındaki tüm arabirimler için akıllı işaretçiler oluşturulmasını engeller.|
|[raw_dispinterfaces](../preprocessor/raw-dispinterfaces.md)|Derleyiciye, `IDispatch::Invoke` çağıran ve HRESULT hata kodunu döndüren dispınterface yöntemleri ve özellikleri için alt düzey sarmalayıcı işlevleri oluşturmasını söyler.|
|[raw_interfaces_only](../preprocessor/raw-interfaces-only.md)|Bu sarmalayıcı işlevlerini kullanan hata işleme sarmalayıcı işlevlerinin ve [özellik](../cpp/property-cpp.md) bildirimlerinin oluşturulmasını engeller.|
|[raw_method_prefix](../preprocessor/raw-method-prefix.md)|Ad çakışmalarını önlemek için farklı bir ön ek belirtir.|
|[raw_native_types](../preprocessor/raw-native-types.md)|Üst düzey sarmalayıcı işlevlerinde COM destek sınıflarının kullanımını devre dışı bırakır ve bunun yerine alt düzey veri türlerinin kullanılmasını zorlar.|
|[raw_property_prefixes](../preprocessor/raw-property-prefixes.md)|Diğer özellik yöntemi için alternatif önekler belirtir.|
|[Yeniden Adlandır](../preprocessor/rename-hash-import.md)|Ad çakışma sorunları etrafında çalışmaktadır.|
|[rename_namespace](../preprocessor/rename-namespace.md)|Tür kitaplığının içeriğini içeren ad alanını yeniden adlandırır.|
|[rename_search_namespace](../preprocessor/rename-search-namespace.md)|[Rename_namespace](../preprocessor/rename-namespace.md) özniteliğiyle aynı işlevselliğe sahiptir, ancak #import yönergesini [auto_search](../preprocessor/auto-search.md) özniteliğiyle kullandığınız tür kitaplıklarında kullanılır.|
|[tlbid](../preprocessor/tlbid.md)|Birincil tür kitaplığı dışındaki kitaplıkların yüklenmesine izin verir.|

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
