---
title: TypeDef, Enum, Union ve Struct öznitelikleri (C++ COM) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: 89e1511df2aeabe7cbd63549a1dca6e53944fbe2
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789892"
---
# <a name="typedef-enum-union-and-struct-attributes"></a>Typedef, Enum, Union ve Struct Öznitelikleri

Aşağıdaki öznitelikler uygulamak [typedef](../../cpp/aliases-and-typedefs-cpp.md), [yapı](../../cpp/struct-cpp.md), ve [enum](../../cpp/enumerations-cpp.md) C++ anahtar sözcükleri.

### <a name="typedef"></a>typedef

|Öznitelik|Açıklama|
|---------------|-----------------|
|[Servis talebi](case-cpp.md)|İle kullanılan [switch_type](switch-type.md) özniteliğini bir **birleşim**.|
|[Özel](custom-cpp.md)|Kendi özniteliğinizi tanımlamanızı sağlar.|
|[export](export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesine neden olur.|
|[first_is](first-is.md)|Aktarılacak ilk dizi öğesinin dizinini belirtir.|
|[helpcontext](helpcontext.md)|Kullanıcı Yardım dosyasında bu öğe hakkındaki bilgileri görüntüleme sağlayan bir bağlam kimliği belirtir.|
|[helpfile](helpfile.md)|Bir tür kitaplığı için Yardım dosyasına adını ayarlar.|
|[helpstring](helpstring.md)|Uygulandığı öğe açıklamak için kullanılan bir karakter dizesi belirtir.|
|[library_block](library-block.md)|.İdl dosyasının kitaplığı bloğu içinde bir yapısı yerleştirir.|
|[ptr](ptr.md)|Bir işaretçinin tam bir işaretçi olarak belirler.|
|[public](public-cpp-attributes.md)|Bu gelen .idl dosyasında başvurulmuyor olsa bile bir typedef tür kitaplığına geçer sağlar.|
|[ref](ref-cpp.md)|Bir başvuru işaretçi tanımlar.|
|[switch_is](switch-is.md)|İfade veya birleşim üyesi seçer birleşim discriminant davranan tanımlayıcısını belirtir.|
|[switch_type](switch-type.md)|Birleşim discriminant kullanılan değişkenin türünü tanımlar.|
|[benzersiz](unique-cpp.md)|Bir benzersiz işaretçi belirtir.|
|[wire_marshal](wire-marshal.md)|Bir uygulamaya özel veri türü yerine iletim için kullanılacak olan veri türünü belirtir.|

### <a name="enum"></a>enum

|Öznitelik|Açıklama|
|---------------|-----------------|
|[Özel](custom-cpp.md)|Kendi özniteliğinizi tanımlamanızı sağlar.|
|[export](export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesine neden olur.|
|[uuid](uuid-cpp-attributes.md)|Bir sınıf veya arabirim için benzersiz Kimliğini belirtir.|
|[v1_enum](v1-enum.md)|Belirtilen listeden seçimli türü 16-bit varsayılan yerine bir 32-bit varlık olarak iletilmesi yönlendirir.|

### <a name="union"></a>birleşim

|Öznitelik|Açıklama|
|---------------|-----------------|
|[Özel](custom-cpp.md)|Kendi özniteliğinizi tanımlamanızı sağlar.|
|[export](export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesine neden olur.|
|[first_is](first-is.md)|Aktarılacak ilk dizi öğesinin dizinini belirtir.|
|[last_is](last-is.md)|Aktarılacak olan son dizi öğenin dizinini belirtir.|
|[length_is](length-is.md)|Aktarılacak dizi öğelerinin sayısını belirtir.|
|[max_is](max-is.md)|Geçerli dizi dizini için maksimum değeri atar.|
|[size_is](size-is.md)|Bellek boyutu boyutlu işaretçiler için ayrılan, boyutlandırılmış işaretçiler ve tek veya çok boyutlu diziler işaretçilere boyutu belirtir.|
|[benzersiz](unique-cpp.md)|Bir benzersiz işaretçi belirtir.|
|[uuid](uuid-cpp-attributes.md)|Bir sınıf veya arabirim için benzersiz Kimliğini belirtir.|

### <a name="nonencapsulated-union"></a>Nonencapsulated birleşim

|Öznitelik|Açıklama|
|---------------|-----------------|
|[ms_union](ms-union.md)|Nonencapsulated birleşimler ağ veri gösterimi hizalamasını denetler.|
|[no_injected_text](no-injected-text.md)|Derleyici, özellik kullanımı sonucu olarak kod ekleme öğesinden engeller.|

### <a name="struct"></a>struct 

|Öznitelik|Açıklama|
|---------------|-----------------|
|[toplanabilir](aggregatable.md)|Sınıf toplama desteklediğini belirtir.|
|[toplamlar](aggregates.md)|Bir denetim için hedef sınıf toplayan gösterir.|
|[appobject](appobject.md)|Coclass'ı bir tam .exe uygulamayla ilişkili olan ve bu tür kitaplığında coclass'ı özellikleri ve işlevleri genel olarak kullanılabilir olduğunu gösterir bir uygulama nesnesi olarak tanımlar.|
|[coclass](coclass.md)|Bir ActiveX denetimi oluşturur.|
|[com_interface_entry](com-interface-entry-cpp.md)|Bir arabirim giriş için bir COM eşlemesi ekler.|
|[control](control.md)|Kullanıcı tanımlı tür bir denetimi olduğunu belirtir.|
|[Özel](custom-cpp.md)|Kendi özniteliğinizi tanımlamanızı sağlar.|
|[db_column](db-column.md)|Belirtilen sütun, satır kümesine bağlar.|
|[db_command](db-command.md)|OLE DB komut oluşturur.|
|[db_param](db-param.md)|Belirtilen üye bağımsız değişkenine bir giriş veya çıkış parametresi ile ilişkilendirir ve değişken sınırlandırır.|
|[db_source](db-source.md)|Bir veri kaynağı için bir bağlantı oluşturur.|
|[db_table](db-table.md)|Bir OLE DB tablosu açılır.|
|[default](default-cpp.md)|Özel veya dispinterface coclass'ı içinde tanımlanan varsayılan programlama arabirimi temsil ettiğini gösterir.|
|[defaultvtable](defaultvtable.md)|Bir denetim için varsayılan vtable arabirimi olarak bir arabirim tanımlar.|
|[event_receiver](event-receiver.md)|Bir olay alıcısı oluşturur.|
|[event_source](event-source.md)|Olay kaynağı oluşturur.|
|[export](export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesine neden olur.|
|[first_is](first-is.md)|Aktarılacak ilk dizi öğesinin dizinini belirtir.|
|[hidden](hidden.md)|Öğe var ancak kullanıcıya dayalı tarayıcıda görüntülenmemesi gerektiğini belirtir.|
|[implements_category](implements-category.md)|Sınıfı için uygulanan bir bileşen kategorilerini belirtir.|
|[last_is](last-is.md)|Aktarılacak olan son dizi öğenin dizinini belirtir.|
|[length_is](length-is.md)|Aktarılacak dizi öğelerinin sayısını belirtir.|
|[max_is](max-is.md)|Geçerli dizi dizini için maksimum değeri atar.|
|[requires_category](requires-category.md)|Hedef sınıfın gerekli bileşen kategorilerini belirler.|
|[size_is](size-is.md)|Bellek boyutu boyutlu işaretçiler için ayrılan, boyutlandırılmış işaretçiler ve tek veya çok boyutlu diziler işaretçilere boyutu belirtir.|
|[Kaynak](source-cpp.md)|Sınıfta, COM nesnesinin kaynak arabirimleri için bağlantı noktalarını belirtir. Özellik veya yöntem üyesi bir nesne veya bir olay kaynağı olan Değişken döndürür gösterir.|
|[İş parçacığı oluşturma](threading-cpp.md)|Bir COM nesnesi için iş parçacığı modelini belirtir.|
|[benzersiz](unique-cpp.md)|Bir benzersiz işaretçi belirtir.|
|[uuid](uuid-cpp-attributes.md)|Bir sınıf veya arabirim için benzersiz Kimliğini belirtir.|
|[Sürüm](version-cpp.md)|Bir sınıfın birden çok sürümü arasında belirli bir sürümünü tanımlar.|
|[vi_progid](vi-progid.md)|ProgID sürümden bağımsız biçimi belirtir.|

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıma Göre Öznitelikler](attributes-by-usage.md)