---
title: TypeDef, Enum, Union ve Struct öznitelikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- union attributes
- attributes [C++], reference topics
- struct attributes
- typedef attributes
- enum attributes
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c14881afd000dc5fb4223a2ecfa9dcdc67e7b541
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891837"
---
# <a name="typedef-enum-union-and-struct-attributes"></a>Typedef, Enum, Union ve Struct Öznitelikleri
Aşağıdaki öznitelikler uygulamak [typedef](http://msdn.microsoft.com/en-us/cc96cf26-ba93-4179-951e-695d1f5fdcf1), [yapısı](../cpp/struct-cpp.md), ve [enum](../cpp/enumerations-cpp.md) C++ anahtar sözcükleri.  
  
### <a name="typedef"></a>typedef  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|[Durumu](../windows/case-cpp.md)|İle kullanılan [switch_type](../windows/switch-type.md) özniteliğini bir **UNION**.|  
|[Özel](../windows/custom-cpp.md)|Kendi özniteliğinizi tanımlamanıza olanak sağlar.|  
|[export](../windows/export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesini neden olur.|  
|[first_is](../windows/first-is.md)|Aktarılacak ilk dizi öğenin dizinini belirtir.|  
|[helpcontext](../windows/helpcontext.md)|Kullanıcı görünümü öğeyle ilgili bilgi bu Yardım dosyasındaki olanak sağlayan bir içerik Kimliğini belirtir.|  
|[helpfile](../windows/helpfile.md)|Tür Kitaplığı Yardım dosyasının adını ayarlar.|  
|[helpstring](../windows/helpstring.md)|Uygulandığı öğe tanımlamak için kullanılan bir karakter dizesini belirtir.|  
|[library_block](../windows/library-block.md)|.İdl dosyanın kitaplığı bloktaki bir yapı yerleştirir.|  
|[ptr](../windows/ptr.md)|Bir işaretçi tam bir işaretçi olarak belirler.|  
|[public](../windows/public-cpp-attributes.md)|Bu gelen .idl dosya içinde başvurulmuyor olsa bile bir typedef türü kitaplığa gider sağlar.|  
|[ref](../windows/ref-cpp.md)|Bir başvuru işaretçi tanımlar.|  
|[switch_is](../windows/switch-is.md)|İfade veya bileşim üyesi seçer birleşim discriminant işlev gören tanımlayıcısını belirtir.|  
|[switch_type](../windows/switch-type.md)|Birleşim discriminant kullanılan değişken türünü tanımlar.|  
|[Benzersiz](../windows/unique-cpp.md)|Benzersiz bir işaretçi belirtir.|  
|[wire_marshal](../windows/wire-marshal.md)|Bir uygulamaya özgü veri türü yerine iletim için kullanılacak bir veri türünü belirtir.|  
  
### <a name="enum"></a>enum  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|[Özel](../windows/custom-cpp.md)|Kendi özniteliğinizi tanımlamanıza olanak sağlar.|  
|[export](../windows/export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesini neden olur.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Sınıfta veya arabirimde benzersiz Kimliğini belirtir.|  
|[v1_enum](../windows/v1-enum.md)|Belirtilen enum türü 16 bit varsayılan yerine bir 32 bit varlık olarak iletilmesi yönlendirir.|  
  
### <a name="union"></a>birleşim  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|[Özel](../windows/custom-cpp.md)|Kendi özniteliğinizi tanımlamanıza olanak sağlar.|  
|[export](../windows/export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesini neden olur.|  
|[first_is](../windows/first-is.md)|Aktarılacak ilk dizi öğenin dizinini belirtir.|  
|[last_is](../windows/last-is.md)|Aktarılacak son dizi öğesinden dizinini belirtir.|  
|[length_is](../windows/length-is.md)|Aktarılacak dizi öğelerinin sayısını belirtir.|  
|[max_is](../windows/max-is.md)|Geçerli dizi dizini için maksimum değeri belirler.|  
|[size_is](../windows/size-is.md)|Bellek boyutu boyutlu işaretçileri ayrılmış, boyutlu işaretçiler ve tek veya çok boyutlu diziler işaretçileri boyutta belirtir.|  
|[Benzersiz](../windows/unique-cpp.md)|Benzersiz bir işaretçi belirtir.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Sınıfta veya arabirimde benzersiz Kimliğini belirtir.|  
  
### <a name="nonencapsulated-union"></a>Nonencapsulated birleşimi  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|[ms_union](../windows/ms-union.md)|Ağ veri gösterimi hizalama nonencapsulated birleşimler denetler.|  
|[no_injected_text](../windows/no-injected-text.md)|Özellik kullanımı sonucunda kodu injecting derleyici engeller.|  
  
### <a name="struct"></a>struct   
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|[toplanabilir](../windows/aggregatable.md)|Sınıf toplama desteklediğini belirtir.|  
|[toplamlar](../windows/aggregates.md)|Bir denetim hedef sınıf toplayan gösterir.|  
|[appobject](../windows/appobject.md)|Bir tam .exe uygulamayla ilişkili olan ve bu tür kitaplığında coclass'ı özellikleri ve işlevleri genel olarak kullanılabilir olduğunu gösterir bir uygulama nesnesi olarak coclass'ı tanımlar.|  
|[coclass](../windows/coclass.md)|ActiveX denetimi oluşturur.|  
|[com_interface_entry](../windows/com-interface-entry-cpp.md)|Bir arabirim giriş COM Haritası ekler.|  
|[control](../windows/control.md)|Kullanıcı tanımlı tür denetim olduğunu belirtir.|  
|[Özel](../windows/custom-cpp.md)|Kendi özniteliğinizi tanımlamanıza olanak sağlar.|  
|[db_column](../windows/db-column.md)|Belirtilen sütun, satır kümesine bağlar.|  
|[db_command](../windows/db-command.md)|OLE DB komut oluşturur.|  
|[db_param](../windows/db-param.md)|Belirtilen üye değişkeni bir giriş veya çıkış parametresi ile ilişkilendirir ve değişken sınırlandırır.|  
|[db_source](../windows/db-source.md)|Bir veri kaynağı için bir bağlantı oluşturur.|  
|[db_table](../windows/db-table.md)|OLE DB tablo açar.|  
|[default](../windows/default-cpp.md)|Özel veya görüntüleme arabirimi coclass'ı içinde tanımlanan varsayılan programlama arabirimi temsil ettiğini gösterir.|  
|[defaultvtable](../windows/defaultvtable.md)|Bir denetim için varsayılan vtable arabirimi olarak bir arabirim tanımlar.|  
|[event_receiver](../windows/event-receiver.md)|Olay alıcısı oluşturur.|  
|[event_source](../windows/event-source.md)|Bir olay kaynağı oluşturur.|  
|[export](../windows/export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesini neden olur.|  
|[first_is](../windows/first-is.md)|Aktarılacak ilk dizi öğenin dizinini belirtir.|  
|[hidden](../windows/hidden.md)|Öğe var, ancak kullanıcı odaklı bir tarayıcıda görüntülenmemelidir olduğunu gösterir.|  
|[implements_category](../windows/implements-category.md)|Sınıfı için uygulanan bileşen kategorileri belirtir.|  
|[last_is](../windows/last-is.md)|Aktarılacak son dizi öğesinden dizinini belirtir.|  
|[length_is](../windows/length-is.md)|Aktarılacak dizi öğelerinin sayısını belirtir.|  
|[max_is](../windows/max-is.md)|Geçerli dizi dizini için maksimum değeri belirler.|  
|[requires_category](../windows/requires-category.md)|Hedef sınıf gerekli bir bileşen kategorilerini belirtir.|  
|[size_is](../windows/size-is.md)|Bellek boyutu boyutlu işaretçileri ayrılmış, boyutlu işaretçiler ve tek veya çok boyutlu diziler işaretçileri boyutta belirtir.|  
|[Kaynak](../windows/source-cpp.md)|Bir sınıf üzerinde bağlantı noktaları için COM nesnesinin kaynak arabirimleri belirtir. Özellik veya yöntem üye nesne veya olay kaynağı değişken döndürdüğünü gösterir.|  
|[İş parçacığı oluşturma](../windows/threading-cpp.md)|Bir COM nesnesi için iş parçacığı modelini belirtir.|  
|[Benzersiz](../windows/unique-cpp.md)|Benzersiz bir işaretçi belirtir.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Sınıfta veya arabirimde benzersiz Kimliğini belirtir.|  
|[Sürüm](../windows/version-cpp.md)|Bir sınıfın birden çok sürümü arasında belirli bir sürümünü tanımlar.|  
|[vi_progid](../windows/vi-progid.md)|Sürüm bağımsız form ProgID belirtir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıma Göre Öznitelikler](../windows/attributes-by-usage.md)