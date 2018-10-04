---
title: Öznitelikler alfabetik başvurusu | Microsoft Docs
ms.custom: index-page
ms.date: 10/02/2018
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
ms.openlocfilehash: d0b305e928fec58833c4aac3f5625783aa2cb9ef
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48790033"
---
# <a name="attributes-alphabetical-reference"></a>Öznitelikler Alfabetik Başvurusu

Aşağıdaki öznitelikler, Visual C++'da kullanılabilir.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[toplanabilir](aggregatable.md)|Bir denetimi başka bir denetim tarafından toplanabilir gösterir.|
|[toplamlar](aggregates.md)|Bir denetim için hedef sınıf toplayan gösterir.|
|[appobject](appobject.md)|Coclass'ı tam bir EXE uygulamayla ilişkili olan ve bu tür kitaplığında coclass'ı özellikleri ve işlevleri genel olarak kullanılabilir olduğunu gösterir bir uygulama nesnesi olarak tanımlar.|
|[async_uuid](async-uuid.md)|COM arabirimi zaman uyumlu ve zaman uyumsuz sürümlerini tanımlamak için MIDL derleyicisi yönergelerinin sağlandığı UUID belirtir.|
|[attribute](attribute.md)|Özel bir öznitelik oluşturmanıza olanak sağlar.|
|[bindable](bindable.md)|Özelliğin veri bağlamayı desteklediğini belirtir.|
|[call_as](call-as.md)|Uzak bir işleve eşlenmesi nonremotable işlevi sağlar.|
|[Servis talebi](case-cpp.md)|İle kullanılan [switch_type](switch-type.md) UNION özniteliği.|
|[coclass](coclass.md)|COM arabirimi uygulayan bir COM nesnesi oluşturur.|
|[com_interface_entry](com-interface-entry-cpp.md)|Bir arabirim giriş için bir COM eşlemesi ekler.|
|[control](control.md)|Kullanıcı tanımlı tür bir denetimi olduğunu belirtir.|
|[cpp_quote](cpp-quote.md)|Belirtilen dizeyi tırnak karakterleri olmadan oluşturulan üst bilgi dosyasına yayar.|
|[Özel](custom-cpp.md)|Kendi özniteliklerine tanımlamanızı sağlar.|
|[db_accessor](db-accessor.md)|Sütunları satır kümesinde bağlar ve bunların karşılık gelen erişimci eşlenir bağlar.|
|[db_column](db-column.md)|Belirtilen sütun, satır kümesine bağlar.|
|[db_command](db-command.md)|OLE DB komutu yürütür.|
|[db_param](db-param.md)|Belirtilen üye değişkeni, bir giriş veya çıkış parametresi ile ilişkilendirir.|
|[db_source](db-source.md)|Oluşturur ve bir veri kaynağı sağlayıcısı üzerinden bir bağlantı kapsüller.|
|[db_table](db-table.md)|Bir OLE DB tablosu açılır.|
|[default](default-cpp.md)|Özel veya dispinterface coclass'ı içinde tanımlanan varsayılan programlama arabirimi temsil ettiğini gösterir.|
|[defaultbind](defaultbind.md)|En iyi nesneyi temsil eden tek ve bağlanabilir özelliği belirtir.|
|[defaultcollelem](defaultcollelem.md)|Visual Basic kod iyileştirme için kullanılır.|
|[defaultvalue](defaultvalue.md)|Belirtilmiş bir isteğe bağlı parametre için bir varsayılan değer belirtimi sağlar.|
|[defaultvtable](defaultvtable.md)|Bir denetim için varsayılan vtable arabirimi olarak bir arabirim tanımlar.|
|[dispinterface](dispinterface.md)|Bir arabirim gönderme arabirimi olarak .idl dosyasına yerleştirir.|
|[displaybind](displaybind.md)|Kullanıcıya bağlanabilir olarak görüntülenmesi gereken özelliği belirtir.|
|[dual](dual.md)|Bir arabirim çift arabirim .idl dosyasına yerleştirir.|
|[emitidl](emitidl.md)|Tüm sonraki IDL öznitelikleri işlem görüp oluşturulan .idl dosyasında yerleştirilmiş olup olmadığını belirler.|
|[entry](entry.md)|Dışarı aktarılan işlevin ya da sabit bir modülün dll giriş noktası belirleyerek belirtir.|
|[event_receiver](event-receiver.md)|Bir olay alıcısı oluşturur.|
|[event_source](event-source.md)|Olay kaynağı oluşturur.|
|[export](export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesine neden olur.|
|[first_is](first-is.md)|Aktarılacak ilk dizi öğesinin dizinini belirtir.|
|[helpcontext](helpcontext.md)|Kullanıcı Yardım dosyasında bu öğe hakkındaki bilgileri görüntüleme sağlayan bir bağlam kimliği belirtir.|
|[helpfile](helpfile.md)|Bir tür kitaplığı için Yardım dosyasına adını ayarlar.|
|[helpstring](helpstring.md)|Bir .hlp veya .chm dosyasında bir Yardım konusu Kimliğini belirtir.|
|[helpstringdll](helpstringdll.md)|Belge dize arama (yerelleştirme) gerçekleştirmek için kullanılacak DLL'in adını belirtir.|
|[hidden](hidden.md)|Öğe var ancak kullanıcıya dayalı tarayıcıda görüntülenmemesi gerektiğini belirtir.|
|[id](id.md)|DISPID bir üye işlevinin (bir özelliği ya da bir yöntemde, arabirim veya dispinterface) belirtir.|
|[idl_module](idl-module.md)|Bir giriş noktası bir DLL içinde belirtir.|
|[idl_quote](idl-quote.md)|Öznitelikleri kullanmanıza olanak tanır veya Visual C++'ın geçerli sürümünde desteklenmeyen IDL oluşturur.|
|[iid_is](iid-is.md)|Bir arabirim işaretçisi tarafından işaret edilen COM arabirimi Laboratuvardaki belirtir.|
|[immediatebind](immediatebind.md)|Veritabanı veri bağlama nesnesinin bir özelliği yapılan tüm değişikliklerin hemen bildirileceğini belirtir.|
|[Uygulayan](implements-cpp.md)|IDL coclass'ı üyesi olmaya zorlanıp dağıtma arabirimleri belirtir.|
|[implements_category](implements-category.md)|Sınıfı için uygulanan bir bileşen kategorilerini belirtir.|
|[import](import.md)|Ana .idl dosyanızdan başvurmak istediğiniz tanımlarını içeren başka bir .idl, .odl veya üst bilgi dosyasını belirtir.|
|[importidl](importidl.md)|Belirtilen .idl dosyası oluşturulan .idl dosyasına ekler.|
|[importlib](importlib.md)|Zaten başka bir tür kitaplığına oluşturulan tür kitaplığı için kullanılabilir derlenmiştir türleri sağlar.|
|[in](in-cpp.md)|Bir parametrenin çağıran yordamdan çağrılan yordama geçirileceğini gösterir.|
|[İçerir](include-cpp.md)|Oluşturulan .idl dosyasına eklenecek bir veya daha fazla üst bilgi dosyaları belirtir.|
|[includelib](includelib-cpp.md)|Oluşturulan .idl dosyasına eklenecek bir .idl veya .h dosyası neden olur.|
|[last_is](last-is.md)|Aktarılacak olan son dizi öğenin dizinini belirtir.|
|[lcid](lcid.md)|Bir işlev için bir yerel ayar tanımlayıcısı geçirmenize olanak tanır.|
|[length_is](length-is.md)|Aktarılacak dizi öğelerinin sayısını belirtir.|
|[library_block](library-block.md)|.İdl dosyasının kitaplığı bloğu içinde bir yapısı yerleştirir.|
|[licensed](licensed.md)|Geçerli olduğu coclass'ı lisanslanır ve kullanarak örneği oluşturulmalıdır gösterir `IClassFactory2`.|
|[Yerel](local-cpp.md)|MIDL derleyicisi arabirimi başlığı kullanıldığında bir üstbilgi Oluşturucu olarak kullanmanıza olanak tanır. Tek bir işlevde kullanıldığında, hiçbir saptamalar oluşturulan yerel bir yordam belirler.|
|[max_is](max-is.md)|Geçerli dizi dizini için maksimum değeri atar.|
|[Modülü](module-cpp.md)|Kitaplık blok .idl dosyasında tanımlar.|
|[ms_union](ms-union.md)|Nonencapsulated birleşimler ağ veri gösterimi hizalamasını denetler.|
|[no_injected_text](no-injected-text.md)|Derleyici, özellik kullanımı sonucu olarak kod ekleme öğesinden engeller.|
|[nonbrowsable](nonbrowsable.md)|Bir arabirim üyesi bir özellik tarayıcısında görüntülenmemelidir gösterir.|
|[noncreatable](noncreatable.md)|Tek başına oluşturulamaz bir nesneyi tanımlar.|
|[nonextensible](nonextensible.md)|Belirten `IDispatch` uygulaması yalnızca özellikleri içerir ve yöntemleri arabirimi açıklamasında listelenir ve çalışma zamanında ek üyeleriyle genişletilemez.|
|[object](object-cpp.md)|Özel bir arabirim tanımlar; özel öznitelik ile eşanlamlıdır.|
|[odl](odl.md)|Arabirimdeki bir nesne Açıklama Dili (ODL) arabirim tanımlar.|
|[oleautomation](oleautomation.md)|Bir arabirim otomasyon ile uyumlu olduğunu gösterir.|
|[İsteğe bağlı](optional-cpp.md)|Bir üye işlev için isteğe bağlı bir parametre belirtir.|
|[out](out-cpp.md)|Çağrılan yordamdan çağıran yordama (sunucudan istemciye) döndürülen işaretçi parametrelerini tanımlar.|
|[pointer_default](pointer-default.md)|Görünen üst düzey işaretçileri dışındaki tüm işaretçiler için varsayılan işaretçi öznitelik parametre listelerindeki belirtir.|
|[pragma](pragma.md)|Belirtilen dizeyi tırnak karakterleri olmadan oluşturulan .idl dosyasına yayar.|
|[progid](progid.md)|Bir COM nesnesi için ProgID belirtir.|
|[propget](propget.md)|Bir özellik erişimcisi (get) işlevi belirtir.|
|[propput](propput.md)|Bir özellik ayarı işlevi belirtir.|
|[propputref](propputref.md)|Bir değer yerine başvurur bir özellik ayarı işlevi belirtir.|
|[ptr](ptr.md)|Bir işaretçinin tam bir işaretçi olarak belirler.|
|[public](public-cpp-attributes.md)|Bu gelen .idl dosyasında başvurulmuyor olsa bile bir typedef tür kitaplığına geçer sağlar.|
|[Aralığı](range-cpp.md)|Bağımsız değişkenler veya değerleri çalışma zamanında ayarlanır alanlar için izin verilen değer aralığı belirtir.|
|[rdx](rdx.md)|Oluşturur veya bir kayıt defteri anahtarı değiştirir.|
|[readonly](readonly-cpp.md)|Bir değişkene atama yasaklar.|
|[ref](ref-cpp.md)|Bir başvuru işaretçi tanımlar.|
|[registration_script](registration-script.md)|Belirtilen kayıt betiği çalıştırır.|
|[requestedit](requestedit.md)|Özelliğin desteklediğini belirtir `OnRequestEdit` bildirim.|
|[requires_category](requires-category.md)|Sınıfı için gerekli bileşen kategorilerini belirtir.|
|[restricted](restricted.md)|Bir kitaplığı veya modül, arabirim veya dispinterface üyesi rasgele çağrılamaz olduğunu belirtir.|
|[retval](retval.md)|Üyenin dönüş değerini alan parametreyi belirler.|
|[satype](satype.md)|Veri türü belirtir `SAFEARRAY`.|
|[size_is](size-is.md)|Bellek boyutu boyutlu işaretçiler için ayrılan, boyutlandırılmış işaretçiler ve tek veya çok boyutlu diziler işaretçilere boyutu belirtir.|
|[Kaynak](source-cpp.md)|Bir sınıf, özelliği veya yöntemi üyesi bir olay kaynağı olduğunu gösterir.|
|[string](string-cpp.md)|Bildiren tek boyutlu **char**, **wchar_t**, `byte`, ya da eşdeğer bir dizi veya işaretçiyi gibi bir dizi gerekir kabul bir dize.|
|[support_error_info](support-error-info.md)|Hata raporlama için hedef nesne destekler.|
|[switch_is](switch-is.md)|İfade veya birleşim üyesi seçer birleşim discriminant davranan tanımlayıcısını belirtir.|
|[switch_type](switch-type.md)|Birleşim discriminant kullanılan değişkenin türünü tanımlar.|
|[synchronize](synchronize.md)|Bir yönteme erişimi eşitler.|
|[İş parçacığı oluşturma](threading-cpp.md)|Bir COM nesnesi için iş parçacığı modelini belirtir.|
|[transmit_as](transmit-as.md)|Hangi istemci ve sunucu uygulamaları işlemek, sunulan bir türü, iletilen türüyle ilişkilendirmek için derleyicinin sağlar.|
|[uidefault](uidefault.md)|Tür bilgileri üyesi kullanıcı arabiriminde görüntülemek için varsayılan üye olduğunu gösterir.|
|[benzersiz](unique-cpp.md)|Bir benzersiz işaretçi belirtir.|
|[usesgetlasterror](usesgetlasterror.md)|Bu işlev çağrılırken bir hata ise çağıranın sonra çağırabilirsiniz çağıran söyler `GetLastError` hata kodu alınamıyor.|
|[uuid](uuid-cpp-attributes.md)|Bir sınıf veya arabirim için benzersiz Kimliğini belirtir.|
|[v1_enum](v1-enum.md)|Belirtilen listeden seçimli türü 16-bit varsayılan yerine bir 32-bit varlık olarak iletilmesi yönlendirir.|
|[vararg](vararg.md)|İşlev, değişken sayıda bağımsız değişken yapmanızı belirtir.|
|[Sürüm](version-cpp.md)|Belirli bir sürüm arasında bir arabirim veya sınıf birden çok sürümünü tanımlar.|
|[vi_progid](vi-progid.md)|ProgID sürümden bağımsız biçimi belirtir.|
|[wire_marshal](wire-marshal.md)|Bir uygulamaya özel veri türü yerine iletim için kullanılacak olan veri türünü belirtir.|

## <a name="see-also"></a>Ayrıca Bkz.

[COM ve .NET için C++ öznitelikleri](cpp-attributes-com-net.md)<br/>
[Gruplara Göre Öznitelikler](attributes-by-group.md)<br/>
[Kullanıma Göre Öznitelikler](attributes-by-usage.md)