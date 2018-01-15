---
title: "IDL öznitelikleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- attributes [C++], reference topics
- IDL attributes
- .idl files, attributes
- IDL files, attributes
- .idl files
ms.assetid: 04c596f4-c97b-4952-8053-316678b1d0b6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 447c4369d7a80348dfb6c5eee54c49d76c1e8a4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="idl-attributes"></a>IDL Öznitelikleri
Geleneksel olarak, bir .idl dosya bakımı için zorunlu kılıyordu:  
  
-   Yapı ve üzerinde değişiklik yapabilmek için bir .idl dosyasının söz dizimi ile ilgili bilgi sahibi olmanız.  
  
-   .İdl dosyanın bazı yönlerini değiştirmenize izin verir bir sihirbaz üzerinde kullanır.  
  
 Şimdi, .idl dosyasını Visual C++ IDL öznitelikleri kullanarak bir kaynak kodu dosyasının içinden değiştirebilirsiniz. Çoğu durumda, Visual C++ IDL öznitelikleri MIDL öznitelikleri aynı ada sahip. Visual C++ IDL özniteliği ve MIDL öznitelik adı olduğunuzda aynı kaynak kodu dosyanızda Visual C++ öznitelik koyma onun namesake MIDL özniteliğini içeren bir .idl dosyasında sonuçlanır anlamına gelir. Ancak, bir Visual C++ IDL özniteliği MIDL özniteliği tüm işlevselliğini sağlamayabilir.  
  
 İle kullanılmadığı zaman [COM öznitelikleri](../windows/com-attributes.md), IDL öznitelikleri arabirimleri tanımlamanıza olanak tanır. Kaynak kodu derlendiğinde öznitelikler oluşturulan .idl dosya tanımlamak için kullanılır. COM öznitelikleri ATL projesinde ile kullanıldığında, bazı IDL gibi özniteliği **coclass'ı**, projeye eklenemeyebilir kod neden.  
  
 Unutmayın [idl_quote](../windows/idl-quote.md) Visual C++ geçerli sürümde desteklenmez MIDL yapıları kullandığınız sağlar. Bu ve diğer öznitelikleri gibi [importlib](../windows/importlib.md) ve [ıncludelıb](../windows/includelib-cpp.md) geçerli Visual C++ projenizdeki varolan .idl dosyaları kullanmak için Yardım.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|[toplanabilir](../windows/aggregatable.md)|Bir denetim başka bir denetim tarafından toplanan olduğunu gösterir.|  
|[appobject](../windows/appobject.md)|Bir tam EXE uygulamayla ilişkili olan ve bu tür kitaplığında coclass'ı özellikleri ve işlevleri genel olarak kullanılabilir olduğunu gösterir bir uygulama nesnesi olarak coclass'ı tanımlar.|  
|[async_uuid](../windows/async-uuid.md)|COM arabirimi zaman uyumlu ve zaman uyumsuz sürümlerini tanımlamak için MIDL derleyici yönlendirir UUID belirtir.|  
|[bindable](../windows/bindable.md)|Özellik veri bağlama desteklediğini belirtir.|  
|[call_as](../windows/call-as.md)|Uzak bir işleve eşlenmesi nonremotable işlevi sağlar.|  
|[durumu](../windows/case-cpp.md)|İle kullanılan [switch_type](../windows/switch-type.md) UNION özniteliği.|  
|[coclass](../windows/coclass.md)|Yerler .idl dosyasına tanımı coclass'ı olarak sınıfı.|  
|[control](../windows/control.md)|Kullanıcı tanımlı tür denetim olduğunu belirtir.|  
|[cpp_quote](../windows/cpp-quote.md)|Belirtilen dize tırnak karakteri olmadan oluşturulan üstbilgi dosyası yayar.|  
|[defaultbind](../windows/defaultbind.md)|En iyi nesneyi temsil eden tek, bağlanabilirse özelliği gösterir.|  
|[defaultcollelem](../windows/defaultcollelem.md)|Visual Basic kodu iyileştirme için kullanılır.|  
|[defaultvalue](../windows/defaultvalue.md)|Yazılı isteğe bağlı bir parametre için varsayılan bir değer belirtimi sağlar.|  
|[default](../windows/default-cpp.md)|Özel veya görüntüleme arabirimi coclass'ı içinde tanımlanan varsayılan programlama arabirimi temsil ettiğini gösterir.|  
|[defaultvtable](../windows/defaultvtable.md)|Bir denetim için varsayılan vtable arabirimi olarak bir arabirim tanımlar.|  
|[dispinterface](../windows/dispinterface.md)|Arabirim dağıtma arabirimi .idl dosyasına yerleştirir.|  
|[displaybind](../windows/displaybind.md)|Kullanıcıya bağlanabilir olarak görüntülenmelidir bir özelliği belirtir.|  
|[dual](../windows/dual.md)|Arabirim çift arabirim .idl dosyasına yerleştirir.|  
|[entry](../windows/entry.md)|Bir verilen işlevi veya sabit bir modüle DLL'deki giriş noktası belirleyerek belirtir.|  
|[first_is](../windows/first-is.md)|Aktarılacak ilk dizi öğenin dizinini belirtir.|  
|[helpcontext](../windows/helpcontext.md)|Kullanıcı görünümü öğeyle ilgili bilgi bu Yardım dosyasındaki olanak sağlayan bir içerik Kimliğini belirtir.|  
|[helpfile](../windows/helpfile.md)|Tür Kitaplığı Yardım dosyasının adını ayarlar.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Yardım konusunun Kimliğini bir .hlp veya .chm dosyasında belirtir.|  
|[helpstringdll](../windows/helpstringdll.md)|Belge dize araması (yerelleştirme) gerçekleştirmek için kullanılacak DLL adını belirtir.|  
|[helpstring](../windows/helpstring.md)|Uygulandığı öğe tanımlamak için kullanılan bir karakter dizesini belirtir.|  
|[hidden](../windows/hidden.md)|Öğe var, ancak kullanıcı odaklı bir tarayıcıda görüntülenmemelidir olduğunu gösterir.|  
|[idl_module](../windows/idl-module.md)|Bir giriş noktası DLL'de belirtir.|  
|[idl_quote](../windows/idl-quote.md)|Öznitelikleri kullanmanıza olanak sağlar veya Visual C++ geçerli sürümünde desteklenmeyen IDL oluşturur.|  
|[id](../windows/id.md)|Üye işlevi (bir özellik veya bir arabirim veya görüntüleme arabirimi bir yöntem) için bir DISPID belirtir.|  
|[iid_is](../windows/iid-is.md)|Arabirim işaretçisi tarafından işaret COM arabirimi IID belirtir.|  
|[immediatebind](../windows/immediatebind.md)|Veritabanı veri bağlama nesnenin bir özelliğini yapılan tüm değişiklikler, hemen bildirilecek gösterir.|  
|[importlib](../windows/importlib.md)|Zaten başka bir tür kitaplığı oluşturulan tür kitaplığı kullanılabilir içine derlenmiştir türleri sağlar.|  
|[import](../windows/import.md)|Ana .idl dosyanızdan başvuru yapmak istediğinizi tanımlarını içeren başka bir .idl, .odl veya üst bilgi dosyasını belirtir.|  
|[içerir](../windows/include-cpp.md)|Oluşturulan .idl dosyasında dahil edilecek bir veya daha fazla üst bilgi dosyaları belirtir.|  
|[includelib](../windows/includelib-cpp.md)|Oluşturulan .idl dosyasında dahil edilecek bir .idl veya .h dosyası neden olur.|  
|[in](../windows/in-cpp.md)|Bir parametre çağrılan yordamı çağırma yordamdan geçirilecek olduğunu gösterir.|  
|[last_is](../windows/last-is.md)|Aktarılacak son dizi öğesinden dizinini belirtir.|  
|[lcid](../windows/lcid.md)|Yerel ayar tanımlayıcısı bir işleve geçirmenize olanak sağlar.|  
|[length_is](../windows/length-is.md)|Aktarılacak dizi öğelerinin sayısını belirtir.|  
|[licensed](../windows/licensed.md)|Geçerli olduğu coclass'ı lisanslanmıştır ve kullanma örneği gerekir gösterir **IClassFactory2**.|  
|[Yerel](../windows/local-cpp.md)|MIDL derleyici arabirimi üstbilgisinde kullanıldığında bir üstbilgi oluşturucuyu olarak kullanmanıza olanak sağlar. Tek bir işlev kullanıldığında, kendisi için hiçbir saplamalar oluşturulan yerel bir yordam belirler.|  
|[max_is](../windows/max-is.md)|Geçerli dizi dizini için maksimum değeri belirler.|  
|[Modülü](../windows/module-cpp.md)|Kitaplık blok .idl dosyasında tanımlar.|  
|[ms_union](../windows/ms-union.md)|Ağ veri gösterimi hizalama nonencapsulated birleşimler denetler.|  
|[no_injected_text](../windows/no-injected-text.md)|Özellik kullanımı sonucunda kodu injecting derleyici engeller.|  
|[nonbrowsable](../windows/nonbrowsable.md)|Bir arabirim üyesi bir özellik tarayıcıda görüntülenmemelidir gösterir.|  
|[noncreatable](../windows/noncreatable.md)|Tek başına başlatılamaz bir nesneyi tanımlar.|  
|[nonextensible](../windows/nonextensible.md)|Belirleyen `IDispatch` uygulaması yalnızca özellikleri içerir ve yöntemleri arabirimi açıklamasında listelenen ve çalışma zamanında ek üyeleriyle genişletilemez.|  
|[object](../windows/object-cpp.md)|Özel bir arabirim tanımlar; özel öznitelik ile eşanlamlı.|  
|[odl](../windows/odl.md)|Arabirim bir nesne Açıklama Dili (ODL) arabirimi olarak tanımlar.|  
|[oleautomation](../windows/oleautomation.md)|Arabirim otomasyon ile uyumlu olup olmadığını gösterir.|  
|[İsteğe bağlı](../windows/optional-cpp.md)|Üye işlevi için isteğe bağlı bir parametre belirtir.|  
|[out](../windows/out-cpp.md)|Çağrılan yordamdan (sunucudan istemciye) arama yordamı döndürülürsünüz işaretçi parametreleri tanımlar.|  
|[pointer_default](../windows/pointer-default.md)|Varsayılan işaretçi özniteliği için tüm işaretçiler görünür üst düzey işaretçileri dışında parametre listelerinde belirtir.|  
|[pragma](../windows/pragma.md)|Belirtilen dize tırnak karakteri olmadan oluşturulan .idl dosyasına yayar.|  
|[progid](../windows/progid.md)|Bir COM nesnesi ProgID belirtir.|  
|[propget](../windows/propget.md)|Özellik erişimcisi (get) işlevini belirtiyor.|  
|[propputref](../windows/propputref.md)|Bir başvuru yerine bir değer kullanır özellik ayarı işlevi belirtir.|  
|[propput](../windows/propput.md)|Bir özellik ayarı işlevi belirtir.|  
|[ptr](../windows/ptr.md)|Bir işaretçi tam bir işaretçi olarak belirler.|  
|[public](../windows/public-cpp-attributes.md)|Bu gelen .idl dosya içinde başvurulmuyor olsa bile bir typedef türü kitaplığa gider sağlar.|  
|[Aralık](../windows/range-cpp.md)|Bağımsız değişken veya değerleri çalışma zamanında ayarlanır alanları için izin verilen değer aralığı belirtir.|  
|[readonly](../windows/readonly-cpp.md)|Bir değişkene atama engelliyor.|  
|[ref](../windows/ref-cpp.md)|Bir başvuru işaretçi tanımlar.|  
|[requestedit](../windows/requestedit.md)|Özellik desteklediğini gösterir **OnRequestEdit** bildirim.|  
|[restricted](../windows/restricted.md)|Bir kitaplık veya modül, arabirim veya görüntüleme arabirimi üyesi rasgele çağrılamaz olduğunu belirtir.|  
|[retval](../windows/retval.md)|Üye dönüş değerini parametre belirler.|  
|[size_is](../windows/size-is.md)|Bellek boyutu boyutlu işaretçileri ayrılmış, boyutlu işaretçiler ve tek veya çok boyutlu diziler işaretçileri boyutta belirtir.|  
|[Kaynak](../windows/source-cpp.md)|Sınıfı, özelliği veya yöntemi üyesi olayları kaynağı olduğunu gösterir.|  
|[string](../windows/string-cpp.md)|Belirten tek boyutlu `char`, `wchar_t`, **bayt**, ya da eşdeğer dizi ya da böyle bir dizi işaretçisine gerekir kabul olarak bir dize.|  
|[switch_is](../windows/switch-is.md)|İfade veya bileşim üyesi seçer birleşim discriminant işlev gören tanımlayıcısını belirtir.|  
|[switch_type](../windows/switch-type.md)|Birleşim discriminant kullanılan değişken türünü tanımlar.|  
|[transmit_as](../windows/transmit-as.md)|Hangi istemci ve sunucu uygulamaları işlemek, sunulan türü, bir iletilen türüyle ilişkilendirmek için derleyicisi bildirir.|  
|[uidefault](../windows/uidefault.md)|Tür bilgileri üye kullanıcı arabiriminde görünen varsayılan üye olduğunu gösterir.|  
|[benzersiz](../windows/unique-cpp.md)|Benzersiz bir işaretçi belirtir.|  
|[usesgetlasterror](../windows/usesgetlasterror.md)|Bu işlev çağrılırken bir hata varsa çağıran sonra çağırabilirsiniz çağıran söyler `GetLastError` hata kodu alınamadı.|  
|[UUID](../windows/uuid-cpp-attributes.md)|Sınıfta veya arabirimde benzersiz Kimliğini belirtir.|  
|[v1_enum](../windows/v1-enum.md)|Belirtilen enum türü 16 bit varsayılan yerine bir 32 bit varlık olarak iletilmesi yönlendirir.|  
|[vararg](../windows/vararg.md)|İşlev değişken sayıda bağımsız değişken sürmesi belirtir.|  
|[vi_progid](../windows/vi-progid.md)|Sürüm bağımsız form ProgID belirtir.|  
|[wire_marshal](../windows/wire-marshal.md)|Bir uygulamaya özgü veri türü yerine iletim için kullanılacak bir veri türünü belirtir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gruplara göre öznitelikler](../windows/attributes-by-group.md)   
 [Öznitelik sınırlamaları](http://msdn.microsoft.com/en-us/6e6c4329-f667-4869-b991-cbe9cb7a8f61)