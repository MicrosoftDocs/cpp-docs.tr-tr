---
title: "coclass'ı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.coclass
dev_langs:
- C++
helpviewer_keywords:
- coclass attribute
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6bcae762c603f05ce11eae5d14eb2e182c666797
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="coclass"></a>coclass
COM arabirimi uygulayan bir COM nesnesi oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[coclass]  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Coclass** C++ öznitelik coclass yapı oluşturulan .idl dosyasına yerleştirir.  
  
 Ayrıca bir coclass'ı tanımlarken belirtebilirsiniz [UUID](../windows/uuid-cpp-attributes.md), [sürüm](../windows/version-cpp.md), [iş parçacığı oluşturma](../windows/threading-cpp.md), [vi_progid](../windows/vi-progid.md), ve [ProgID ](../windows/progid.md) öznitelikleri. Bunları herhangi biri belirtilmezse oluşturulur.  
  
 İki üst bilgi dosyaları sınıflarıyla içeriyorsa **coclass** özniteliğini ve bir GUID belirtmeyin derleyici aynı GUID için her iki sınıfları kullanır ve bir MIDL hatasına neden olur.  Bu nedenle, kullanmanız gereken `uuid` özniteliği kullandığınızda **coclass'ı**.  
  
 **ATL projeleri**  
  
 Bu öznitelik bir sınıf veya yapı tanımı ATL projesinde önündeki zaman onu:  
  
-   Kod veya nesne için otomatik kayıt desteklemek için veri yerleştirir.  
  
-   Kod veya nesne için bir COM sınıfı fabrikası desteklemek için veri yerleştirir.  
  
-   Kod veya uygulamak için veri yerleştirir **IUnknown** ve nesneyi bir COM creatable nesnesi yapın.  
  
 Özellikle, aşağıdaki temel sınıflar hedef nesnesine eklendi:  
  
-   [CComCoClass sınıfı](../atl/reference/ccomcoclass-class.md) nesne için varsayılan sınıf Fabrika ve toplama modeli sağlar.  
  
-   [İn uygulamasına sınıfı](../atl/reference/ccomobjectrootex-class.md) sahip bir şablon tarafından belirtilen iş parçacığı modeli sınıfı göre [iş parçacığı oluşturma](../windows/threading-cpp.md) özniteliği. Varsa **iş parçacığı oluşturma** özniteliği belirtilmezse, apartman modeli iş parçacığı oluşturma varsayılan değerdir.  
  
-   [IProvideClassInfo2Impl](../atl/reference/iprovideclassinfo2impl-class.md) eklenir [noncreatable](../windows/noncreatable.md) özniteliği için hedef nesne belirtilmedi.  
  
 Son olarak, katıştırılmış IDL kullanarak tanımlı değil tüm çift arabirim karşılık gelen ile değiştirilir [IDispatchImpl](../atl/reference/idispatchimpl-class.md) sınıfı. Çift arabirim katıştırılmış IDL içinde tanımlanmış olması durumunda, temel listesinde belirli arabirimi değiştirilmez.  
  
 **Coclass** özniteliği de kullanılabilir hale getirir aşağıdaki işlevleri durumunda veya eklenen kodu aracılığıyla `GetObjectCLSID`, statik yöntemi temel sınıf olarak `CComCoClass`:  
  
-   `UpdateRegistry`sınıf oluşturucuları hedef sınıfın kaydeder.  
  
-   `GetObjectCLSID`, kayıt için ilgili de kullanılabilir hedef sınıfın CLSID elde edilir.  
  
-   **GetObjectFriendlyName** varsayılan biçim dizesi döndürür "\<*hedef sınıf adını*> `Object`". Bu işlev zaten varsa, eklenmez. Bu işlev otomatik olarak oluşturulan daha yaşamanızı adını döndürmek için hedef sınıfına ekleyin.  
  
-   **GetProgID**, kayıt için ilgili, döndürür belirtilen dize ile [ProgID](../windows/progid.md) özniteliği.  
  
-   **GetVersionIndependentProgID** aynı işlevselliğe sahip **GetProgID**, ancak belirtilen dizeyi döndürür [vi_progid](../windows/vi-progid.md).  
  
 COM eşlemesi ilgili aşağıdaki değişiklikler için hedef sınıf oluşturulur:  
  
-   Hedef sınıf türetilen tüm arabirimler için girişleri ve tarafından belirtilen tüm girişleri ile COM eşlemesi eklenen [COM arabirimi giriş noktaları](../mfc/com-interface-entry-points.md) özniteliği ya da tarafından gerekli olanlar [toplamalar](../windows/aggregates.md) özniteliği.  
  
-   Bir [OBJECT_ENTRY_AUTO](../atl/reference/object-map-macros.md#object_entry_auto) makrosu COM eşlemeye eklenir.
  
 Sınıfı için .idl dosyasında oluşturulan coclass'ı adını sınıf olarak aynı ada sahip olacaktır.  Örneğin ve aşağıdaki örneğe başvuran CLSID_CMyClass coclass CMyClass, MIDL üretilen üstbilgi dosyası aracılığıyla bir istemci için sınıf kimliği erişmek için kullanın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösterir **coclass** özniteliği:  
  
```  
// cpp_attr_ref_coclass1.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface I {  
   HRESULT func();  
};  
  
[coclass, progid("MyCoClass.coclass.1"), vi_progid("MyCoClass.coclass"),   
appobject, uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")]  
class CMyClass : public I {};  
```  
  
 Aşağıdaki örnek, varsayılan uygulaması tarafından eklenen kod görünür bir işlevi geçersiz kılmak gösterilmiştir **coclass** özniteliği. Bkz: [/Fx](../build/reference/fx-merge-injected-code.md) eklenen kodu görüntüleme hakkında daha fazla bilgi. Tüm temel sınıflar veya için bir sınıf kullanma arabirimleri olabilir görünür eklenen kodu.   Ayrıca, bir sınıf eklenen kodu varsayılan olarak dahil edilir ve açıkça o sınıfın temel olarak, coclass için belirttiğiniz, öznitelik sağlayıcısı kodunuzda belirtilen formu kullanın.  
  
```  
// cpp_attr_ref_coclass2.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlwin.h>  
#include <atltypes.h>  
#include <atlctl.h>  
#include <atlhost.h>  
#include <atlplus.h>  
  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000000")]  
__interface bb {};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000001")]  
class CMyClass : public bb {  
public:  
   // by adding the definition of UpdateRegistry to your code,   
   // the function will not be included in the injected code  
   static HRESULT WINAPI UpdateRegistry(BOOL bRegister) {  
      // you can add to the default implementation  
      CRegistryVirtualMachine rvm;  
      HRESULT hr;  
      if (FAILED(hr = rvm.AddStandardReplacements()))  
         return hr;  
      rvm.AddReplacement(_T("FriendlyName"), GetObjectFriendlyName());  
      return rvm.VMUpdateRegistry(GetOpCodes(), GetOpcodeStringVals(),  
         GetOpcodeDWORDVals(), GetOpcodeBinaryVals(), bRegister);  
   }  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**,`struct`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [COM öznitelikleri](../windows/com-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [appobject](../windows/appobject.md)