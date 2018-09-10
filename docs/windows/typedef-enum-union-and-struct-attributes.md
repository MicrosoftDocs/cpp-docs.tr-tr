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
- attributes [C++/CLI], reference topics
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 74e9bbf3ad593f5ce1e6d1868d8e1a09b0bd885e
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44314605"
---
# <a name="typedef-enum-union-and-struct-attributes"></a>Typedef, Enum, Union ve Struct Öznitelikleri

Aşağıdaki öznitelikler uygulamak [typedef](../cpp/aliases-and-typedefs-cpp.md), [yapı](../cpp/struct-cpp.md), ve [enum](../cpp/enumerations-cpp.md) C++ anahtar sözcükleri.

### <a name="typedef"></a>typedef

|Öznitelik|Açıklama|
|---------------|-----------------|
|[Servis talebi](../windows/case-cpp.md)|İle kullanılan [switch_type](../windows/switch-type.md) özniteliğini bir **birleşim**.|
|[Özel](../windows/custom-cpp.md)|Kendi özniteliğinizi tanımlamanızı sağlar.|
|[export](../windows/export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesine neden olur.|
|[first_is](../windows/first-is.md)|Aktarılacak ilk dizi öğesinin dizinini belirtir.|
|[helpcontext](../windows/helpcontext.md)|Kullanıcı Yardım dosyasında bu öğe hakkındaki bilgileri görüntüleme sağlayan bir bağlam kimliği belirtir.|
|[helpfile](../windows/helpfile.md)|Bir tür kitaplığı için Yardım dosyasına adını ayarlar.|
|[helpstring](../windows/helpstring.md)|Uygulandığı öğe açıklamak için kullanılan bir karakter dizesi belirtir.|
|[library_block](../windows/library-block.md)|.İdl dosyasının kitaplığı bloğu içinde bir yapısı yerleştirir.|
|[ptr](../windows/ptr.md)|Bir işaretçinin tam bir işaretçi olarak belirler.|
|[public](../windows/public-cpp-attributes.md)|Bu gelen .idl dosyasında başvurulmuyor olsa bile bir typedef tür kitaplığına geçer sağlar.|
|[ref](../windows/ref-cpp.md)|Bir başvuru işaretçi tanımlar.|
|[switch_is](../windows/switch-is.md)|İfade veya birleşim üyesi seçer birleşim discriminant davranan tanımlayıcısını belirtir.|
|[switch_type](../windows/switch-type.md)|Birleşim discriminant kullanılan değişkenin türünü tanımlar.|
|[benzersiz](../windows/unique-cpp.md)|Bir benzersiz işaretçi belirtir.|
|[wire_marshal](../windows/wire-marshal.md)|Bir uygulamaya özel veri türü yerine iletim için kullanılacak olan veri türünü belirtir.|

### <a name="enum"></a>enum

|Öznitelik|Açıklama|
|---------------|-----------------|
|[Özel](../windows/custom-cpp.md)|Kendi özniteliğinizi tanımlamanızı sağlar.|
|[export](../windows/export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesine neden olur.|
|[uuid](../windows/uuid-cpp-attributes.md)|Bir sınıf veya arabirim için benzersiz Kimliğini belirtir.|
|[v1_enum](../windows/v1-enum.md)|Belirtilen listeden seçimli türü 16-bit varsayılan yerine bir 32-bit varlık olarak iletilmesi yönlendirir.|

### <a name="union"></a>birleşim

|Öznitelik|Açıklama|
|---------------|-----------------|
|[Özel](../windows/custom-cpp.md)|Kendi özniteliğinizi tanımlamanızı sağlar.|
|[export](../windows/export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesine neden olur.|
|[first_is](../windows/first-is.md)|Aktarılacak ilk dizi öğesinin dizinini belirtir.|
|[last_is](../windows/last-is.md)|Aktarılacak olan son dizi öğenin dizinini belirtir.|
|[length_is](../windows/length-is.md)|Aktarılacak dizi öğelerinin sayısını belirtir.|
|[max_is](../windows/max-is.md)|Geçerli dizi dizini için maksimum değeri atar.|
|[size_is](../windows/size-is.md)|Bellek boyutu boyutlu işaretçiler için ayrılan, boyutlandırılmış işaretçiler ve tek veya çok boyutlu diziler işaretçilere boyutu belirtir.|
|[benzersiz](../windows/unique-cpp.md)|Bir benzersiz işaretçi belirtir.|
|[uuid](../windows/uuid-cpp-attributes.md)|Bir sınıf veya arabirim için benzersiz Kimliğini belirtir.|

### <a name="nonencapsulated-union"></a>Nonencapsulated birleşim

|Öznitelik|Açıklama|
|---------------|-----------------|
|[ms_union](../windows/ms-union.md)|Nonencapsulated birleşimler ağ veri gösterimi hizalamasını denetler.|
|[no_injected_text](../windows/no-injected-text.md)|Derleyici, özellik kullanımı sonucu olarak kod ekleme öğesinden engeller.|

### <a name="struct"></a>struct 

|Öznitelik|Açıklama|
|---------------|-----------------|
|[toplanabilir](../windows/aggregatable.md)|Sınıf toplama desteklediğini belirtir.|
|[toplamlar](../windows/aggregates.md)|Bir denetim için hedef sınıf toplayan gösterir.|
|[appobject](../windows/appobject.md)|Coclass'ı bir tam .exe uygulamayla ilişkili olan ve bu tür kitaplığında coclass'ı özellikleri ve işlevleri genel olarak kullanılabilir olduğunu gösterir bir uygulama nesnesi olarak tanımlar.|
|[coclass](../windows/coclass.md)|Bir ActiveX denetimi oluşturur.|
|[com_interface_entry](../windows/com-interface-entry-cpp.md)|Bir arabirim giriş için bir COM eşlemesi ekler.|
|[control](../windows/control.md)|Kullanıcı tanımlı tür bir denetimi olduğunu belirtir.|
|[Özel](../windows/custom-cpp.md)|Kendi özniteliğinizi tanımlamanızı sağlar.|
|[db_column](../windows/db-column.md)|Belirtilen sütun, satır kümesine bağlar.|
|[db_command](../windows/db-command.md)|OLE DB komut oluşturur.|
|[db_param](../windows/db-param.md)|Belirtilen üye bağımsız değişkenine bir giriş veya çıkış parametresi ile ilişkilendirir ve değişken sınırlandırır.|
|[db_source](../windows/db-source.md)|Bir veri kaynağı için bir bağlantı oluşturur.|
|[db_table](../windows/db-table.md)|Bir OLE DB tablosu açılır.|
|[default](../windows/default-cpp.md)|Özel veya dispinterface coclass'ı içinde tanımlanan varsayılan programlama arabirimi temsil ettiğini gösterir.|
|[defaultvtable](../windows/defaultvtable.md)|Bir denetim için varsayılan vtable arabirimi olarak bir arabirim tanımlar.|
|[event_receiver](../windows/event-receiver.md)|Bir olay alıcısı oluşturur.|
|[event_source](../windows/event-source.md)|Olay kaynağı oluşturur.|
|[export](../windows/export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesine neden olur.|
|[first_is](../windows/first-is.md)|Aktarılacak ilk dizi öğesinin dizinini belirtir.|
|[hidden](../windows/hidden.md)|Öğe var ancak kullanıcıya dayalı tarayıcıda görüntülenmemesi gerektiğini belirtir.|
|[implements_category](../windows/implements-category.md)|Sınıfı için uygulanan bir bileşen kategorilerini belirtir.|
|[last_is](../windows/last-is.md)|Aktarılacak olan son dizi öğenin dizinini belirtir.|
|[length_is](../windows/length-is.md)|Aktarılacak dizi öğelerinin sayısını belirtir.|
|[max_is](../windows/max-is.md)|Geçerli dizi dizini için maksimum değeri atar.|
|[requires_category](../windows/requires-category.md)|Hedef sınıfın gerekli bileşen kategorilerini belirler.|
|[size_is](../windows/size-is.md)|Bellek boyutu boyutlu işaretçiler için ayrılan, boyutlandırılmış işaretçiler ve tek veya çok boyutlu diziler işaretçilere boyutu belirtir.|
|[Kaynak](../windows/source-cpp.md)|Sınıfta, COM nesnesinin kaynak arabirimleri için bağlantı noktalarını belirtir. Özellik veya yöntem üyesi bir nesne veya bir olay kaynağı olan Değişken döndürür gösterir.|
|[İş parçacığı oluşturma](../windows/threading-cpp.md)|Bir COM nesnesi için iş parçacığı modelini belirtir.|
|[benzersiz](../windows/unique-cpp.md)|Bir benzersiz işaretçi belirtir.|
|[uuid](../windows/uuid-cpp-attributes.md)|Bir sınıf veya arabirim için benzersiz Kimliğini belirtir.|
|[Sürüm](../windows/version-cpp.md)|Bir sınıfın birden çok sürümü arasında belirli bir sürümünü tanımlar.|
|[vi_progid](../windows/vi-progid.md)|ProgID sürümden bağımsız biçimi belirtir.|

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıma Göre Öznitelikler](../windows/attributes-by-usage.md)