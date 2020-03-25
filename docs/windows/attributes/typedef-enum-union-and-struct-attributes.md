---
title: TypeDef, Enum, Union ve struct öznitelikleri (C++ com)
ms.date: 10/02/2018
helpviewer_keywords:
- union attributes
- attributes [C++/CLI], reference topics
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
ms.openlocfilehash: fdc380cdc207361a145862f87d809a4bcea01c27
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214480"
---
# <a name="typedef-enum-union-and-struct-attributes"></a>Typedef, Enum, Union ve Struct Öznitelikleri

Aşağıdaki öznitelikler [typedef](../../cpp/aliases-and-typedefs-cpp.md), [struct](../../cpp/struct-cpp.md)ve [enum](../../cpp/enumerations-cpp.md) C++ anahtar sözcükleri için geçerlidir.

### <a name="typedef"></a>typedef

|Öznitelik|Açıklama|
|---------------|-----------------|
|[case](case-cpp.md)|Bir **birleşimdeki** [switch_type](switch-type.md) özniteliğiyle birlikte kullanılır.|
|[custom](custom-cpp.md)|Kendi öznitelemenizi tanımlamanızı sağlar.|
|[export](export.md)|Veri yapısının. IDL dosyasına yerleştirilmesine neden olur.|
|[first_is](first-is.md)|İletilmek üzere ilk dizi öğesinin dizinini belirtir.|
|[helpcontext](helpcontext.md)|Kullanıcının Yardım dosyasında bu öğeyle ilgili bilgileri görüntülemesine imkan tanıyan bir bağlam KIMLIĞI belirtir.|
|[helpfile](helpfile.md)|Bir tür kitaplığı için yardım dosyasının adını ayarlar.|
|[helpstring](helpstring.md)|Uygulandığı öğeyi anlatmak için kullanılan bir karakter dizesini belirtir.|
|[library_block](library-block.md)|. IDL dosyasının Kitaplık bloğunun içine bir yapı koyar.|
|[ptr](ptr.md)|Bir işaretçiyi tam bir işaretçi olarak belirler.|
|[public](public-cpp-attributes.md)|Bir typedef 'in,. IDL dosyası içinden başvurulmamış olsa bile tür kitaplığına gitmesini sağlar.|
|[ref](ref-cpp.md)|Başvuru işaretçisini tanımlar.|
|[switch_is](switch-is.md)|Birleşim üyesini seçen birleşim ayırt edici olarak davranan ifade veya tanımlayıcıyı belirtir.|
|[switch_type](switch-type.md)|UNION ayrımınant olarak kullanılan değişkenin türünü tanımlar.|
|[unique](unique-cpp.md)|Benzersiz bir işaretçi belirtir.|
|[wire_marshal](wire-marshal.md)|Uygulamaya özgü veri türü yerine iletim için kullanılacak bir veri türü belirtir.|

### <a name="enum"></a>enum

|Öznitelik|Açıklama|
|---------------|-----------------|
|[custom](custom-cpp.md)|Kendi öznitelemenizi tanımlamanızı sağlar.|
|[export](export.md)|Veri yapısının. IDL dosyasına yerleştirilmesine neden olur.|
|[uuid](uuid-cpp-attributes.md)|Bir sınıf veya arabirim için benzersiz KIMLIĞI belirtir.|
|[v1_enum](v1-enum.md)|Belirtilen numaralandırılmış türün 16 bit varsayılan yerine 32 bitlik bir varlık olarak aktarılacağını yönlendirir.|

### <a name="union"></a>birleşim

|Öznitelik|Açıklama|
|---------------|-----------------|
|[custom](custom-cpp.md)|Kendi öznitelemenizi tanımlamanızı sağlar.|
|[export](export.md)|Veri yapısının. IDL dosyasına yerleştirilmesine neden olur.|
|[first_is](first-is.md)|İletilmek üzere ilk dizi öğesinin dizinini belirtir.|
|[last_is](last-is.md)|İletilmek üzere son dizi öğesinin dizinini belirtir.|
|[length_is](length-is.md)|Aktarılacak dizi öğelerinin sayısını belirtir.|
|[max_is](max-is.md)|Geçerli bir dizi dizininin en büyük değerini belirtir.|
|[size_is](size-is.md)|Boyutlandırılmış işaretçiler için ayrılan bellek boyutunu, boyutlandırılmış işaretçilere boyutlandırılmış boyutları ve tek veya çok boyutlu dizileri belirtir.|
|[unique](unique-cpp.md)|Benzersiz bir işaretçi belirtir.|
|[uuid](uuid-cpp-attributes.md)|Bir sınıf veya arabirim için benzersiz KIMLIĞI belirtir.|

### <a name="nonencapsulated-union"></a>Kapsüllenmiş olmayan birleşim

|Öznitelik|Açıklama|
|---------------|-----------------|
|[ms_union](ms-union.md)|Kapsüllenolmayan birleşimlerin ağ verisi gösterimi hizalamasını denetler.|
|[no_injected_text](no-injected-text.md)|Öznitelik kullanımı sonucu olarak derleyicinin ekleme kodundan yapılmasını engeller.|

### <a name="struct"></a>struct

|Öznitelik|Açıklama|
|---------------|-----------------|
|[toplanabilir](aggregatable.md)|Sınıfın toplamayı desteklediğini gösterir.|
|[toplamlar](aggregates.md)|Bir denetimin hedef sınıfı topladığını gösterir.|
|[appobject](appobject.md)|Bir tam. exe uygulamasıyla ilişkili bir uygulama nesnesi olarak coclass 'ı tanımlar ve coclass 'ın işlevlerinin ve özelliklerinin bu tür kitaplığında genel olarak kullanılabildiğini gösterir.|
|[coclass](coclass.md)|Bir ActiveX denetimi oluşturur.|
|[com_interface_entry](com-interface-entry-cpp.md)|COM eşlemesine bir arabirim girişi ekler.|
|[control](control.md)|Kullanıcı tanımlı türün bir denetim olduğunu belirtir.|
|[custom](custom-cpp.md)|Kendi öznitelemenizi tanımlamanızı sağlar.|
|[db_column](db-column.md)|Belirtilen bir sütunu satır kümesine bağlar.|
|[db_command](db-command.md)|Bir OLE DB komutu oluşturur.|
|[db_param](db-param.md)|Belirtilen üye değişkenini bir giriş veya çıkış parametresiyle ilişkilendirir ve değişkeni ayırır.|
|[db_source](db-source.md)|Bir veri kaynağına bir bağlantı oluşturur.|
|[db_table](db-table.md)|Bir OLE DB tablosu açar.|
|[default](default-cpp.md)|Bir coclass içinde tanımlanan özel veya dispınterface 'in varsayılan programlama arabirimini temsil ettiğini belirtir.|
|[defaultvtable](defaultvtable.md)|Bir denetim için varsayılan vtable arabirimi olarak bir arabirimi tanımlar.|
|[event_receiver](event-receiver.md)|Bir olay alıcısı oluşturur.|
|[event_source](event-source.md)|Bir olay kaynağı oluşturur.|
|[export](export.md)|Veri yapısının. IDL dosyasına yerleştirilmesine neden olur.|
|[first_is](first-is.md)|İletilmek üzere ilk dizi öğesinin dizinini belirtir.|
|[hidden](hidden.md)|Öğenin var olduğunu ancak kullanıcıya dayalı bir tarayıcıda gösterilmemelidir.|
|[implements_category](implements-category.md)|Sınıf için uygulanan bileşen kategorilerini belirtir.|
|[last_is](last-is.md)|İletilmek üzere son dizi öğesinin dizinini belirtir.|
|[length_is](length-is.md)|Aktarılacak dizi öğelerinin sayısını belirtir.|
|[max_is](max-is.md)|Geçerli bir dizi dizininin en büyük değerini belirtir.|
|[requires_category](requires-category.md)|Hedef sınıfın gerekli bileşen kategorilerini belirtir.|
|[size_is](size-is.md)|Boyutlandırılmış işaretçiler için ayrılan bellek boyutunu, boyutlandırılmış işaretçilere boyutlandırılmış boyutları ve tek veya çok boyutlu dizileri belirtir.|
|[source](source-cpp.md)|Bir sınıfında, bağlantı noktaları için COM nesnesinin kaynak arabirimlerini belirtir. Bir özellik veya yöntemde, üyenin bir olay kaynağı olan bir nesne veya DEĞIŞKEN döndürdüğünü gösterir.|
|[threading](threading-cpp.md)|COM nesnesi için iş parçacığı modelini belirtir.|
|[unique](unique-cpp.md)|Benzersiz bir işaretçi belirtir.|
|[uuid](uuid-cpp-attributes.md)|Bir sınıf veya arabirim için benzersiz KIMLIĞI belirtir.|
|[version](version-cpp.md)|Bir sınıfın birden çok sürümü arasında belirli bir sürümü tanımlar.|
|[vi_progid](vi-progid.md)|ProgID 'nin sürümden bağımsız bir biçimini belirtir.|

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıma Göre Öznitelikler](attributes-by-usage.md)
