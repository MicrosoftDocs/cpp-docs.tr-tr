---
title: Öznitelikler alfabetik başvurusu | Microsoft Docs
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.attributes
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI]
ms.assetid: fb2216ef-9fbd-44f4-afed-732aa99450e2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e2353b952964ffe6b8078f688b4ac8e129d891d7
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44314696"
---
# <a name="attributes-alphabetical-reference"></a>Öznitelikler Alfabetik Başvurusu

Aşağıdaki öznitelikler, Visual C++'da kullanılabilir.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[toplanabilir](../windows/aggregatable.md)|Bir denetimi başka bir denetim tarafından toplanabilir gösterir.|
|[toplamlar](../windows/aggregates.md)|Bir denetim için hedef sınıf toplayan gösterir.|
|[appobject](../windows/appobject.md)|Coclass'ı tam bir EXE uygulamayla ilişkili olan ve bu tür kitaplığında coclass'ı özellikleri ve işlevleri genel olarak kullanılabilir olduğunu gösterir bir uygulama nesnesi olarak tanımlar.|
|[async_uuid](../windows/async-uuid.md)|COM arabirimi zaman uyumlu ve zaman uyumsuz sürümlerini tanımlamak için MIDL derleyicisi yönergelerinin sağlandığı UUID belirtir.|
|[attribute](../windows/attribute.md)|Özel bir öznitelik oluşturmanıza olanak sağlar.|
|[bindable](../windows/bindable.md)|Özelliğin veri bağlamayı desteklediğini belirtir.|
|[call_as](../windows/call-as.md)|Uzak bir işleve eşlenmesi nonremotable işlevi sağlar.|
|[Servis talebi](../windows/case-cpp.md)|İle kullanılan [switch_type](../windows/switch-type.md) UNION özniteliği.|
|[coclass](../windows/coclass.md)|COM arabirimi uygulayan bir COM nesnesi oluşturur.|
|[com_interface_entry](../windows/com-interface-entry-cpp.md)|Bir arabirim giriş için bir COM eşlemesi ekler.|
|[control](../windows/control.md)|Kullanıcı tanımlı tür bir denetimi olduğunu belirtir.|
|[cpp_quote](../windows/cpp-quote.md)|Belirtilen dizeyi tırnak karakterleri olmadan oluşturulan üst bilgi dosyasına yayar.|
|[Özel](../windows/custom-cpp.md)|Kendi özniteliklerine tanımlamanızı sağlar.|
|[db_accessor](../windows/db-accessor.md)|Sütunları satır kümesinde bağlar ve bunların karşılık gelen erişimci eşlenir bağlar.|
|[db_column](../windows/db-column.md)|Belirtilen sütun, satır kümesine bağlar.|
|[db_command](../windows/db-command.md)|OLE DB komutu yürütür.|
|[db_param](../windows/db-param.md)|Belirtilen üye değişkeni, bir giriş veya çıkış parametresi ile ilişkilendirir.|
|[db_source](../windows/db-source.md)|Oluşturur ve bir veri kaynağı sağlayıcısı üzerinden bir bağlantı kapsüller.|
|[db_table](../windows/db-table.md)|Bir OLE DB tablosu açılır.|
|[default](../windows/default-cpp.md)|Özel veya dispinterface coclass'ı içinde tanımlanan varsayılan programlama arabirimi temsil ettiğini gösterir.|
|[defaultbind](../windows/defaultbind.md)|En iyi nesneyi temsil eden tek ve bağlanabilir özelliği belirtir.|
|[defaultcollelem](../windows/defaultcollelem.md)|Visual Basic kod iyileştirme için kullanılır.|
|[defaultvalue](../windows/defaultvalue.md)|Belirtilmiş bir isteğe bağlı parametre için bir varsayılan değer belirtimi sağlar.|
|[defaultvtable](../windows/defaultvtable.md)|Bir denetim için varsayılan vtable arabirimi olarak bir arabirim tanımlar.|
|[dispinterface](../windows/dispinterface.md)|Bir arabirim gönderme arabirimi olarak .idl dosyasına yerleştirir.|
|[displaybind](../windows/displaybind.md)|Kullanıcıya bağlanabilir olarak görüntülenmesi gereken özelliği belirtir.|
|[dual](../windows/dual.md)|Bir arabirim çift arabirim .idl dosyasına yerleştirir.|
|[emitidl](../windows/emitidl.md)|Tüm sonraki IDL öznitelikleri işlem görüp oluşturulan .idl dosyasında yerleştirilmiş olup olmadığını belirler.|
|[entry](../windows/entry.md)|Dışarı aktarılan işlevin ya da sabit bir modülün dll giriş noktası belirleyerek belirtir.|
|[event_receiver](../windows/event-receiver.md)|Bir olay alıcısı oluşturur.|
|[event_source](../windows/event-source.md)|Olay kaynağı oluşturur.|
|[export](../windows/export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesine neden olur.|
|[first_is](../windows/first-is.md)|Aktarılacak ilk dizi öğesinin dizinini belirtir.|
|[helpcontext](../windows/helpcontext.md)|Kullanıcı Yardım dosyasında bu öğe hakkındaki bilgileri görüntüleme sağlayan bir bağlam kimliği belirtir.|
|[helpfile](../windows/helpfile.md)|Bir tür kitaplığı için Yardım dosyasına adını ayarlar.|
|[helpstring](../windows/helpstring.md)|Bir .hlp veya .chm dosyasında bir Yardım konusu Kimliğini belirtir.|
|[helpstringdll](../windows/helpstringdll.md)|Belge dize arama (yerelleştirme) gerçekleştirmek için kullanılacak DLL'in adını belirtir.|
|[hidden](../windows/hidden.md)|Öğe var ancak kullanıcıya dayalı tarayıcıda görüntülenmemesi gerektiğini belirtir.|
|[id](../windows/id.md)|DISPID bir üye işlevinin (bir özelliği ya da bir yöntemde, arabirim veya dispinterface) belirtir.|
|[idl_module](../windows/idl-module.md)|Bir giriş noktası bir DLL içinde belirtir.|
|[idl_quote](../windows/idl-quote.md)|Öznitelikleri kullanmanıza olanak tanır veya Visual C++'ın geçerli sürümünde desteklenmeyen IDL oluşturur.|
|[iid_is](../windows/iid-is.md)|Bir arabirim işaretçisi tarafından işaret edilen COM arabirimi Laboratuvardaki belirtir.|
|[immediatebind](../windows/immediatebind.md)|Veritabanı veri bağlama nesnesinin bir özelliği yapılan tüm değişikliklerin hemen bildirileceğini belirtir.|
|[Uygulayan](../windows/implements-cpp.md)|IDL coclass'ı üyesi olmaya zorlanıp dağıtma arabirimleri belirtir.|
|[implements_category](../windows/implements-category.md)|Sınıfı için uygulanan bir bileşen kategorilerini belirtir.|
|[import](../windows/import.md)|Ana .idl dosyanızdan başvurmak istediğiniz tanımlarını içeren başka bir .idl, .odl veya üst bilgi dosyasını belirtir.|
|[importidl](../windows/importidl.md)|Belirtilen .idl dosyası oluşturulan .idl dosyasına ekler.|
|[importlib](../windows/importlib.md)|Zaten başka bir tür kitaplığına oluşturulan tür kitaplığı için kullanılabilir derlenmiştir türleri sağlar.|
|[in](../windows/in-cpp.md)|Bir parametrenin çağıran yordamdan çağrılan yordama geçirileceğini gösterir.|
|[İçerir](../windows/include-cpp.md)|Oluşturulan .idl dosyasına eklenecek bir veya daha fazla üst bilgi dosyaları belirtir.|
|[includelib](../windows/includelib-cpp.md)|Oluşturulan .idl dosyasına eklenecek bir .idl veya .h dosyası neden olur.|
|[last_is](../windows/last-is.md)|Aktarılacak olan son dizi öğenin dizinini belirtir.|
|[lcid](../windows/lcid.md)|Bir işlev için bir yerel ayar tanımlayıcısı geçirmenize olanak tanır.|
|[length_is](../windows/length-is.md)|Aktarılacak dizi öğelerinin sayısını belirtir.|
|[library_block](../windows/library-block.md)|.İdl dosyasının kitaplığı bloğu içinde bir yapısı yerleştirir.|
|[licensed](../windows/licensed.md)|Geçerli olduğu coclass'ı lisanslanır ve kullanarak örneği oluşturulmalıdır gösterir `IClassFactory2`.|
|[Yerel](../windows/local-cpp.md)|MIDL derleyicisi arabirimi başlığı kullanıldığında bir üstbilgi Oluşturucu olarak kullanmanıza olanak tanır. Tek bir işlevde kullanıldığında, hiçbir saptamalar oluşturulan yerel bir yordam belirler.|
|[max_is](../windows/max-is.md)|Geçerli dizi dizini için maksimum değeri atar.|
|[Modülü](../windows/module-cpp.md)|Kitaplık blok .idl dosyasında tanımlar.|
|[ms_union](../windows/ms-union.md)|Nonencapsulated birleşimler ağ veri gösterimi hizalamasını denetler.|
|[no_injected_text](../windows/no-injected-text.md)|Derleyici, özellik kullanımı sonucu olarak kod ekleme öğesinden engeller.|
|[nonbrowsable](../windows/nonbrowsable.md)|Bir arabirim üyesi bir özellik tarayıcısında görüntülenmemelidir gösterir.|
|[noncreatable](../windows/noncreatable.md)|Tek başına oluşturulamaz bir nesneyi tanımlar.|
|[nonextensible](../windows/nonextensible.md)|Belirten `IDispatch` uygulaması yalnızca özellikleri içerir ve yöntemleri arabirimi açıklamasında listelenir ve çalışma zamanında ek üyeleriyle genişletilemez.|
|[object](../windows/object-cpp.md)|Özel bir arabirim tanımlar; özel öznitelik ile eşanlamlıdır.|
|[odl](../windows/odl.md)|Arabirimdeki bir nesne Açıklama Dili (ODL) arabirim tanımlar.|
|[oleautomation](../windows/oleautomation.md)|Bir arabirim otomasyon ile uyumlu olduğunu gösterir.|
|[İsteğe bağlı](../windows/optional-cpp.md)|Bir üye işlev için isteğe bağlı bir parametre belirtir.|
|[out](../windows/out-cpp.md)|Çağrılan yordamdan çağıran yordama (sunucudan istemciye) döndürülen işaretçi parametrelerini tanımlar.|
|[pointer_default](../windows/pointer-default.md)|Görünen üst düzey işaretçileri dışındaki tüm işaretçiler için varsayılan işaretçi öznitelik parametre listelerindeki belirtir.|
|[pragma](../windows/pragma.md)|Belirtilen dizeyi tırnak karakterleri olmadan oluşturulan .idl dosyasına yayar.|
|[progid](../windows/progid.md)|Bir COM nesnesi için ProgID belirtir.|
|[propget](../windows/propget.md)|Bir özellik erişimcisi (get) işlevi belirtir.|
|[propput](../windows/propput.md)|Bir özellik ayarı işlevi belirtir.|
|[propputref](../windows/propputref.md)|Bir değer yerine başvurur bir özellik ayarı işlevi belirtir.|
|[ptr](../windows/ptr.md)|Bir işaretçinin tam bir işaretçi olarak belirler.|
|[public](../windows/public-cpp-attributes.md)|Bu gelen .idl dosyasında başvurulmuyor olsa bile bir typedef tür kitaplığına geçer sağlar.|
|[Aralığı](../windows/range-cpp.md)|Bağımsız değişkenler veya değerleri çalışma zamanında ayarlanır alanlar için izin verilen değer aralığı belirtir.|
|[rdx](../windows/rdx.md)|Oluşturur veya bir kayıt defteri anahtarı değiştirir.|
|[readonly](../windows/readonly-cpp.md)|Bir değişkene atama yasaklar.|
|[ref](../windows/ref-cpp.md)|Bir başvuru işaretçi tanımlar.|
|[registration_script](../windows/registration-script.md)|Belirtilen kayıt betiği çalıştırır.|
|[requestedit](../windows/requestedit.md)|Özelliğin desteklediğini belirtir `OnRequestEdit` bildirim.|
|[requires_category](../windows/requires-category.md)|Sınıfı için gerekli bileşen kategorilerini belirtir.|
|[restricted](../windows/restricted.md)|Bir kitaplığı veya modül, arabirim veya dispinterface üyesi rasgele çağrılamaz olduğunu belirtir.|
|[retval](../windows/retval.md)|Üyenin dönüş değerini alan parametreyi belirler.|
|[satype](../windows/satype.md)|Veri türü belirtir `SAFEARRAY`.|
|[size_is](../windows/size-is.md)|Bellek boyutu boyutlu işaretçiler için ayrılan, boyutlandırılmış işaretçiler ve tek veya çok boyutlu diziler işaretçilere boyutu belirtir.|
|[Kaynak](../windows/source-cpp.md)|Bir sınıf, özelliği veya yöntemi üyesi bir olay kaynağı olduğunu gösterir.|
|[string](../windows/string-cpp.md)|Bildiren tek boyutlu **char**, **wchar_t**, `byte`, ya da eşdeğer bir dizi veya işaretçiyi gibi bir dizi gerekir kabul bir dize.|
|[support_error_info](../windows/support-error-info.md)|Hata raporlama için hedef nesne destekler.|
|[switch_is](../windows/switch-is.md)|İfade veya birleşim üyesi seçer birleşim discriminant davranan tanımlayıcısını belirtir.|
|[switch_type](../windows/switch-type.md)|Birleşim discriminant kullanılan değişkenin türünü tanımlar.|
|[synchronize](../windows/synchronize.md)|Bir yönteme erişimi eşitler.|
|[İş parçacığı oluşturma](../windows/threading-cpp.md)|Bir COM nesnesi için iş parçacığı modelini belirtir.|
|[transmit_as](../windows/transmit-as.md)|Hangi istemci ve sunucu uygulamaları işlemek, sunulan bir türü, iletilen türüyle ilişkilendirmek için derleyicinin sağlar.|
|[uidefault](../windows/uidefault.md)|Tür bilgileri üyesi kullanıcı arabiriminde görüntülemek için varsayılan üye olduğunu gösterir.|
|[benzersiz](../windows/unique-cpp.md)|Bir benzersiz işaretçi belirtir.|
|[usesgetlasterror](../windows/usesgetlasterror.md)|Bu işlev çağrılırken bir hata ise çağıranın sonra çağırabilirsiniz çağıran söyler `GetLastError` hata kodu alınamıyor.|
|[uuid](../windows/uuid-cpp-attributes.md)|Bir sınıf veya arabirim için benzersiz Kimliğini belirtir.|
|[v1_enum](../windows/v1-enum.md)|Belirtilen listeden seçimli türü 16-bit varsayılan yerine bir 32-bit varlık olarak iletilmesi yönlendirir.|
|[vararg](../windows/vararg.md)|İşlev, değişken sayıda bağımsız değişken yapmanızı belirtir.|
|[Sürüm](../windows/version-cpp.md)|Belirli bir sürüm arasında bir arabirim veya sınıf birden çok sürümünü tanımlar.|
|[vi_progid](../windows/vi-progid.md)|ProgID sürümden bağımsız biçimi belirtir.|
|[wire_marshal](../windows/wire-marshal.md)|Bir uygulamaya özel veri türü yerine iletim için kullanılacak olan veri türünü belirtir.|

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Öznitelikleri Başvurusu](../windows/cpp-attributes-reference.md)  
[Kavramları](../windows/attributed-programming-concepts.md)  
[Gruplara Göre Öznitelikler](../windows/attributes-by-group.md)  
[Kullanıma Göre Öznitelikler](../windows/attributes-by-usage.md)