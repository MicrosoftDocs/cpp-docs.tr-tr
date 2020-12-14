---
description: 'Daha fazla bilgi edinin: coclass'
title: coclass (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.coclass
helpviewer_keywords:
- coclass attribute
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
ms.openlocfilehash: 9ff2198807407a7dfc56649ed80cb1fa2bafc17c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247377"
---
# <a name="coclass"></a>coclass

COM arabirimini uygulayabilen bir COM nesnesi oluşturur.

## <a name="syntax"></a>Syntax

```cpp
[coclass]
```

## <a name="remarks"></a>Açıklamalar

**Coclass** C++ özniteliği, oluşturulan. IDL dosyasına bir coclass yapısı koyar.

Bir coclass tanımlarken, [UUID](uuid-cpp-attributes.md), [Sürüm](version-cpp.md), [iş parçacığı](threading-cpp.md), [vi_progid](vi-progid.md)ve [ProgID](progid.md) özniteliklerini de belirtebilirsiniz. Bunlardan biri belirtilmediyse, oluşturulur.

İki üst bilgi dosyası, **coclass** özniteliğiyle sınıflar içeriyorsa ve bir GUID belirtmezseniz, derleyici her iki sınıf için de aynı GUID 'i kullanır ve bu, MIDL hatasına neden olur.  Bu nedenle, `uuid` **coclass** kullandığınızda özniteliğini kullanmanız gerekir.

**ATL projeleri**

Bu öznitelik, ATL projesindeki bir sınıf veya yapı tanımından önce olduğunda:

- Nesne için otomatik kaydı desteklemeye yönelik kodu veya verileri çıkartır.

- Nesne için bir COM sınıfı fabrikasını desteklemek üzere kodu veya verileri çıkartır.

- Uygulamak `IUnknown` ve nesneyi BIR com-creatable nesnesi haline getirmek için kod veya veri çıkartır.

Özellikle, aşağıdaki temel sınıflar hedef nesnesine eklenir:

- [CComCoClass sınıfı](../../atl/reference/ccomcoclass-class.md) , nesne için varsayılan sınıf fabrikası ve toplama modelini sağlar.

- [CComObjectRootEx sınıfının](../../atl/reference/ccomobjectrootex-class.md) , [Threading](threading-cpp.md) özniteliği tarafından belirtilen iş parçacığı modeli sınıfına dayalı bir şablonu vardır. `threading`Öznitelik belirtilmemişse, varsayılan iş parçacığı modeli Apartment olur.

- [IProvideClassInfo2Impl](../../atl/reference/iprovideclassinfo2impl-class.md) , hedef nesne için [noncreatable](noncreatable.md) özniteliği belirtilmemişse eklenir.

Son olarak, katıştırılmış IDL kullanılarak tanımlanmayan herhangi bir ikili arabirim, karşılık gelen [IDispatchImpl](../../atl/reference/idispatchimpl-class.md) sınıfıyla değiştirilmiştir. Dual Interface katıştırılmış IDL içinde tanımlıysa, temel listedeki belirli arabirim değiştirilmez.

**Coclass** özniteliği Ayrıca aşağıdaki işlevleri, eklenen kod ile veya durumunda `GetObjectCLSID` temel sınıfta statik bir yöntem olarak kullanılabilir hale getirir `CComCoClass` :

- `UpdateRegistry` Hedef sınıfın sınıf fabrikalarını kaydeder.

- `GetObjectCLSID`kaydıyla ilgili olan, hedef sınıfın CLSID 'sini elde etmek için de kullanılabilir.

- `GetObjectFriendlyName` Varsayılan olarak "" biçiminde bir dize döndürür \<*target class name*> `Object` . Bu işlev zaten mevcutsa, eklenmez. Otomatik olarak üretilenden daha kolay bir ad döndürmek için bu işlevi Target sınıfına ekleyin.

- `GetProgID`kaydıyla ilgili olan, [ProgID](progid.md) özniteliğiyle belirtilen dizeyi döndürür.

- `GetVersionIndependentProgID` , ile aynı işlevselliğe sahiptir `GetProgID` , ancak [vi_progid](vi-progid.md)belirtilen dizeyi döndürür.

COM eşlemesiyle ilgili olan aşağıdaki değişiklikler hedef sınıfa yapılır:

- Hedef sınıfın türediği tüm arabirimlerin ve [com arabirimi giriş noktaları](../../mfc/com-interface-entry-points.md) özniteliği tarafından belirtilen veya [toplamalar](aggregates.md) özniteliği tarafından istenen tüm GIRDILERDEN oluşan girişlerle bir com eşlemesi eklenir.

- COM haritasına bir [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) makrosu eklenir.

Sınıfı için. IDL dosyasında oluşturulan coclass 'ın adı sınıfla aynı ada sahip olacaktır.  Örneğin, ve bir coclass 'ın sınıf KIMLIĞINE erişmek için, `CMyClass` MIDL tarafından oluşturulan üstbilgi dosyası aracılığıyla bir istemcide, kullanın `CLSID_CMyClass` .

## <a name="example"></a>Örnek

Aşağıdaki kod, **coclass** özniteliğinin nasıl kullanılacağını gösterir:

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

Aşağıdaki örnek, **coclass** özniteliği tarafından eklenen kodda görüntülenen bir işlevin varsayılan uygulamasının nasıl geçersiz kılınacağını göstermektedir. Eklenen kodu görüntüleme hakkında daha fazla bilgi için bkz. [/FX](../../build/reference/fx-merge-injected-code.md) . Bir sınıf için kullandığınız tüm temel sınıflar veya arabirimler eklenen kodda görüntülenir. Ayrıca, bir sınıf eklenen kodda varsayılan olarak dahil edilir ve bu sınıfı doğrudan coclass 'niz için bir temel olarak belirtirseniz, öznitelik sağlayıcısı kodunuzda belirtilen formu kullanır.

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`**|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[COM öznitelikleri](com-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[appobject](appobject.md)
