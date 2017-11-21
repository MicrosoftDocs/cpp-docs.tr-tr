---
title: "#<a name=\"import-directive-c--microsoft-docs\"></a>Yönergesi (C++) alma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '#import'
dev_langs: C++
helpviewer_keywords:
- .tlh files
- '#import directive'
- import directive (#import)
- tlh files
- tlbid switch
- preprocessor, directives
- COM, type library header file
ms.assetid: 787d1112-e543-40d7-ab15-a63d43f4030a
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 797ef6e17f1681e0e44af2f131e5b324a607297d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="import-directive-c"></a>#import Yönergesi (C++)
**C++ özel**  
  
 Tür kitaplığından bilgileri birleştirmek için kullanılır. Tür kitaplığı içeriğini çoğunlukla COM arabirimleri açıklayan C++ sınıfları dönüştürülür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#import "filename" [attributes]  
#import <filename> [attributes]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Dosya adı*  
 İçeri aktarmak için tür kitaplığı belirtir. `filename`aşağıdakilerden biri olabilir:  
  
-   Bir .olb, .tlb veya .dll dosyası gibi bir tür kitaplığı içeren bir dosya adı. Anahtar sözcüğü **dosya:**, her dosya koyun.  
  
-   ProgID bir tür kitaplığı denetiminde. Anahtar sözcüğü **ProgID:**, her ProgID koyun. Örneğin:  
  
    ```  
    #import "progid:my.prog.id.1.5"  
    ```  
  
     ProgID hakkında daha fazla bilgi için bkz: [yerelleştirme kimliği ve sürüm numarasını belirtme](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber).  
  
     Bir 64-bit işletim sisteminde çapraz derleyici ile derleme yapılırken Derleyici yalnızca 32-bit kayıt defteri kovanı okuyabilir olması gerektiğini unutmayın. Yerel 64 bit derleyici oluşturmak ve 64-bit tür kitaplığının kaydı için kullanmak isteyebilirsiniz.  
  
-   Tür kitaplığı kitaplık kimliği. Anahtar sözcüğü **kitaplık kimliği:**, her kitaplık kimliği koyun Örneğin:  
  
    ```  
    #import "libid:12341234-1234-1234-1234-123412341234" version("4.0") lcid("9")  
    ```  
  
     Sürüm veya LCID, belirtmezseniz [kuralları](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber) için uygulanan **ProgID:** için de geçerli **kitaplık kimliği:**.  
  
-   Bir yürütülebilir dosyanın (.exe) dosyası.  
  
-   Tür kitaplığı kaynağı (örneğin, .ocx) içeren bir kitaplık (.dll) dosyası.  
  
-   Tür kitaplığı bulunduran bir bileşik belge.  
  
-   Tarafından anlaşılan herhangi bir dosya biçiminde **LoadTypeLib** API.  
  
 `attributes`  
 Bir veya daha fazla [#import öznitelikleri](#_predir_the_23import_directive_import_attributes). Bir boşluk veya virgülle ayrı özniteliklerle. Örneğin:  
  
```  
#import "..\drawctl\drawctl.tlb" no_namespace, raw_interfaces_only  
```  
  
 veya  
  
```  
#import "..\drawctl\drawctl.tlb" no_namespace raw_interfaces_only  
```  
  
## <a name="remarks"></a>Açıklamalar  
  
##  <a name="_predir_the_23import_directive_searchorderforfilename"></a>Dosya adı için arama sırası  
 *filename* isteğe bağlı olarak bir dizin belirtimine göre öncesinde. Dosya adı, varolan bir dosyanın adı olmalıdır. Yolun eksik olarak belirtildiğinde önişlemci için tür kitaplığı dosyaları, arama sırasını iki sözdizimi arasındaki farktır.  
  
|Sözdizimi formu|Eylem|  
|-----------------|------------|  
|Tırnak işaretli formu|Tür kitaplığı dosyaları içeren dosyayı dizinin ilk olarak aramak için önişlemci bildirir `#import` deyimi ve ardından dahil hangi dosyaların dizinleri (`#include`) Bu dosya. Önişlemci sonra aşağıda gösterilen yolları boyunca arar.|  
|Açılı ayraç formu|Tür kitaplığı dosya aşağıdaki yollardan boyunca aramak için önişlemci bildirir:<br /><br /> 1.  **Yolu** ortam değişkeni yol listesi<br />2.  **LIB** ortam değişkeni yol listesi<br />3.  /I tarafından belirtilen yol (ek içeren dizinler) derleyici seçeneği, onu derleyici ile başka bir tür kitaplığından başvuruldu bir tür kitaplığı aramada dışında [no_registry](../preprocessor/no-registry.md) özniteliği.|  
  
##  <a name="_predir_the_23import_directive_specifyingthelocalizationidandversionnumber"></a>Yerelleştirme kimliği ve sürüm numarasını belirtme  
 Bir ProgID belirttiğinizde, yerelleştirme kimliği ve sürüm numarasını ProgID de belirtebilirsiniz. Örneğin:  
  
```  
#import "progid:my.prog.id" lcid("0") version("4.0)  
```  
  
 Yerelleştirme kimliği belirtmezseniz, bir ProgID aşağıdaki kurallara göre seçilir:  
  
-   Yalnızca bir yerelleştirme kimliği bir kullanılır.  
  
-   Birden fazla yerelleştirme kimliği birinci sürüm numarası 0, 9 ya da 409 ile kullanılır.  
  
-   Birden fazla yerelleştirme kimliği yoktur ve bunların hiçbiri 0, 9 ya da 409 sonuncu kullanılır.  
  
-   Bir sürüm numarası belirtmezseniz, en son sürümü kullanılır.  
  
##  <a name="_predir_the_23import_directive_header_files_created_by_import"></a>Alma işlemi tarafından oluşturulan üstbilgi dosyaları  
 `#import`C++ kaynak kodu tür kitaplığı içeriğini yeniden iki üst bilgi dosyaları oluşturur. Birincil üst bilgi dosyasını Microsoft arabirimi tanım dili (MIDL) derleyici, ancak ek derleyici tarafından üretilen kod ve veri üreten benzer. [Birincil üstbilgi dosyası](#_predir_the_primary_type_library_header_file) tür kitaplığı aynı taban adına sahip artı bir. TLH uzantısı. İkincil üstbilgi dosyası aynı temel tür kitaplığı ile adda bir. TLI uzantısı. Derleyicinin ürettiği üye işlevleri için uygulamaları içerir ve yer alır (`#include`) birincil üstbilgi dosyasında.  
  
 Byref parametreleri kullanan bir görüntüleme arabirimi özellik alma işlemi, #import __declspec oluşturmaz ([özelliği](../cpp/property-cpp.md)) deyimi işlev için.  
  
 Her iki üst bilgi dosyaları /Fo (nesne dosya adı) seçeneği tarafından belirtilen çıktı dizinine yerleştirilir. Bunlar ardından okuma ve birincil üst bilgi dosyasını tarafından adlandırılan sanki derleyicisi tarafından derlenen bir `#include` yönergesi.  
  
 Aşağıdaki derleyici iyileştirmelerini gelir `#import` yönergesi:  
  
-   Üstbilgi dosyası oluşturduğunuzda, tür kitaplığı olarak aynı zaman damgası verilir.  
  
-   Zaman `#import` olduğundan işlenemiyor, derleyici ilk üstbilgi var ve güncel olup olmadığını denetler. Yanıt Evet ise, onu yeniden oluşturulması gerekmez.  
  
 `#import` Yönergesi de içinde en az yeniden katılır ve önceden derlenmiş üstbilgi dosyasında yerleştirilebilir. Bkz: [önceden derlenmiş üst bilgi dosyaları oluşturma](../build/reference/creating-precompiled-header-files.md) daha fazla bilgi için.  
  
###  <a name="_predir_the_primary_type_library_header_file"></a>Birincil tür kitaplığı üstbilgi dosyası  
 Birincil tür kitaplığı üstbilgi dosyası yedi bölümden oluşur:  
  
-   Ortak başlık: Açıklamalar, içeren `#include` COMDEF bildirimi. (Bu, kullanılan bazı standart makrolar üstbilgisinde tanımlayan) H ve diğer çeşitli kurulum bilgileri.  
  
-   İletme başvuruları ve tür tanımları: yapısı bildirimlerini gibi oluşuyorsa `struct IMyInterface` ve tür tanımları.  
  
-   İşaretçi bildirimleri akıllı: Şablon sınıfı `_com_ptr_t` arabirim işaretçileri yalıtır ve çağrılacak ihtiyacını ortadan kaldıran bir akıllı işaretçi uygulaması `AddRef`, **sürüm**, `QueryInterface` işlevleri. Ayrıca, gizler `CoCreateInstance` yeni bir COM nesnesi oluşturmada çağırın. Bu bölümde makrosu deyimini kullanan **_COM_SMARTPTR_TYPEDEF** COM arabirimi, şablon özelleştirmeleri olması için tür tanımları oluşturmak için [_com_ptr_t](../cpp/com-ptr-t-class.md) Şablon sınıfı. Örneğin, arabirimin **IMyInterface**,. TLH dosya içerir:  
  
    ```  
    _COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
    ```  
  
     hangi derleyici şekilde genişletir:  
  
    ```  
    typedef _com_ptr_t<_com_IIID<IMyInterface, __uuidof(IMyInterface)> > IMyInterfacePtr;  
    ```  
  
     Tür `IMyInterfacePtr` yerine ham arabirim işaretçisi kullanılabilir `IMyInterface*`. Sonuç olarak, çeşitli çağırmak için gerek yoktur **IUnknown** üye işlevleri  
  
-   TypeInfo bildirimleri: sınıf tanımlarını ve diğer öğeleri tarafından döndürülen tek tek TypeInfo öğeleri gösterme öncelikle oluşan **ITypeLib:GetTypeInfo**. Bu bölümde, bağımlı bir form üstbilgisinde her TypeInfo tür kitaplığından yansıtılır `TYPEKIND` bilgi.  
  
-   İsteğe bağlı eski Tarz GUID tanımı: adlandırılmış GUID sabitleri oluşturucusundaki içerir. Bu form adlarıdır **CLSID_CoClass** ve **IID_Interface**, MIDL derleyici tarafından üretilen benzer.  
  
-   `#include`İkincil tür kitaplığı üstbilgi bildirimi.  
  
-   Altbilgi Demirbaş: şu anda içeren `#pragma pack(pop)`.  
  
 Başlık Demirbaş ve altbilgi Demirbaş bölümünde, dışındaki tüm bölümleri tarafından belirtilen adıyla bir ad alanındaki iliştirilir **Kitaplığı** özgün IDL dosyasında deyimi. Tür kitaplığı üstbilgi adlarından ad alanı adına sahip bir açık nitelik tarafından ya da aşağıdaki bildirimi dahil olmak üzere kullanabilirsiniz:  
  
```  
using namespace MyLib;  
```  
  
 hemen sonra `#import` kaynak kodunu deyiminde.  
  
 Ad alanı kullanılarak gizlenebilir [no_namespace](#_predir_no_namespace) özniteliği `#import` yönergesi. Ancak, ad alanı gizleme ad çakışmalarına neden olabilir. Ad alanı olarak da adlandırılabilir [rename_namespace](#_predir_rename_namespace) özniteliği.  
  
 Derleyici o anda işlenen türü kitaplığı tarafından gerekli herhangi bir tür kitaplığı bağımlılığı tam yolunu sağlar. Yol, Yorumlar formunda tür kitaplığı üstbilgisine yazılır (. TLH) derleyici her işlenen tür kitaplığı oluşturur.  
  
 Tür kitaplığı diğer tür kitaplıkları tanımlanan türlere başvurular içeriyorsa sonra. TLH dosya yorumlar aşağıdaki sıralama içerir:  
  
```  
//  
// Cross-referenced type libraries:  
//  
//  #import "c:\path\typelib0.tlb"  
//  
```  
  
 Gerçek dosya adını `#import` açıklamadır Çapraz referanslı tür kitaplığı tam yolunu kayıt defterinde saklandığı şekilde. Tür tanımları eksik nedeniyle hatalarını karşılaşırsanız, Yorumlar başındaki denetleyin. Hangi bağımlı tür kitaplıklarının görmek için TLH önce içe aktarılması gerekir. Büyük olasılıkla hatalardır sözdizimi hataları (örneğin, C2143, C2146, C2321) C2501 (decl tanımlayıcıları eksik) veya C2433 ('veri belirtimine izin verilmeyen inline') derleme sırasında. TLI dosyası.  
  
 Hangi bağımlılık açıklamaları aksi için sistem üstbilgileri tarafından sağlanmayan ve ardından sağlayın belirlemelisiniz bir `#import` önce belirli bir noktada yönerge `#import` hataları gidermek için bağımlı tür kitaplığı yönergesi.  
  
 Daha fazla bilgi için Bilgi Bankası makalesine bakın "#import sarmalayıcı yöntemleri neden erişim ihlali" (Q242527) veya "kullandığınızda derleyici hataları XML ile #import" (Q269194). MSDN Kitaplığı medyada veya Bilgi Bankası makaleleri bulabilirsiniz [Microsoft Support](https://support.microsoft.com/).  
  
##  <a name="_predir_the_23import_directive_import_attributes"></a>#import öznitelikleri  
 `#import`İsteğe bağlı olarak bir veya daha fazla öznitelik ekleyebilirsiniz. Bu öznitelikler tür kitaplığı üstbilgi içeriğini değiştirmek için derleyici söyleyin. Ters eğik çizgi (**\\**) simgesi, tek bir ek satır eklemek için kullanılabilir `#import` deyimi. Örneğin:  
  
```  
#import "test.lib" no_namespace \  
   rename("OldName", "NewName")  
```  
  
 Daha fazla bilgi için bkz: [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md).  
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)   
 [Derleyici COM desteği](../cpp/compiler-com-support.md)
