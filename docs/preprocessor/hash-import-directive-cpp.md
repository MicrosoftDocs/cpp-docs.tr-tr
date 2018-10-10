---
title: '#içeri aktarma yönergesi (C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#import'
dev_langs:
- C++
helpviewer_keywords:
- .tlh files
- '#import directive'
- import directive (#import)
- tlh files
- tlbid switch
- preprocessor, directives
- COM, type library header file
ms.assetid: 787d1112-e543-40d7-ab15-a63d43f4030a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 60397fea85e3fd121469ae4568dac18fa6b9ddb1
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890328"
---
# <a name="import-directive-c"></a>#import Yönergesi (C++)
**C++ özgü**  
  
Tür kitaplığından bilgileri birleştirmek için kullanılır. Tür kitaplığının içeriği çoğunlukla COM arabirimlerini açıklayan C++ sınıflarına dönüştürülür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#import "filename" [attributes]  
#import <filename> [attributes]  
```  
  
### <a name="parameters"></a>Parametreler  
*Dosya adı*  
İçe aktarılacak tür kitaplığını belirtir. *filename* aşağıdakilerden biri olabilir:  
  
- .Olb, .tlb veya .dll dosyası gibi bir tür kitaplığı içeren bir dosya adı. Anahtar sözcüğü **dosya:**, her dosya adının önüne gelebilir.  
  
- Progid tür kitaplığında bir denetimin. Anahtar sözcüğü **ProgID:**, her program kimliğinin önüne gelebilir. Örneğin:  
  
    ```  
    #import "progid:my.prog.id.1.5"  
    ```  
  
     Progid'ler hakkında daha fazla bilgi için bkz. [yerelleştirme kimliği ve sürüm numarasını belirtme](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber).  
  
     64-bit işletim sisteminde çapraz bir derleyici ile derleme yaparken, derleyicinin yalnızca 32 bit kayıt defteri kovanını olacağını unutmayın. Derleme ve 64 bit tür kitaplığını kaydetmek için yerel 64 bit derleyiciyi kullanmak isteyebilirsiniz.  
  
- Tür kitaplığının Kitaplık kimliği. Anahtar sözcüğü **libid:**, her kitaplık kimliğinin önüne gelebilir Örneğin:  
  
    ```  
    #import "libid:12341234-1234-1234-1234-123412341234" version("4.0") lcid("9")  
    ```  
  
     Sürüm veya lcid belirtmezseniz [kuralları](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber) uygulanan **ProgID:** de uygulanır **libid:**.  
  
- Yürütülebilir (.exe) dosya.  
  
- Tür kitaplığı kaynağı (.ocx gibi) içeren bir kitaplık (.dll) dosyası.  
  
- Bir tür kitaplığını kullanımda tutan bir bileşik belge.  
  
- Tarafından anlaşılabilir herhangi bir dosya biçiminde **LoadTypeLib** API.  
  
*Öznitelikleri*  
Bir veya daha fazla [#import öznitelikleri](#_predir_the_23import_directive_import_attributes). Ayrı öznitelikleri boşluk veya virgül ile. Örneğin:  
  
```  
#import "..\drawctl\drawctl.tlb" no_namespace, raw_interfaces_only  
```  
  
veya  
  
```  
#import "..\drawctl\drawctl.tlb" no_namespace raw_interfaces_only  
```  
  
## <a name="remarks"></a>Açıklamalar  
  
##  <a name="_predir_the_23import_directive_searchorderforfilename"></a> Dosya adı için arama sırası  

*filename* isteğe bağlı olarak bir dizin belirtimi tarafından öncesinde. Dosya adı, var olan bir dosya adı olmalıdır. İki sözdizimi formu arasındaki farkı yolu belirtilmediğinde önişlemcinin, önişlemci tür kitaplığı dosyalarını arama sırasıdır.  
  
|Söz dizimi biçimi|Eylem|  
|-----------------|------------|  
|Tırnak işareti|Önişlemciye tür kitaplığı dosyalarını içeren dosya dizininde bulunan ilk arayın bildirir **#import** deyimi ve ardından dahil tüm dosyaların dizinlerine (`#include`) Bu dosya. Önişlemci sonra aşağıda gösterilen yolları boyunca arar.|  
|Açılı ayraç biçimi|Önişlemciye aşağıdaki yollarla birlikte tür kitaplığı dosyalarını araması talimatı verir:<br /><br /> 1.  `PATH` Ortam değişkeni yol listesi<br />2.  `LIB` Ortam değişkeni yol listesi<br />3.  /I tarafından belirtilen yol (ek içeren dizinler) derleyici seçeneği, onu derleyici, başka bir kitaplık ile başvurulan bir tür kitaplığı arıyor dışında [no_registry](../preprocessor/no-registry.md) özniteliği.|  
  
##  <a name="_predir_the_23import_directive_specifyingthelocalizationidandversionnumber"></a> Yerelleştirme kimliği ve sürüm numarasını belirtme  

Bir progid belirttiğinizde, progid, yerelleştirme kimliği ve sürüm numarasını da belirtebilirsiniz. Örneğin:  
  
```  
#import "progid:my.prog.id" lcid("0") version("4.0)  
```  
  
Bir yerelleştirme kimliği belirtmezseniz, bir program kimliği aşağıdaki kurallara göre seçilir:  
  
- Yalnızca bir yerelleştirme kimliği varsa, bunu kullanılır.  
  
- Birden fazla yerelleştirme kimliği varsa sürüm numarası 0, 9 veya 409 olan kullanılır.  
  
- Sonuncu varsa birden fazla yerelleştirme kimliği ve bunların hiçbiri 0, 9 veya 409 olan kullanılır.  
  
- Bir sürüm numarası belirtmezseniz en yeni sürümü kullanılır.  
  
##  <a name="_predir_the_23import_directive_header_files_created_by_import"></a> İçeri aktarma tarafından oluşturulan üstbilgi dosyaları  

**#import** C++ kaynak kodunda tür kitaplığı içeriklerini yeniden iki üstbilgi dosyası oluşturur. Birincil üstbilgi dosyası Microsoft arabirim tanımı dili (MIDL) derleyici tarafından ancak derleyicinin ürettiği ek kod ve veri üreten benzer. [Birincil üstbilgi dosyası](#_predir_the_primary_type_library_header_file) tür kitaplığı aynı temel ada sahip yanı sıra. TLH uzantısı. İkincil üstbilgi dosyası tür kitaplığı olarak aynı temel ada sahip bir. TLI uzantısı. Derleyici tarafından oluşturulan üye işlevlerin uygulanmasını içerir ve dahildir (`#include`) birincil üstbilgi dosyası içinde.  
  
Byref parametrelerini kullanan bir kaynak görüntüleme arabirimi özelliği içe aktarılıyorsa, #import __declspec oluşturmaz ([özelliği](../cpp/property-cpp.md)) işlev bildirimi.  
  
Her iki başlık dosyası /Fo (nesne dosyasını Adlandır) seçeneği tarafından belirtilen çıktı dizinine yerleştirilir. Bunlar ardından okuyun ve varsa birincil üstbilgi dosyası tarafından adlandırılmış gibi derleyici tarafından derlenmiş bir `#include` yönergesi.  
  
Aşağıdaki derleyici iyileştirmeleri gelir **#import** yönergesi:  
  
- Üstbilgi dosyası oluşturulduğunda, tür kitaplığı ile aynı zaman damgası verilir.  
  
- Zaman **#import** olan işlendiğinde derleyici ilk olarak başlığın mevcut ve güncel olmadığını denetler. Yanıt Evet ise, yeniden oluşturulması gerekmez.  
  
**#İmport** yönergesi ayrıca en az yeniden katıldığı ve bir ön derlenmiş üstbilgi dosyasına yerleştirilebilir. Bkz: [önceden derlenmiş üst bilgi dosyaları oluşturma](../build/reference/creating-precompiled-header-files.md) daha fazla bilgi için.  
  
###  <a name="_predir_the_primary_type_library_header_file"></a> Birincil tür kitaplığı üstbilgi dosyası  
Birincil tür kitaplığı üstbilgi dosyası yedi bölümden oluşur:  
  
- Demirbaş: açıklamalardan oluşur `#include` COMDEF bildirimi. (Bu üst bilgisinde kullanılan bazı standart makroları tanımlar) H ve diğer çeşitli Kurulum bilgilerinden.  
  
- İleri başvurular ve tür tanımları: gibi yapı bildirimlerinden oluşur `struct IMyInterface` ve tür tanımları.  
  
- Akıllı işaretçi bildirimleri: Şablon sınıfı `_com_ptr_t` , arabirim işaretçilerini kapsayan ve çağırma ihtiyacını ortadan kaldıran bir akıllı işaretçi uygulamasıdır `AddRef`, `Release`, `QueryInterface` işlevleri. Ayrıca, onu gizliyor `CoCreateInstance` yeni bir COM nesnesi oluşturulurken çağırın. Bu bölümde makro deyimini kullanan `_COM_SMARTPTR_TYPEDEF` şablon özelleştirmeleri için COM arabirimlerinin TypeDef kurmaya [_com_ptr_t](../cpp/com-ptr-t-class.md) Şablon sınıfı. Örneğin, arabirimin `IMyInterface`,. TLH dosyasını içerecek:  
  
    ```  
    _COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
    ```  
  
     hangi derleyici şu şekilde genişletir:  
  
    ```  
    typedef _com_ptr_t<_com_IIID<IMyInterface, __uuidof(IMyInterface)> > IMyInterfacePtr;  
    ```  
  
     Tür `IMyInterfacePtr` yerine ham arabirim işaretçisi kullanılabilir `IMyInterface*`. Sonuç olarak, çeşitli çağırmaya gerek yoktur `IUnknown` üye işlevleri  
  
- Typeinfo bildirimleri: sınıf tanımlarını ve diğer öğeleri tarafından döndürülen bireysel typeinfo öğelerini ifşa eden, öncelikle oluşur `ITypeLib:GetTypeInfo`. Bu bölümde tür kitaplığındaki her typeinfo üst bilgisinde üstbilgiye yansıtılır `TYPEKIND` bilgileri.  
  
- İsteğe bağlı eski tip GUID tanımı: adlandırılmış GUID sabitlerinin başlatmalarını içerir. Formun adları bunlar `CLSID_CoClass` ve `IID_Interface`, MIDL derleyici tarafından oluşturulan benzer.  
  
- `#include` İkinci tür kitaplık üstbilgisi için bildirimi.  
  
- Altbilgi Demirbaş: şu anda içerir `#pragma pack(pop)`.  
  
Başlık Demirbaş ve altbilgi Demirbaş, hariç tüm bölümleri tarafından belirlenen adıyla bir ad alanı içine alınan `library` özgün IDL dosyasındaki deyimi. Ad alanı adı ile açık bir nitelik olarak ya da aşağıdaki bildirimi dahil olmak üzere tür kitaplığı başlığındaki adları kullanabilirsiniz:  
  
```  
using namespace MyLib;  
```  
  
hemen sonra **#import** kaynak kodunda deyimi.  
  
Ad alanı kullanılarak gizlenebilir [no_namespace](#_predir_no_namespace) özniteliği **#import** yönergesi. Ancak, ad alanının gizlenmesi ad çakışmalarına neden. Ad alanı olarak da adlandırılabilir [rename_namespace](#_predir_rename_namespace) özniteliği.  
  
Derleyici o anda işlediği tür kitaplığının gerektirdiği her tür kitaplığı bağımlılığının tam yolunu sağlar. Yol, yorumlar, biçiminde tür kitaplığı üstbilgisine yazılır (. TLH) derleyicinin işlenen her tür kitaplığı için oluşturur.  
  
Bir tür kitaplığı diğer tür kitaplıklarında tanımlanan türlere başvuru içeriyorsa, sonra. TLH dosyası aşağıdaki sıralamada açıklamaları şunları içerir:  
  
```  
//  
// Cross-referenced type libraries:  
//  
//  #import "c:\path\typelib0.tlb"  
//  
```  
  
Gerçek dosya adı **#import** açıklama tam yoludur çapraz başvurulan tür kitaplığının kayıt defterinde saklanan şekilde. Eksik tür tanımlarından kaynaklanan hatalarla karşılaşırsanız, Yorumlar başındaki denetleyin. TLH hangi bağımlı tür kitaplıklarının görmek için önce içe aktarılması gerekir. Büyük olasılıkla hatalardır söz dizimi hatalarını (örneğin, C2143, C2146, C2321), C2501 (eksik belirticileri), veya C2433 ('veri bildiriminde izin verilmeyen inline') derleme sırasında. TLI dosyası.  
  
Bağımlılık açıklamaları aksi için sistem üstbilgileri tarafından sağlanmayan ve ardından sağlayan belirlemelisiniz bir **#import** önce belirli bir noktada yönerge **#import** bağımlı öğenin yönergesi hataları gidermek için Tür Kitaplığı'nı tıklatın.  

##  <a name="_predir_the_23import_directive_import_attributes"></a> #import öznitelikleri

**#import** isteğe bağlı olarak bir veya daha fazla öznitelik içerebilir. Bu öznitelikler, derleyiciye tür kitaplığı başlıklarının içeriğini değiştirmek söyleyin. Ters eğik çizgi (**\\**) sembolü, tek bir ek satırlar eklemek için kullanılabilir **#import** deyimi. Örneğin:  
  
```  
#import "test.lib" no_namespace \  
   rename("OldName", "NewName")  
```  
  
Daha fazla bilgi için [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md).  
  
**END C++ özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)<br/>
[Derleyici COM Desteği](../cpp/compiler-com-support.md)