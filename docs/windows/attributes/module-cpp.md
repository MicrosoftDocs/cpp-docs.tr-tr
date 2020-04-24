---
title: modül (C++ COM Özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.module
helpviewer_keywords:
- module attributes
ms.assetid: 02223b2a-62b5-4262-832f-564b1e11e58e
ms.openlocfilehash: 9d4f9e23aaf182e28930ba3a4462b07533ba9015
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754383"
---
# <a name="module-c"></a>modül (C++)

.idl dosyasındaki kitaplık bloğunu tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ module (type=dll, name=string, version=1.0, uuid=uuid, lcid=integer, control=boolean, helpstring=string, helpstringdll=string, helpfile=string, helpcontext=integer, helpstringcontext=integer, hidden=boolean, restricted=boolean, custom=string, resource_name=string,) ];
```

### <a name="parameters"></a>Parametreler

*Türü*<br/>
(İsteğe bağlı) Aşağıdakilerden biri olabilir:

- `dll`Ortaya çıkan DLL'nin işlem içi bir COM sunucusu olarak çalışmasına olanak tanıyan işlevler ve sınıflar ekler. Varsayılan değer budur.

- `exe`Ortaya çıkan yürütülebilir işlemin dışında bir COM sunucusu olarak çalışmasına izin veren işlevler ve sınıflar ekler.

- `service`Ortaya çıkan yürütülebilir bir NT hizmeti olarak çalışmasına izin veren işlevler ve sınıflar ekler.

- `unspecified`Modül özniteliği ile ilgili ATL kodunun enjeksiyonunu devre dışı kılabilir: ATL Modülü sınıfının enjeksiyonu, küresel örnek _AtlModule ve giriş noktası fonksiyonları. Projedeki diğer öznitelikler nedeniyle ATL kodunun enjeksiyonu devre dışı etmez.

*Adı*<br/>
(İsteğe bağlı) Kütüphane bloğunun adı.

*Sürüm*<br/>
(İsteğe bağlı) Kitaplık bloğuna atamak istediğiniz sürüm numarası. Varsayılan değer 1.0'dır.

*uuid*<br/>
Kütüphane için benzersiz kimlik. Bu parametreyi atlarsanız, kitaplık için otomatik olarak bir kimlik oluşturulur. Kitaplık bloğunuzun *uuid'ini* almanız gerekebilir, bunu tanımlayıcı __uuidof *(libraryname)* **)** kullanarak yapabilirsiniz. **__uuidof(**

*lcid*<br/>
Yerelleştirme parametresi. Daha fazla bilgi için [lcid](/windows/win32/Midl/lcid) bakın.

*Denetim*<br/>
(İsteğe bağlı) Kitaplıktaki tüm ortak sınıfların denetimler olduğunu belirtir.

*helpstring*<br/>
Tür kitaplığını belirtir.

*helpstringdll*<br/>
(İsteğe bağlı) Belge dizesini aramak için kullanılacak .dll dosyasının adını ayarlar. Daha fazla bilgi için [helpstringdll'e](/windows/win32/Midl/helpstringdll) bakın.

*helpfile*<br/>
(İsteğe bağlı) Tür kitaplığı için **Yardım** dosyasının adı.

*helpcontext*<br/>
(İsteğe bağlı) Bu tür kitaplığı için **Yardım Kimliği.**

*helpstringcontext*<br/>
(İsteğe bağlı) Daha fazla bilgi için [yardım bağlamına](helpstringcontext.md) bakın.

*Gizli*<br/>
(İsteğe bağlı) Tüm kitaplığın görüntülenmesini engeller. Bu kullanım denetimlerle birlikte kullanılmak üzere tasarlanmıştır. Ana bilgisayarların denetimi genişletilmiş özelliklerle saran yeni bir tür kitaplığı oluşturması gerekir. Daha fazla bilgi için [gizli](/windows/win32/Midl/hidden) MIDL özniteliğine bakın.

*kısıtlı*<br/>
(İsteğe bağlı) Kitaplığın üyeleri rasgele çağrılamıyor. Daha fazla bilgi için [kısıtlı](/windows/win32/Midl/restricted) MIDL özniteliğine bakın.

*Özel*<br/>
(İsteğe bağlı) Bir veya daha fazla öznitelik; bu [özel](custom-cpp.md) öznitelik benzer. Özeliçin ilk *custom* parametre öznitelik GUID'dir. Örneğin:

```
[module(custom={guid,1}, custom={guid1,2})]
```

*resource_name*<br/>
.rgs dosyasının dize kaynak kimliği, DLL, çalıştırılabilir veya hizmetin APP Kimliğini kaydetmek için kullanılır. Modül tür hizmeti olduğunda, bu bağımsız değişken, hizmet adını içeren dize kimliğini elde etmek için de kullanılır.

> [!NOTE]
> Hem .rgs dosyası hem de hizmet adını içeren dize aynı sayısal değeri içermelidir.

## <a name="remarks"></a>Açıklamalar

Eğer [emitidl](emitidl.md)için *sınırlı* parametre belirtmediğiniz sürece, **modül** C++ öznitelikleri kullanan herhangi bir programda gereklidir.

**Modül** özniteliğine ek olarak, kaynak kodu [da dispinterface,](dispinterface.md) [dual](dual.md), [object](object-cpp.md)veya [coclass](coclass.md)ima eden bir öznitelik kullanırsa bir kitaplık bloğu oluşturulur.

Bir .idl dosyasında bir kitaplık bloğuna izin verilir. Kaynak kodundaki birden çok modül girişi birleştirilir ve en son parametre değerleri uygulanır.

Bu öznitelik ATL kullanan bir proje içinde kullanılırsa, öznitelik davranışı değişir. Yukarıdaki davranışa ek olarak, öznitelik de doğru tür `_AtlModule`ve ek destek kodu bir global nesne (çağrılır) ekler. Öznitelik tek başınaysa, doğru modül türünden türetilen bir sınıf ekler. Öznitelik bir sınıfa uygulanırsa, doğru modül türünden bir taban sınıf ekler. Doğru tür, *tür* parametresinin değerine göre belirlenir:

- `type` = **Dll**

   [CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md) taban sınıf ve bir COM sunucusu için gerekli standart DLL giriş noktaları olarak kullanılır. Bu giriş noktaları [DllMain](/windows/win32/Dlls/dllmain), [DllRegisterServer](/windows/win32/api/olectl/nf-olectl-dllregisterserver), [DllUnRegisterServer](/windows/win32/api/olectl/nf-olectl-dllunregisterserver), [DllCanUnloadNow](/windows/win32/api/combaseapi/nf-combaseapi-dllcanunloadnow), ve [DllGetClassObject](/windows/win32/api/combaseapi/nf-combaseapi-dllgetclassobject)vardır.

- `type` = **Exe**

   [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md) taban sınıf ve standart çalıştırılabilir giriş noktası [WinMain](/windows/win32/api/winbase/nf-winbase-winmain)olarak kullanılır.

- `type` = **Hizmet**

   [CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md) taban sınıf ve standart çalıştırılabilir giriş noktası [WinMain](/windows/win32/api/winbase/nf-winbase-winmain)olarak kullanılır.

- `type` = **Belirtilme -miş**

   Modül özniteliği ile ilgili ATL kodunun enjeksiyonunu devre dışı kılabilir.

## <a name="example"></a>Örnek

Aşağıdaki kod, oluşturulan .idl dosyasında kitaplık bloğunun nasıl oluşturuluğunu gösterir.

```cpp
// cpp_attr_ref_module1.cpp
// compile with: /LD
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];
```

Aşağıdaki kod, **modülü**kullanarak bir sonucu olarak enjekte edilen kodda görünecek bir işlevin kendi uygulamasını sağlayabileceğinizi gösterir. Enjekte edilen kodu görüntüleme hakkında daha fazla bilgi için [/Fx'e](../../build/reference/fx-merge-injected-code.md) bakın. **Modül** özniteliği tarafından eklenen işlevlerden birini geçersiz kılmak için, işlevin uygulanmasını içerecek bir sınıf yapın ve **modül** özniteliğinin o sınıfa uygulanmasını sağlayabilir.

```cpp
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

### <a name="attribute-context"></a>Öznitelik Bağlamı

|||
|-|-|
|**Için geçerlidir**|Her yer|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için Bkz. [Öznitelik Bağlamları.](cpp-attributes-com-net.md#contexts)

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[usesgetlasterror](usesgetlasterror.md)<br/>
[Kitaplığı](/windows/win32/Midl/library)<br/>
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)<br/>
[helpfile](helpfile.md)<br/>
[Sürüm](version-cpp.md)
