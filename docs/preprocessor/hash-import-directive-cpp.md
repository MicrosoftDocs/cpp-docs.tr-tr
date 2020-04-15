---
title: '##import yönergesi (C++)'
ms.date: 08/29/2019
f1_keywords:
- '#import'
helpviewer_keywords:
- .tlh files
- '#import directive'
- import directive (#import)
- tlh files
- tlbid switch
- preprocessor, directives
- COM, type library header file
ms.assetid: 787d1112-e543-40d7-ab15-a63d43f4030a
ms.openlocfilehash: 9cdfef091b659151f427c381e386f0e83396e741
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332063"
---
# <a name="import-directive-c"></a>#import yönergesi (C++)

**C++ Özel**

Tür kitaplığından gelen bilgileri birleştirmek için kullanılır. Tür kitaplığın içeriği, çoğunlukla COM arabirimlerini açıklayan C++ sınıflarına dönüştürülür.

## <a name="syntax"></a>Sözdizimi

> **#import** "*dosya* \[adı " *öznitelikleri*]\
> **#import** \< *dosya adı*> \[*öznitelikleri*]

### <a name="parameters"></a>Parametreler

*Dosyaadı*\
İçe aktarılabilmek için tür kitaplığını belirtir. *Dosya adı* aşağıdaki türlerden biri olabilir:

- .olb, .tlb veya .dll dosyası gibi tür kitaplığı içeren bir dosyanın adı. Anahtar kelime, `file:`, her dosya adından önce gelebilir.

- Tür kitaplığında bir denetimin progid'i. Anahtar kelime, `progid:`, her progid önce olabilir. Örneğin:

    ```cpp
    #import "progid:my.prog.id.1.5"
    ```

   Progids hakkında daha fazla bilgi için [bkz.](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber)

   64 bit işletim sisteminde 32 bit çapraz derleyici kullandığınızda, derleyici yalnızca 32 bit kayıt defteri kovanı okuyabilir. 64 bit türünde bir kitaplık oluşturmak ve kaydetmek için yerel 64 bit derleyiciyi kullanmak isteyebilirsiniz.

- Tür kitaplığın kitaplık kimliği. Anahtar kelime, `libid:`, her kitaplık kimliği önce olabilir. Örneğin:

    ```cpp
    #import "libid:12341234-1234-1234-1234-123412341234" version("4.0") lcid("9")
    ```

   Belirtmezseniz `version` `lcid`veya , uygulanan [rules](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber) `progid:` kurallar `libid:`da uygulanır.

- Çalıştırılabilir (.exe) dosyası.

- Tür kitaplığı kaynağı (.ocx gibi) içeren bir kitaplık (.dll) dosyası.

- Tür kitaplığı tutan bileşik belge.

- **LoadTypeLib** API tarafından anlaşılabilecek diğer dosya biçimleri.

*Öznitelik*\
Bir veya daha fazla [#import öznitelikleri](#_predir_the_23import_directive_import_attributes). Bir boşluk veya virgül ile ayrı öznitelikleri. Örneğin:

```cpp
#import "..\drawctl\drawctl.tlb" no_namespace, raw_interfaces_only
```

\-veya-

```cpp
#import "..\drawctl\drawctl.tlb" no_namespace raw_interfaces_only
```

## <a name="remarks"></a>Açıklamalar

### <a name="search-order-for-filename"></a><a name="_predir_the_23import_directive_searchorderforfilename"></a>Dosya adı için arama sırası

*dosya adı* isteğe bağlı olarak bir dizin belirtimi tarafından önce gelir. Dosya adı varolan bir dosyayı adlandırmalıdır. İki sözdizimi biçimi arasındaki fark, yol tam olarak belirtilmediğinde önişlemcinin tür kitaplığı dosyalarını arama sırasıdır.

|Sözdizimi formu|Eylem|
|-----------------|------------|
|Alıntı formu|Ön işlemciye, **önce #import** deyimini içeren dosyadizininde ve daha sonra bu dosyayı içeren`#include`dosyaların dizinlerinde tür kitaplığı dosyalarını aramasını bildirir. Önişlemci daha sonra aşağıda gösterilen yollar boyunca arama.|
|Açı-braket formu|Ön işlemciye aşağıdaki yollar boyunca kitaplık dosyalarını arama talimatı verir:<br /><br /> 1. `PATH` Çevre değişken yol listesi<br />2. `LIB` Çevre değişken yol listesi<br />3. [/I](../build/reference/i-additional-include-directories.md) derleyici seçeneği tarafından belirtilen yol, bunun dışında derleyici [no_registry](../preprocessor/no-registry.md) özniteliği ile başka bir tür kitaplığı başvurulan bir tür kitaplığı arıyor.|

### <a name="specify-the-localization-id-and-version-number"></a><a name="_predir_the_23import_directive_specifyingthelocalizationidandversionnumber"></a>Yerelleştirme kimliği ve sürüm numarasını belirtin

Bir progid belirttiğiniz zaman, progid'in yerelleştirme kimliğini ve sürüm numarasını da belirtebilirsiniz. Örneğin:

```cpp
#import "progid:my.prog.id" lcid("0") version("4.0)
```

Bir yerelleştirme kimliği belirtmezseniz, aşağıdaki kurallara göre bir progid seçilir:

- Yalnızca bir yerelleştirme kimliği varsa, bu kimlik kullanılır.

- Birden fazla yerelleştirme kimliği varsa, sürüm numarası 0, 9 veya 409 olan ilk kimlik kullanılır.

- Birden fazla yerelleştirme kimliği varsa ve bunların hiçbiri 0, 9 veya 409 değilse, sonuncusu kullanılır.

- Bir sürüm numarası belirtmezseniz, en son sürüm kullanılır.

### <a name="header-files-created-by-import"></a><a name="_predir_the_23import_directive_header_files_created_by_import"></a>Alma tarafından oluşturulan üstbilgi dosyaları

**#import,** C++ kaynak kodundaki tür kitaplığı içeriğini yeniden oluşturan iki üstbilgi dosyası oluşturur. Birincil üstbilgi dosyası, Microsoft Arabirim Tanımı Dili (MIDL) derleyicisi tarafından üretilen, ancak ek derleyici tarafından oluşturulan kod ve verilerle birlikte oluşturulan dosyaya benzer. [Birincil üstbilgi dosyası,](#_predir_the_primary_type_library_header_file) tür kitaplığıyla aynı temel ada ve bir . TLH uzantısı. İkincil üstbilgi dosyası, tür kitaplığıyla aynı temel ada sahiptir ve . TLI uzantısı. Derleyici tarafından oluşturulan üye işlevler için uygulamaları içerir`#include`ve ( ) birincil üstbilgi dosyasına dahil edilir.

Parametreleri kullanan `byref` bir dispinterface özelliği alıyorsanız, **#import** işlev için bir [__declspec (özellik)](../cpp/property-cpp.md) deyimi oluşturmaz.

Her iki üstbilgi dosyası [/Fo (ad nesnesi dosyası)](../build/reference/fo-object-file-name.md) seçeneği tarafından belirtilen çıktı dizinine yerleştirilir. Daha sonra derleyici tarafından birincil üstbilgi dosyası bir `#include` yönerge tarafından adlandırılmış gibi okunur ve derlenir.

Aşağıdaki derleyici optimizasyonları **#import** yönergesi ile birlikte gelir:

- Üstbilgi dosyası, oluşturulduğunda, tür kitaplığı ile aynı zaman damgası verilir.

- **#import** işlendiğinde, derleyici ilk olarak üstbilginin var olup olmadığını ve güncel olup olmadığını denetler. Evet ise, yeniden oluşturulması gerekmez.

**#import** yönergesi de en az yeniden oluşturma katılır ve önceden derlenmiş bir üstbilgi dosyasına yerleştirilebilir.  Daha fazla bilgi için [bkz.](../build/creating-precompiled-header-files.md)

### <a name="primary-type-library-header-file"></a><a name="_predir_the_primary_type_library_header_file"></a>Birincil tür kitaplığı üstbilgi dosyası

Birincil tür kitaplığı üstbilgi dosyası yedi bölümden oluşur:

- Başlık kazan: comdef `#include` için yorum, ifade oluşur. H (üstbilgide kullanılan bazı standart makroları tanımlar) ve diğer çeşitli kurulum bilgileri.

- İleri referanslar ve typedefs: gibi `struct IMyInterface` yapı bildirimleri ve typedefs oluşur.

- Akıllı işaretçi bildirimleri: `_com_ptr_t` Şablon sınıfı akıllı bir işaretçidir. Arabirim işaretçileri kapsüller ve arama `AddRef`ihtiyacını ortadan `Release`kaldırır `QueryInterface` , ve işlevleri. Ayrıca, yeni `CoCreateInstance` bir COM nesnesi oluştururken aramayı gizler. Bu bölüm, `_COM_SMARTPTR_TYPEDEF` [_com_ptr_t](../cpp/com-ptr-t-class.md) şablon sınıfının şablon uzmanlıkları olarak COM arabirimlerinin typedefs oluşturmak için makro deyimini kullanır. Örneğin, arayüz `IMyInterface`için , . TLH dosyası şunları içerecektir:

    ```TLH
    _COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));
    ```

   derleyicinin genişleteceği:

    ```cpp
    typedef _com_ptr_t<_com_IIID<IMyInterface, __uuidof(IMyInterface)> > IMyInterfacePtr;
    ```

   Türü `IMyInterfacePtr` daha sonra ham arabirim işaretçisi `IMyInterface*`yerine kullanılabilir. Sonuç olarak, çeşitli `IUnknown` üye işlevleri çağırmaya gerek yoktur

- Typeinfo bildirimleri: Öncelikle sınıf tanımları ve diğer öğeleri tarafından `ITypeLib:GetTypeInfo`döndürülen tek tek typeinfo öğeleri açığa oluşur. Bu bölümde, tür kitaplığından her yazı `TYPEKIND` bilgisi, bilgilere bağlı bir formda üstbilgiye yansıtılır.

- İsteğe bağlı eski stil GUID tanımı: Adlandırılmış GUID sabitlerinin başharflerini içerir. Bu adlar, `CLSID_CoClass` `IID_Interface`MIDL derleyicisi tarafından oluşturulanlara benzer bir forma sahiptir.

- `#include`ikincil tür kitaplık üstbilgisi için deyim.

- Alter kazan: Şu `#pragma pack(pop)`anda içerir .

Başlık kazan ve alter kazan bölümü hariç tüm bölümler, orijinal IDL dosyasında `library` ifadede adı belirtilen bir ad alanına eklenir. Ad alanı adını kullanarak açık bir nitelik tarafından tür kitaplığı üstbilgisinden adları kullanabilirsiniz. Veya aşağıdaki ifadeyi ekleyebilirsiniz:

```cpp
using namespace MyLib;
```

kaynak kodundaki **#import** ifadesinden hemen sonra.

Ad **alanı, #import** yönergesinin [no_namespace)](no-namespace.md)özniteliği kullanılarak bastırılabilir. Ancak, ad alanını bastırmak ad çakışmalarına neden olabilir. Ad [alanı, rename_namespace](rename-namespace.md) özniteliği yle de yeniden adlandırılabilir.

Derleyici, şu anda işlemekte olduğu tür kitaplığı tarafından gereken tür kitaplığı bağımlılığına tam yol sağlar. Yol, açıklama biçiminde, tür kitaplığı üstbilgisine yazılır (. TLH) derleyicinin her işlenmiş tür kitaplığı için oluşturduğu.

Tür kitaplığı, diğer tür kitaplıklarında tanımlanan türlere başvurular içeriyorsa, TLH dosyası aşağıdaki türde açıklamalar içerecektir:

```TLH
//
// Cross-referenced type libraries:
//
//  #import "c:\path\typelib0.tlb"
//
```

**#import** açıklamadaki gerçek dosya adı, kayıt defterinde depolanan çapraz başvurulu tür kitaplığın tam yoludur. Tür tanımlarının eksik olması nedeniyle hatalarla karşılaşırsanız, 'nin başındaki açıklamaları kontrol edin. TLH önce hangi bağımlı tür kitaplıkların alınması gerekebileceğini görmek için. Olası hatalar sözdizimi hatalarıdır (örneğin, C2143, C2146, C2321), C2501 (eksik decl-belirteçler) veya C2433 ('inline' veri bildiriminde izin verilmez) derlenirken . TLI dosyası.

Bağımlılık hatalarını gidermek için, bağımlılık açıklamalarından hangilerinin sistem üstileri tarafından başka şekilde sağlanmadığını belirleyin ve bağımlı tür kitaplığı **#import** yönergesinden önce bir noktada **#import** bir yönerge sağlayın.

### <a name="import-attributes"></a><a name="_predir_the_23import_directive_import_attributes"></a>#import öznitelikleri

**#import** isteğe bağlı olarak bir veya daha fazla öznitelik içerebilir. Bu öznitelikler derleyiciye tür kitaplığı üstbilgilerinin içeriğini değiştirmesini söyler. Bir ters**\\**eğik çizgi ( ) simgesi, tek bir **#import** deyimine ek satırlar eklemek için kullanılabilir. Örneğin:

```cpp
#import "test.lib" no_namespace \
   rename("OldName", "NewName")
```

Daha fazla bilgi için [#import özniteliklerine](../preprocessor/hash-import-attributes-cpp.md)bakın.

**END C++ Özel**

## <a name="see-also"></a>Ayrıca bkz.

[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)\
[Derleyici COM desteği](../cpp/compiler-com-support.md)
