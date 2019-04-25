---
title: coclass'ı (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.coclass
helpviewer_keywords:
- coclass attribute
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
ms.openlocfilehash: e1f99a2780ab4f451533a3e797e473f60680c6ab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148295"
---
# <a name="coclass"></a>coclass

COM arabirimi uygulayan bir COM nesnesi oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
[coclass]
```

## <a name="remarks"></a>Açıklamalar

**Coclass'ı** C++ özniteliği oluşturulmuş bir .idl dosyasında bir coclass'ı yapısı yerleştirir.

Coclass'ı tanımlarken, ayrıca belirtebilirsiniz [UUID](uuid-cpp-attributes.md), [sürüm](version-cpp.md), [iş parçacığı](threading-cpp.md), [vi_progid](vi-progid.md), ve [program kimliği ](progid.md) öznitelikleri. Herhangi biri belirtilmezse oluşturulur.

İki üst bilgi dosyaları sınıflarıyla içeriyorsa **coclass'ı** özniteliğini ve bir GUID belirtmeyin derleyici aynı GUID için hem sınıflarını kullanır ve bir MIDL hatasına neden olur.  Bu nedenle, kullanmalısınız `uuid` özniteliğini kullandığınızda **coclass'ı**.

**ATL projeleri**

Bu öznitelik, bir sınıf veya yapı tanımı bir ATL projesinde önce geldiğinde bunu:

- Kod veya nesne için otomatik kayıt desteklemek için veri ekler.

- Kod veya COM sınıf üreteci nesne için desteklemek için veri ekler.

- Kod veya uygulamak için veri eklediği `IUnknown` ve nesne haline getiren bir oluşturulabilir COM nesnesi.

Özellikle, aşağıdaki temel sınıflar, hedef nesneye eklenir:

- [CComCoClass sınıfı](../../atl/reference/ccomcoclass-class.md) nesne için varsayılan sınıf üreteci ve toplama modelini sağlar.

- [CComObjectRootEx sınıfı](../../atl/reference/ccomobjectrootex-class.md) sahip bir şablon tarafından belirtilen iş parçacığı model sınıfı göre [iş parçacığı](threading-cpp.md) özniteliği. Varsa `threading` özniteliği belirtilmezse, apartman modeli iş parçacığı varsayılan değerdir.

- [Iprovideclassınfo2ımpl](../../atl/reference/iprovideclassinfo2impl-class.md) eklenir [noncreatable](noncreatable.md) özniteliği için hedef nesne belirtilmedi.

Son olarak, katıştırılmış IDL ile tanımlanmamış herhangi bir çift arabirim karşılık gelen ile değiştirilir [Idispatchımpl](../../atl/reference/idispatchimpl-class.md) sınıfı. Çift arabirim katıştırılmış IDL içinde tanımlıysa, özel arabirim temel listesinde değiştirilmez.

**Coclass'ı** özniteliği ayrıca aşağıdaki işlevleri kullanıma sunar eklenen kodu aracılığıyla ya da durumunda `GetObjectCLSID`, temel sınıfında statik bir yöntem olarak `CComCoClass`:

- `UpdateRegistry` hedef sınıfın sınıf üreteçlerini kaydeder.

- `GetObjectCLSID`, kayıt için ilgili de kullanılabilir hedef sınıfın CLSID elde edilir.

- `GetObjectFriendlyName` Varsayılan biçim dizesi döndürür "\<*hedef sınıf adı*> `Object`". Bu işlev zaten mevcutsa eklenmez. Bu işlev otomatik olarak oluşturulan olandan daha kolay adı döndürülecek hedef sınıfına ekleyin.

- `GetProgID`, belirtilen dizeyi döndürür, kayıt için ilgili [ProgID](progid.md) özniteliği.

- `GetVersionIndependentProgID` aynı işlevlere sahip `GetProgID`, ancak belirtilen dizeyi döndürür [vi_progid](vi-progid.md).

Hedef sınıf için COM haritaya ilgili aşağıdaki değişiklikler yapılır:

- COM eşlemesi girişleri tüm arabirimlerin hedef sınıf türetilir ve tarafından belirtilen tüm girişler eklenir [COM arabirimi giriş noktaları](../../mfc/com-interface-entry-points.md) özniteliği veya gerektirdiği [toplamalar](aggregates.md) özniteliği.

- Bir [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) makrosu, COM eşlemesine eklenir.

Oluşturulan sınıf için .idl dosyasındaki coclass adı, sınıfı aynı ada sahip.  Örneğin ve sınıf kimliği için bir coclass'ı erişmek için aşağıdaki örnek, söz konusu `CMyClass`, MIDL tarafından oluşturulan üstbilgi dosyası aracılığıyla bir istemci kullanın `CLSID_CMyClass`.

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanılacağını gösterir **coclass'ı** özniteliği:

```cpp
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

Aşağıdaki örnek, varsayılan uygulama tarafından eklenen kodda görüntülenen bir işlevin geçersiz kılmak gösterilir **coclass'ı** özniteliği. Bkz: [/Fx](../../build/reference/fx-merge-injected-code.md) eklenen kodu görüntüleme hakkında daha fazla bilgi. Tüm temel sınıflar veya bir sınıf için kullandığınız arabirimlerini olması görünür eklenen kodun. Ayrıca, bir sınıf, varsayılan olarak eklenen kodu bulunur ve açıkça bu sınıf bir temel olarak, coclass'ı için belirttiğiniz, öznitelik sağlayıcısı kodunuzda belirtilen formu kullanın.

```cpp
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
   // by adding the definition of UpdateRegistry to your code, // the function will not be included in the injected code
   static HRESULT WINAPI UpdateRegistry(BOOL bRegister) {
      // you can add to the default implementation
      CRegistryVirtualMachine rvm;
      HRESULT hr;
      if (FAILED(hr = rvm.AddStandardReplacements()))
         return hr;
      rvm.AddReplacement(_T("FriendlyName"), GetObjectFriendlyName());
      return rvm.VMUpdateRegistry(GetOpCodes(), GetOpcodeStringVals(),       GetOpcodeDWORDVals(), GetOpcodeBinaryVals(), bRegister);
   }
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|None|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[COM Öznitelikleri](com-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[appobject](appobject.md)