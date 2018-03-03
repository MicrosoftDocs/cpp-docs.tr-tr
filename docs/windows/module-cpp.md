---
title: "Modül (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.module
dev_langs:
- C++
helpviewer_keywords:
- module attributes
ms.assetid: 02223b2a-62b5-4262-832f-564b1e11e58e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 75b41ea146096a60210918b5f21e7b6278e35001
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="module-c"></a>modül (C++)
Kitaplık blok .idl dosyasında tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ module (  
   type=dll,  
   name=string,  
   version=1.0,  
   uuid=uuid,  
   lcid=integer,  
   control=boolean,  
   helpstring=string,  
   helpstringdll=string,  
   helpfile=string,  
   helpcontext=integer,  
   helpstringcontext=integer,  
   hidden=boolean,  
   restricted=boolean,  
   custom=string,  
   resource_name=string,  
) ];  
```  
  
#### <a name="parameters"></a>Parametreler  
 ***tür*** (isteğe bağlı)  
 Aşağıdakilerden biri olabilir:  
  
-   **dll** işlevleri ve işlem içi COM sunucusu olarak çalışması ortaya çıkan DLL'i izin sınıfları ekler. Varsayılan değer budur.  
  
-   **exe** ekler işlevleri ve elde edilen izin sınıfları işleve işlem COM sunucusu dışı olarak çalıştırılabilir.  
  
-   **Hizmet** ekler işlevleri ve elde edilen izin sınıfları işleve bir NT hizmeti olarak çalıştırılabilir.  
  
-   **Belirtilmeyen** ekleme modül özniteliği ilgili ATL kodu devre dışı bırakır: ekleme ATL modül sınıfı, genel örnek _AtlModule ve giriş noktası işlevleri.  ATL kodu projedeki diğer öznitelikleri nedeniyle ekleme işlemi devre dışı bırakmaz.  
  
 ***ad*** (isteğe bağlı)  
 Kitaplık blok adı.  
  
 ***Sürüm*** (isteğe bağlı)  
 Kitaplık bloğuna atamak istediğiniz sürüm numarası. 1.0 varsayılan değerdir.  
  
 `uuid`  
 Kitaplık için benzersiz kimlik. Bu parametresini atlarsanız, kimliği kitaplık için otomatik olarak oluşturulur. Alınacak gerekebilir *UUID* tanımlayıcısını kullanarak yapabilirsiniz, kitaplık bloğunun **__uuidof (***libraryname***)**.  
  
 **lcid**  
 Yerelleştirme parametresi. Bkz: [LCID](http://msdn.microsoft.com/library/windows/desktop/aa367067) daha fazla bilgi için.  
  
 **Denetim** (isteğe bağlı)  
 Kitaplığı'nda, tüm coclass'ları denetimlerin olduğunu belirtir.  
  
 **helpstring**  
 Tür kitaplığı belirtir.  
  
 ***helpstringdll*** (isteğe bağlı)  
 Bir belge dize araması gerçekleştirmek için kullanılacak .dll dosyasının adını ayarlar. Bkz: [helpstringdll](http://msdn.microsoft.com/library/windows/desktop/aa366860) daha fazla bilgi için.  
  
 **HelpFile** (isteğe bağlı)  
 Tür kitaplığı için Yardım dosyasının adı.  
  
 **HelpContext** (isteğe bağlı)  
 Bu tür kitaplığı Yardım kimliği.  
  
 **helpstringcontext** (isteğe bağlı)  
 Bkz: [helpstringcontext](../windows/helpstringcontext.md) daha fazla bilgi için.  
  
 **Gizli** (isteğe bağlı)  
 Tüm Kitaplığı görüntülenmesini engeller. Bu kullanım denetimleri ile kullanılmak üzere tasarlanmıştır. Genişletilmiş özellikler denetimiyle sarmalar yeni bir tür kitaplığı oluşturmak için konaklar gerekir. Bkz: [gizli](http://msdn.microsoft.com/library/windows/desktop/aa366861) daha fazla bilgi için MIDL özniteliği.  
  
 **kısıtlı** (isteğe bağlı)  
 Kitaplık üyelerini rasgele çağrılamaz. Bkz: [kısıtlı](http://msdn.microsoft.com/library/windows/desktop/aa367157) daha fazla bilgi için MIDL özniteliği.  
  
 ***özel*** (isteğe bağlı)  
 Bir veya daha fazla öznitelik; Bu benzer [özel](../windows/custom-cpp.md) özniteliği. İlk parametre olarak `custom` öznitelik GUID'dir. Örneğin:  
  
```  
[module(custom={guid,1}, custom={guid1,2})]  
```  
  
 **resource_name**  
 Yürütülebilir dosya veya hizmet DLL uygulama Kimliğini kaydetmek için kullanılan .rgs dosya dize kaynak kimliği. Modül türü hizmeti olduğunda, bu bağımsız değişken hizmet adını içeren dize Kimliğini almak için de kullanılır.  
  
> [!NOTE]
>  .Rgs dosya ve hizmet adını içeren dize aynı sayısal değer içermelidir.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtmediğiniz sürece **kısıtlı** parametresi [emitidl](../windows/emitidl.md), **Modülü** C++ öznitelikleri kullanan herhangi bir programda gereklidir.  
  
 Bir kitaplık bloğu, oluşturulacak ek olarak **Modülü** özniteliği, kaynak kodu de kullanır [görüntüleme arabirimi](../windows/dispinterface.md), [çift](../windows/dual.md), [nesne](../windows/object-cpp.md), ya da anlaşılacağı bir öznitelik [coclass'ı](../windows/coclass.md).  
  
 Bir kitaplık blok .idl dosyasında izin verilir. En son parametre değerlerini uygulanan birden çok modül girişleri kaynak kodunda birleştirilir.  
  
 Bu öznitelik, ATL kullanan bir proje içinde kullanılıyorsa, öznitelik davranışını değiştirir. Yukarıdaki davranışa ek olarak, öznitelik da genel bir nesne ekler (adlı **_AtlModule**) doğru türde ve ek destek kodu. Öznitelik tek başına ise, doğru modülü türden türetilmiş bir sınıf ekler. Öznitelik bir sınıfa uygulandığında, doğru modül türünün bir temel sınıf ekler. Doğru türü değeri tarafından belirlenir `type` parametre:  
  
-   `type` = **dll**  
  
     [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) temel sınıf ve standart DLL girdi kullanılan bir COM sunucu için gereken noktaları. Bu giriş noktaları [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583), [DllRegisterServer](http://msdn.microsoft.com/library/windows/desktop/ms682162), [DllUnRegisterServer](http://msdn.microsoft.com/library/windows/desktop/ms691457), [DllCanUnloadNow](http://msdn.microsoft.com/library/windows/desktop/ms690368), ve [ DllGetClassObject](http://msdn.microsoft.com/library/windows/desktop/dd797891).  
  
-   `type` = **exe**  
  
     [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) temel sınıf ve standart yürütülebilir giriş noktası kullanılan [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559).  
  
-   `type` = **hizmeti**  
  
     [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) temel sınıf ve standart yürütülebilir giriş noktası kullanılan [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559).  
  
-   `type` = **belirtilmemiş**  
  
     ATL kodu modülü öznitelik ilişkili ekleme devre dışı bırakır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod oluşturulan .idl dosyasında kitaplığını bloğunu oluşturulacağını gösterir.  
  
```  
// cpp_attr_ref_module1.cpp  
// compile with: /LD  
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];  
```  
  
 Aşağıdaki kod, kendi uygulama kullanarak bir sonucu olarak eklendi kodda görüneceği bir işlevin sağlayabilirsiniz gösterir **Modülü**. Bkz: [/Fx](../build/reference/fx-merge-injected-code.md) eklenen kodu görüntüleme hakkında daha fazla bilgi. Tarafından eklenen işlevler biri geçersiz kılmak için **Modülü** özniteliği, uygulamanızı işlevinin içerir ve yapan bir sınıf olun **Modülü** o sınıfın özniteliğini uygulayın.  
  
```  
// cpp_attr_ref_module2.cpp  
// compile with: /LD /link /OPT:NOREF  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlwin.h>  
#include <atltypes.h>  
#include <atlctl.h>  
#include <atlhost.h>  
#include <atlplus.h>  
  
// no semicolon after attribute block  
[module(dll, name="MyLibrary", version="1.2", helpfile="MyHelpFile")]   
// module attribute now applies to this class  
class CMyClass {  
public:  
BOOL WINAPI DllMain(DWORD dwReason, LPVOID lpReserved) {  
   // add your own code here  
   return __super::DllMain(dwReason, lpReserved);  
   }  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Her yerden|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [Tek başına öznitelikler](../windows/stand-alone-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [usesgetlasterror](../windows/usesgetlasterror.md)   
 [Kitaplığı](http://msdn.microsoft.com/library/windows/desktop/aa367069)   
 [HelpContext](../windows/helpcontext.md)   
 [HelpString](../windows/helpstring.md)   
 [HelpFile](../windows/helpfile.md)   
 [Sürüm](../windows/version-cpp.md)   
