---
title: IDL öznitelikleri (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- IDL attributes
- .idl files [C++], attributes
- IDL files [C++], attributes
- .idl files [C++]
ms.assetid: 04c596f4-c97b-4952-8053-316678b1d0b6
ms.openlocfilehash: 8cceae2f1c4880b72f1ffc30070d6aa6bf8e3a51
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211976"
---
# <a name="idl-attributes"></a>IDL Öznitelikleri

Geleneksel olarak, bir. IDL dosyasının saklanması şunları yapmak zorunda olduğunuz anlamına gelir:

- Bir. IDL dosyasının yapısını ve söz dizimini değiştirebilmek için hakkında bilgi sahibi olun.

- . IDL dosyasının bazı yönlerini değiştirmenize olanak sağlayan bir sihirbaza güvenin.

Şimdi, Visual C++ IDL özniteliklerini kullanarak bir kaynak kod dosyası içinden. IDL dosyasını değiştirebilirsiniz. Çoğu durumda, Visual C++ IDL öznitelikleri MıDL öznitelikleriyle aynı ada sahiptir. Bir Visual C++ IDL özniteliği ve MıDL özniteliği aynı olduğunda, Visual C++ özniteliğini kaynak kodu dosyanıza koymak, Namesake MıDL özniteliğini içeren bir. IDL dosyasına neden olacaktır. Ancak, bir Visual C++ IDL özniteliği bir MıDL özniteliğinin tüm işlevlerini sağlayamayabilir.

[Com öznitelikleriyle](com-attributes.md)birlikte kullanılmazsa, IDL öznitelikleri arabirimleri tanımlamanızı sağlar. Kaynak kodu derlendiğinde, öznitelikler oluşturulan. IDL dosyasını tanımlamak için kullanılır. Bir ATL projesinde COM öznitelikleriyle birlikte kullanıldığında, gibi bazı IDL öznitelikleri `coclass` projeye eklenebilir.

[İdl_quote](idl-quote.md) , Visual C++ geçerli sürümünde desteklenmeyen MIDL yapılarını kullanmanıza izin verir. Bu ve [ımportlib](importlib.md) ve [ıncludelib](includelib-cpp.md) gibi diğer öznitelikler, geçerli Visual Studio C++ projenizdeki mevcut. IDL dosyalarını kullanmanıza yardımcı olur.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[toplanabilir](aggregatable.md)|Bir denetimin başka bir denetim tarafından toplanamayacağını gösterir.|
|[appobject](appobject.md)|Coclass 'ı tam bir EXE uygulamasıyla ilişkili bir uygulama nesnesi olarak tanımlar ve coclass 'ın işlev ve özelliklerinin bu tür kitaplığında genel olarak kullanılabildiğini gösterir.|
|[async_uuid](async-uuid.md)|Bir COM arabiriminin hem zaman uyumlu hem de zaman uyumsuz sürümlerini tanımlamak için MıDL derleyicisini yönlendiren UUID 'yi belirtir.|
|[bağlanabilir](bindable.md)|Özelliğin veri bağlamayı desteklediğini belirtir.|
|[call_as](call-as.md)|Uzaktan erişilemeyen bir işlevin uzak bir işlevle eşleştirilmesini sağlar.|
|[harflerini](case-cpp.md)|Bir birleşimdeki [switch_type](switch-type.md) özniteliğiyle birlikte kullanılır.|
|[coclass](coclass.md)|Sınıf tanımını bir. IDL dosyasına, coclass olarak koyar.|
|[denetimle](control.md)|Kullanıcı tanımlı türün bir denetim olduğunu belirtir.|
|[cpp_quote](cpp-quote.md)|Belirtilen dizeyi, tırnak karakterleri olmadan, oluşturulan üst bilgi dosyasına yayar.|
|[defaultbind](defaultbind.md)|Nesneyi en iyi şekilde temsil eden tek ve bağlanabilir özelliği gösterir.|
|[defaultcollelem](defaultcollelem.md)|Visual Basic kodu iyileştirmesi için kullanılır.|
|[defaultvalue](defaultvalue.md)|Türü belirtilmiş bir isteğe bağlı parametre için varsayılan değer belirtimine izin verir.|
|[default](default-cpp.md)|Bir coclass içinde tanımlanan özel veya dispınterface 'in varsayılan programlama arabirimini temsil ettiğini belirtir.|
|[defaultvtable](defaultvtable.md)|Bir denetim için varsayılan vtable arabirimi olarak bir arabirimi tanımlar.|
|[dispinterface](dispinterface.md)|Bir arabirimi. IDL dosyasına bir dağıtım arabirimi olarak koyar.|
|[displaybind](displaybind.md)|Kullanıcıya bağlanabilir olarak görüntülenmesi gereken bir özelliği gösterir.|
|[çift](dual.md)|. IDL dosyasına bir arabirimi çift arabirim olarak koyar.|
|[girişte](entry.md)|DLL 'deki giriş noktasını tanımlayarak bir modülde, bir içe aktarılmış işlevi veya sabiti belirtir.|
|[first_is](first-is.md)|İletilmek üzere ilk dizi öğesinin dizinini belirtir.|
|[helpcontext](helpcontext.md)|Kullanıcının Yardım dosyasında bu öğeyle ilgili bilgileri görüntülemesine imkan tanıyan bir bağlam KIMLIĞI belirtir.|
|[helpfile](helpfile.md)|Bir tür kitaplığı için yardım dosyasının adını ayarlar.|
|[helpstringcontext](helpstringcontext.md)|Bir. hlp veya. chm dosyasındaki Yardım konusunun KIMLIĞINI belirtir.|
|[helpstringdll](helpstringdll.md)|Belge dizesi aramasını (Yerelleştirme) gerçekleştirmek için kullanılacak DLL 'in adını belirtir.|
|[helpstring](helpstring.md)|Uygulandığı öğeyi anlatmak için kullanılan bir karakter dizesini belirtir.|
|[gizli](hidden.md)|Öğenin var olduğunu ancak kullanıcıya dayalı bir tarayıcıda gösterilmemelidir.|
|[idl_module](idl-module.md)|DLL 'de bir giriş noktası belirtir.|
|[idl_quote](idl-quote.md)|Geçerli Visual C++ sürümünde desteklenmeyen öznitelikleri veya IDL yapılarını kullanmanıza izin verir.|
|[id](id.md)|Bir üye işlev için bir DISPID belirtir (bir özellik veya bir yöntem, bir arabirim ya da dispınterface).|
|[iid_is](iid-is.md)|Bir arabirim işaretçisi tarafından işaret edilen COM arabiriminin IID 'sini belirtir.|
|[immediatebind](immediatebind.md)|Veritabanına, veri bağlantılı nesnenin bir özelliğindeki tüm değişikliklerin hemen bildirileceğini bildirir.|
|[importlib](importlib.md)|Oluşturulan tür kitaplığı için kullanılabilir başka bir tür kitaplığına derlenmiş olan türleri oluşturur.|
|[aktarmaya](import.md)|Main. IDL dosyanızda başvurmak istediğiniz tanımları içeren başka bir. IDL,. odl veya üst bilgi dosyasını belirtir.|
|[içeriyor](include-cpp.md)|Oluşturulan. IDL dosyasına dahil edilecek bir veya daha fazla üst bilgi dosyasını belirtir.|
|[INCLUDELIB](includelib-cpp.md)|Oluşturulan. IDL dosyasına bir. IDL veya. h dosyasının eklenmesine neden olur.|
|[in](in-cpp.md)|Çağıran yordamdan çağrılan yordama bir parametre geçirilecek olduğunu gösterir.|
|[last_is](last-is.md)|İletilmek üzere son dizi öğesinin dizinini belirtir.|
|[lcid](lcid.md)|Bir işleve yerel ayar tanımlayıcıyı geçirmenize olanak sağlar.|
|[length_is](length-is.md)|Aktarılacak dizi öğelerinin sayısını belirtir.|
|[lisanslı](licensed.md)|Geçerli olduğu coclass 'ın lisanslandığını ve kullanılarak örneğinin oluşturulması gerektiğini gösterir `IClassFactory2` .|
|[Yerel](local-cpp.md)|Arabirim üstbilgisinde kullanıldığında MıDL derleyicisini üst bilgi Oluşturucu olarak kullanmanıza olanak tanır. Tek bir işlevde kullanıldığında, hiçbir saplamalar üretilmeden önce bir yerel yordam belirler.|
|[max_is](max-is.md)|Geçerli bir dizi dizininin en büyük değerini belirtir.|
|[birimi](module-cpp.md)|. IDL dosyasında kitaplık bloğunu tanımlar.|
|[ms_union](ms-union.md)|Kapsüllenolmayan birleşimlerin ağ verisi gösterimi hizalamasını denetler.|
|[no_injected_text](no-injected-text.md)|Öznitelik kullanımı sonucu olarak derleyicinin ekleme kodundan yapılmasını engeller.|
|[nonbrowsable](nonbrowsable.md)|Bir arabirim üyesinin bir özellik tarayıcısında görüntülenmemesi gerektiğini belirtir.|
|[noncreatable](noncreatable.md)|Kendisi tarafından örneklenemez bir nesne tanımlar.|
|[nonextensible](nonextensible.md)|`IDispatch`Uygulamanın yalnızca arabirim açıklamasında listelenen özellikleri ve yöntemleri içerdiğini belirtir ve çalışma zamanında ek üyelerle birlikte genişletilemez.|
|[object](object-cpp.md)|Özel bir arabirim tanımlar; Özel öznitelikle eşanlamlı.|
|[odl](odl.md)|Bir arabirimi nesne Açıklama Dili (ODL) arabirimi olarak tanımlar.|
|[oleautomation](oleautomation.md)|Bir arabirimin Otomasyon ile uyumlu olduğunu gösterir.|
|[seçim](optional-cpp.md)|Bir üye işlevi için isteğe bağlı bir parametre belirtir.|
|[dışı](out-cpp.md)|Çağrılan yordamdan çağıran yordama (sunucudan istemciye) döndürülen işaretçi parametrelerini tanımlar.|
|[pointer_default](pointer-default.md)|Parametre listelerinde görünen en üst düzey işaretçiler hariç tüm işaretçiler için varsayılan işaretçi özniteliğini belirtir.|
|[pragma](pragma.md)|Belirtilen dizeyi, tırnak karakterleri olmadan, oluşturulan. IDL dosyasına yayar.|
|[progid](progid.md)|COM nesnesi için ProgID belirtir.|
|[propget](propget.md)|Bir özellik erişimcisi (Get) işlevi belirtir.|
|[propputref](propputref.md)|Değer yerine başvuru kullanan bir özellik ayarı işlevi belirtir.|
|[propput](propput.md)|Bir özellik ayarı işlevi belirtir.|
|[ptr](ptr.md)|Bir işaretçiyi tam bir işaretçi olarak belirler.|
|[genel](public-cpp-attributes.md)|Bir typedef 'in,. IDL dosyası içinden başvurulmamış olsa bile tür kitaplığına gitmesini sağlar.|
|[aralığı](range-cpp.md)|Değerleri çalışma zamanında ayarlanmış olan bağımsız değişkenler veya alanlar için izin verilen değerler aralığını belirtir.|
|[readonly](readonly-cpp.md)|Bir değişkene atamayı yasaklar.|
|[ref](ref-cpp.md)|Başvuru işaretçisini tanımlar.|
|[requestedit](requestedit.md)|Özelliğin bildirimi desteklediğini gösterir `OnRequestEdit` .|
|[dığından](restricted.md)|Bir kitaplığın veya bir modülün, arabirimin veya dispınterface üyesinin rastgele çağrılamıyor olduğunu belirtir.|
|[retval](retval.md)|Üyenin dönüş değerini alan parametreyi belirler.|
|[size_is](size-is.md)|Boyutlandırılmış işaretçiler için ayrılan bellek boyutunu, boyutlandırılmış işaretçilere boyutlandırılmış boyutları ve tek veya çok boyutlu dizileri belirtir.|
|[kaynaktaki](source-cpp.md)|Bir sınıfın, özelliğin veya yöntemin bir üyesinin bir olay kaynağı olduğunu belirtir.|
|[dizisinde](string-cpp.md)|Tek boyutlu **`char`** , **`wchar_t`** , `byte` veya denk dizi ya da bu dizi işaretçisinin bir dize olarak değerlendirilmesi gerektiğini gösterir.|
|[switch_is](switch-is.md)|Birleşim üyesini seçen birleşim ayırt edici olarak davranan ifade veya tanımlayıcıyı belirtir.|
|[switch_type](switch-type.md)|UNION ayrımınant olarak kullanılan değişkenin türünü tanımlar.|
|[transmit_as](transmit-as.md)|Derleyiciye, iletilen bir tür ile istemci ve sunucu uygulamalarının üzerinde bulunan, sunulan bir türü ilişkilendirmesini söyler.|
|[uidefault](uidefault.md)|Tür bilgisi üyesinin Kullanıcı arabiriminde görüntülenmek üzere varsayılan üye olduğunu gösterir.|
|[unique](unique-cpp.md)|Benzersiz bir işaretçi belirtir.|
|[usesgetlasterror](usesgetlasterror.md)|Çağrıyı yapana, bu işlevi çağırırken bir hata oluşursa, çağıranın `GetLastError` hata kodunu almak için çağırabileceklerini söyler.|
|[uuid](uuid-cpp-attributes.md)|Bir sınıf veya arabirim için benzersiz KIMLIĞI belirtir.|
|[v1_enum](v1-enum.md)|Belirtilen numaralandırılmış türün 16 bit varsayılan yerine 32 bitlik bir varlık olarak aktarılacağını yönlendirir.|
|[vararg](vararg.md)|İşlevin değişken sayıda bağımsız değişken alıp alan belirtir.|
|[vi_progid](vi-progid.md)|ProgID 'nin sürümden bağımsız bir biçimini belirtir.|
|[wire_marshal](wire-marshal.md)|Uygulamaya özgü veri türü yerine iletim için kullanılacak bir veri türü belirtir.|

## <a name="see-also"></a>Ayrıca bkz.

[Gruba göre öznitelikler](attributes-by-group.md)
