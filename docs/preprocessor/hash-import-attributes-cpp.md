---
title: "#<a name=\"import-attributes-c--microsoft-docs\"></a>Öznitelikler (C++) alma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: '#import directive, attributes'
ms.assetid: 2a5085e3-82ee-4f83-892b-0aa6cc13863b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fd11326e33ff783b3868215794f9803e97d41c55
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="import-attributes-c"></a>#import Öznitelikleri (C++)
#İmport yönergesi ile kullanılan öznitelikler için bağlantılar sağlar.  
  
 **Microsoft özel**  
  
 Aşağıdaki öznitelikler #import yönergesi için kullanılabilir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|[auto_rename](../preprocessor/auto-rename.md)|Olası ad çakışmalarını çözmek için değişken adına iki alt çizgi (__) ekleyerek C++ ayrılmış sözcüklerini yeniden adlandırır.|  
|[auto_search](../preprocessor/auto-search.md)|Tür kitaplığına #import ile başvurulduğunda ve kitaplığın kendisi başka bir tür kitaplığına başvurduğunda, derleyicinin diğer tür kitaplığı için örtük bir #import yapabileceğini belirtir.|  
|[embedded_idl](../preprocessor/embedded-idl.md)|Tür kitaplığı, öznitelik oluşturulan kod korunur .tlh dosyasına yazılır belirtir.|  
|[hariç tutma](../preprocessor/exclude-hash-import.md)|Öğeleri, oluşturulan tür kitaplığı üstbilgi dosyalarından çıkarır.|  
|[high_method_prefix](../preprocessor/high-method-prefix.md)|Üst düzey özellikleri ve yöntemleri adlandırmada kullanılacak öneki belirtir.|  
|[high_property_prefixes](../preprocessor/high-property-prefixes.md)|Diğer özellik yöntemi için alternatif önekler belirtir.|  
|[implementation_only](../preprocessor/implementation-only.md)|.Tlh üstbilgi dosyası (birincil üstbilgi dosyası) oluşturulmasını engeller.|  
|[include()](../preprocessor/include-parens.md)|Otomatik dışlama devre dışı bırakır.|  
|[inject_statement](../preprocessor/inject-statement.md)|Bağımsız değişkenini tür kitaplığı üstbilgisine kaynak metin olarak ekler.|  
|[named_guids](../preprocessor/named-guids.md)|Formun eski stildeki GUID değişkenlerini başlatmak ve tanımlamak için derleyici söyler **LIBID_MyLib**, **CLSID_MyCoClass**, **IID_MyInterface**, ve **DIID _MyDispInterface**.|  
|[no_auto_exclude](../preprocessor/no-auto-exclude.md)|Otomatik dışlama devre dışı bırakır.|  
|[no_dual_interfaces](../preprocessor/no-dual-interfaces.md)|Değişiklikleri derleyici yolu çift arabirim yöntemleri için sarmalayıcı işlevleri oluşturur.|  
|[no_implementation](../preprocessor/no-implementation.md)|Sarmalayıcı üye işlevleri uygulamaları içeren .tli üstbilgi nesil gizler.|  
|[no_namespace](../preprocessor/no-namespace.md)|Ad alanı adı derleyici tarafından oluşturulmayan belirtir.|  
|[no_registry](../preprocessor/no-registry.md)|Tür kitaplıkları için kayıt defterini aramak için değil derleyici söyler.|  
|[no_search_namespace](../preprocessor/no-search-namespace.md)|Aynı işlevselliğe sahip [no_namespace](../preprocessor/no-namespace.md) özniteliği ancak #import yönergesi ile kullandığınız tür kitaplıklarının kullanılan [auto_search](../preprocessor/auto-search.md) özniteliği.|  
|[no_smart_pointers](../preprocessor/no-smart-pointers.md)|Tür Kitaplığı'nda tüm arabirimler için akıllı işaretçiler oluşturulmasını önler.|  
|[raw_dispinterfaces](../preprocessor/raw-dispinterfaces.md)|Alt düzey sarmalayıcı işlevleri görüntüleme arabirimi yöntemleri ve arama özellikleri için oluşturulacak derleyici söyler **IDispatch::Invoke** ve geri dönüp `HRESULT` hata kodu.|  
|[raw_interfaces_only](../preprocessor/raw-interfaces-only.md)|Hata işleme sarmalayıcı işlevleri oluşturulmasını önler ve [özelliği](../cpp/property-cpp.md) bu sarmalayıcı işlevleri kullanmak bildirimleri.|  
|[raw_method_prefix](../preprocessor/raw-method-prefix.md)|Ad çakışmaları önlemek için farklı bir önek belirtir.|  
|[raw_native_types](../preprocessor/raw-native-types.md)|COM desteği sınıfları üst düzey sarmalayıcı işlevlerinde kullanımını devre dışı bırakır ve bunun yerine alt düzey veri türlerinin zorlar.|  
|[raw_property_prefixes](../preprocessor/raw-property-prefixes.md)|Diğer özellik yöntemi için alternatif önekler belirtir.|  
|[Yeniden Adlandır](../preprocessor/rename-hash-import.md)|Ad çakışma sorunlarını çözmek çalışır.|  
|[rename_namespace](../preprocessor/rename-namespace.md)|Tür kitaplığı içeriğini içeren ad alanını yeniden adlandırır.|  
|[rename_search_namespace](../preprocessor/rename-search-namespace.md)|Aynı işlevselliğe sahip [rename_namespace](../preprocessor/rename-namespace.md) özniteliği ancak #import yönergesi ile kullandığınız tür kitaplıklarının kullanılan [auto_search](../preprocessor/auto-search.md) özniteliği.|  
|[tlbid](../preprocessor/tlbid.md)|Birincil tür kitaplığı dışında kitaplıkları yüklenmesini sağlar.|  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)