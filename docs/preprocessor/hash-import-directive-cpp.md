---
description: 'Daha fazla bilgi edinin: #import yönergesi (C++)'
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
ms.openlocfilehash: 73768071dd0ee300ad7b2fd2706fda0ed76067ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269282"
---
# <a name="import-directive-c"></a>#import yönergesi (C++)

**C++ özel**

Bir tür kitaplığından bilgi birleştirmek için kullanılır. Tür kitaplığının içeriği, genellikle COM arabirimlerini açıklayan C++ sınıflarına dönüştürülür.

## <a name="syntax"></a>Syntax

> **#import** "*dosya adı*" \[ *öznitelikleri*] \
> **#import** \<*filename*> \[ *öznitelikler*]

### <a name="parameters"></a>Parametreler

*kısaltın*\
İçeri aktarılacak tür kitaplığını belirtir. *Dosya adı* aşağıdaki türlerinden biri olabilir:

- Bir. olb,. tlb veya. dll dosyası gibi bir tür kitaplığı içeren bir dosyanın adı. Anahtar sözcüğü, `file:` her dosya adının önüne alabilir.

- Tür kitaplığındaki bir denetimin ProgID 'si. Anahtar sözcüğü, `progid:` her bir ProgID 'den önce olabilir. Örneğin:

    ```cpp
    #import "progid:my.prog.id.1.5"
    ```

   ProgID 'ler hakkında daha fazla bilgi için bkz. [YERELLEŞTIRME kimliği ve sürüm numarasını belirtme](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber).

   64 bit işletim sisteminde 32 bitlik bir çapraz derleyici kullandığınızda, derleyici yalnızca 32-bit kayıt defteri kovanını okuyabilir. 64 bit tür kitaplığı derlemek ve kaydettirmek için yerel 64 bit derleyicisini kullanmak isteyebilirsiniz.

- Tür kitaplığının kitaplık KIMLIĞI. Anahtar sözcüğü, `libid:` her bir KITAPLıK kimliğinin önüne eklenebilir. Örneğin:

    ```cpp
    #import "libid:12341234-1234-1234-1234-123412341234" version("4.0") lcid("9")
    ```

   `version`Veya belirtmezseniz `lcid` , ' ye uygulanan [kurallar](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber) da ' a `progid:` uygulanır `libid:` .

- Yürütülebilir (. exe) dosya.

- Bir tür kitaplığı kaynağı (örn. ocx) içeren bir kitaplık (. dll) dosyası.

- Bir tür kitaplığını tutan bileşik bir belge.

- **LoadTypeLib** API 'si tarafından anlaşılabilecek diğer dosya biçimleri.

*özelliklerine*\
Bir veya daha fazla [#import özniteliği](#_predir_the_23import_directive_import_attributes). Öznitelikleri boşluk veya virgül ile ayırın. Örneğin:

```cpp
#import "..\drawctl\drawctl.tlb" no_namespace, raw_interfaces_only
```

\-veya

```cpp
#import "..\drawctl\drawctl.tlb" no_namespace raw_interfaces_only
```

## <a name="remarks"></a>Açıklamalar

### <a name="search-order-for-filename"></a><a name="_predir_the_23import_directive_searchorderforfilename"></a> Dosya adı için arama sırası

*dosya adı* , isteğe bağlı olarak bir dizin belirtimi tarafından yapılır. Dosya adı var olan bir dosyayı adı olmalıdır. İki sözdizimi formu arasındaki fark, yol tam olarak belirtilmediğinde Önişlemci 'nin tür kitaplığı dosyalarını arayacağı sıradır.

|Söz dizimi biçimi|Eylem|
|-----------------|------------|
|Alıntılanmış form|Önişlemci 'yi, **#import** ifadesini içeren dosyanın dizinindeki önce tür kitaplığı dosyalarını, sonra da dosyanın hangi dosyalara ( `#include` ) sahip olduğunu arayacağını söyler. Ön işlemci daha sonra aşağıda gösterilen yollar üzerinde arama yapar.|
|Açılı ayraç formu|Önişlemci 'yi aşağıdaki yollarla tür kitaplığı dosyalarını arayacak şekilde yönlendirir:<br /><br /> 1. `PATH` ortam değişkeni yol listesi<br />2. `LIB` ortam değişkeni yol listesi<br />3. [/i](../build/reference/i-additional-include-directories.md) derleyici seçeneği tarafından belirtilen yol, derleyici, [no_registry](../preprocessor/no-registry.md) özniteliğiyle başka bir tür kitaplığından başvurulan bir tür kitaplığı arıyor.|

### <a name="specify-the-localization-id-and-version-number"></a><a name="_predir_the_23import_directive_specifyingthelocalizationidandversionnumber"></a> Yerelleştirme KIMLIĞI ve sürüm numarasını belirtin

Bir ProgID belirttiğinizde, ProgID 'nin yerelleştirme KIMLIĞINI ve sürüm numarasını da belirtebilirsiniz. Örneğin:

```cpp
#import "progid:my.prog.id" lcid("0") version("4.0)
```

Bir yerelleştirme KIMLIĞI belirtmezseniz, aşağıdaki kurallara göre bir ProgID seçilir:

- Yalnızca bir yerelleştirme KIMLIĞI varsa, bunlardan biri kullanılır.

- Birden fazla yerelleştirme KIMLIĞI varsa, sürüm numarası 0, 9 veya 409 olan ilki kullanılır.

- Birden fazla yerelleştirme KIMLIĞI varsa ve bunlardan hiçbiri 0, 9 veya 409 değilse, en son kullanılır.

- Sürüm numarası belirtmezseniz, en son sürüm kullanılır.

### <a name="header-files-created-by-import"></a><a name="_predir_the_23import_directive_header_files_created_by_import"></a> İçeri aktarma tarafından oluşturulan başlık dosyaları

**#import** , C++ kaynak kodunda tür kitaplığı içeriğini yeniden oluşturan iki üst bilgi dosyası oluşturur. Birincil üstbilgi dosyası, Microsoft Arabirim Tanımlama Dili (MıDL) derleyicisi tarafından üretilen, ancak derleyici tarafından oluşturulan ek kod ve verilerle benzerdir. [Birincil üstbilgi dosyası](#_predir_the_primary_type_library_header_file) tür kitaplığı ile aynı temel ada sahiptir ve bir. TLH uzantısı. İkincil üstbilgi dosyası, ile tür kitaplığı ile aynı temel ada sahiptir. TLI uzantısı. Derleyici tarafından üretilen üye işlevleri için uygulamaları içerir ve `#include` birincil üstbilgi dosyasında () bulunur.

Parametreleri kullanan bir dispınterface özelliği içeri aktarılmazsa `byref` , **#import** işlev için bir [__declspec (özellik)](../cpp/property-cpp.md) açıklaması oluşturmaz.

Her iki üstbilgi dosyası da [/fo (ad nesne dosyası)](../build/reference/fo-object-file-name.md) seçeneği tarafından belirtilen çıkış dizinine yerleştirilir. Bunlar, birincil üst bilgi dosyası bir yönerge tarafından adlandırılmışsa, derleyici tarafından okunırlar ve derlenirler `#include` .

Aşağıdaki derleyici iyileştirmeleri **#import** yönergesiyle birlikte gelir:

- Oluşturulan üstbilgi dosyası, tür kitaplığıyla aynı zaman damgasına verilir.

- **#İmport** işlendiğinde, derleyici ilk olarak üstbilginin var olduğunu ve güncel olup olmadığını denetler. Yanıt Evet ise, yeniden oluşturulması gerekmez.

**#İmport** yönergesi, en az yeniden oluşturma ile katılıyorsa ön derlenmiş üstbilgi dosyasına yerleştirilebilir.  Daha fazla bilgi için bkz. [önceden derlenmiş üst bilgi dosyaları oluşturma](../build/creating-precompiled-header-files.md).

### <a name="primary-type-library-header-file"></a><a name="_predir_the_primary_type_library_header_file"></a> Birincil tür kitaplığı üstbilgi dosyası

Birincil tür kitaplığı üstbilgi dosyası yedi bölümden oluşur:

- Başlık demirbaş: COMDEF için olan açıklamalardan oluşur `#include` . H (üst bilgide kullanılan bazı standart makroları tanımlar) ve diğer çeşitli kurulum bilgileri.

- İleri başvurular ve tür tanımları: gibi yapı bildirimlerinden ve tür `struct IMyInterface` tanımları oluşur.

- Akıllı işaretçi bildirimleri: şablon sınıfı `_com_ptr_t` akıllı bir işaretçisidir. Arabirim işaretçilerini kapsüller, ve işlevleri çağırma gereksinimini ortadan kaldırır `AddRef` `Release` `QueryInterface` . Ayrıca, `CoCreateInstance` Yeni BIR com nesnesi oluştururken çağrıyı gizler. Bu bölümde, `_COM_SMARTPTR_TYPEDEF` [_com_ptr_t](../cpp/com-ptr-t-class.md) şablon sınıfının şablon Uzmanlıkları olarak com arabirimlerinin tür tanımları 'ları oluşturmak için Macro deyimleri kullanılmaktadır. Örneğin, arabirimi için, `IMyInterface` . TLH dosyası şunları içerir:

    ```TLH
    _COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));
    ```

   derleyicinin hangi şekilde genişlendirilecektir:

    ```cpp
    typedef _com_ptr_t<_com_IIID<IMyInterface, __uuidof(IMyInterface)> > IMyInterfacePtr;
    ```

   `IMyInterfacePtr`Daha sonra tür, ham arabirim işaretçisinin yerine kullanılabilir `IMyInterface*` . Sonuç olarak, çeşitli `IUnknown` üye işlevlerini çağırmanız gerekmez

- TypeInfo bildirimleri: Öncelikle, tarafından döndürülen tek bir TypeInfo öğesini açığa çıkaran sınıf tanımlarından ve diğer öğelerden oluşur `ITypeLib:GetTypeInfo` . Bu bölümde, tür kitaplığındaki her bir TypeInfo, bilgilere bağlı olan bir formdaki üstbilgiye yansıtılır `TYPEKIND` .

- İsteğe bağlı eski stil GUID tanımı: Adlandırılmış GUID sabitlerinin başlatmaları Içerir. Bu adlar, `CLSID_CoClass` ve `IID_Interface` , MIDL derleyicisi tarafından üretilenlere benzer biçimde yapılır.

- `#include` ikincil tür kitaplığı üst bilgisi için olan bildirim.

- Altbilgi demirbaş: Şu anda dahildir `#pragma pack(pop)` .

Başlık ortak ve altbilgi ortak bölümü dışındaki tüm bölümler, `library` özgün IDL dosyasındaki ifadesiyle belirtilen adına sahip bir ad alanı içine alınmıştır. Tür kitaplığı üstbilgisindeki adları, ad alanı adını kullanarak açık bir nitelik ile kullanabilirsiniz. Ya da aşağıdaki ifadeyi dahil edebilirsiniz:

```cpp
using namespace MyLib;
```

kaynak kodundaki **#import** deyimden hemen sonra.

Ad alanı, **#import** yönergesinin [no_namespace](no-namespace.md)) özniteliği kullanılarak gizlenebilir. Ancak, ad alanını gizleme ad çakışmalarına neden olabilir. Ad alanı [rename_namespace](rename-namespace.md) özniteliği tarafından da yeniden adlandırılabilir.

Derleyici, şu anda işlediği tür kitaplığı için gereken herhangi bir tür kitaplığı bağımlılığının tam yolunu sağlar. Yol, açıklama biçiminde, tür kitaplığı üst bilgisine (. TLH) her işlenen tür kitaplığı için derleyicinin oluşturduğu.

Bir tür kitaplığı, diğer tür kitaplıklarında tanımlanan türlere başvurular içeriyorsa,. TLH dosyası, aşağıdaki sıralamanın açıklamalarını içerir:

```TLH
//
// Cross-referenced type libraries:
//
//  #import "c:\path\typelib0.tlb"
//
```

**#İmport** açıklamasında gerçek dosya adı, çapraz başvurulan tür kitaplığının kayıt defterinde saklanan tam yoludur. Eksik tür tanımlarının neden olduğu hatalarla karşılaşırsanız, içindeki açıklamaları kontrol edin. İlk olarak hangi bağımlı tür kitaplıklarının içeri aktarılması gerektiğini görmek için TLH. Olası hatalar, derleme sırasında sözdizimi hatalarıyla (örneğin, C2143, C2146, C2321), C2501 (eksik decl-belirticileri) veya C2433 (veri bildiriminde ' inline ' izin verilmez). TLI dosyası.

Bağımlılık hatalarını çözümlemek için, sistem üstbilgileri tarafından başka bir şekilde bağımlılık yorumlarının ne tür bir şekilde sağlanmadığını belirleyip, ardından bağımlı tür kitaplığının **#import** yönergesinden önce bir noktada **#import** yönergesi sağlayın.

### <a name="import-attributes"></a><a name="_predir_the_23import_directive_import_attributes"></a> #import öznitelikleri

**#import** , isteğe bağlı olarak bir veya daha fazla öznitelik içerebilir. Bu öznitelikler derleyiciye tür kitaplığı üstbilgilerinin içeriğini değiştirmesini söyler. Bir ters eğik çizgi ( **\\** ) simgesi, tek bir **#import** ifadesine ek satırlar eklemek için kullanılabilir. Örneğin:

```cpp
#import "test.lib" no_namespace \
   rename("OldName", "NewName")
```

Daha fazla bilgi için bkz. [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md).

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)\
[Derleyici COM desteği](../cpp/compiler-com-support.md)
