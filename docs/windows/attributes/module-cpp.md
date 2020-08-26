---
title: Modül (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.module
helpviewer_keywords:
- module attributes
ms.assetid: 02223b2a-62b5-4262-832f-564b1e11e58e
ms.openlocfilehash: b6cde0baaae9901258e90ededf05c60cb13a7dc1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833978"
---
# <a name="module-c"></a>modül (C++)

. IDL dosyasında kitaplık bloğunu tanımlar.

## <a name="syntax"></a>Söz dizimi

```cpp
[ module (type=dll, name=string, version=1.0, uuid=uuid, lcid=integer, control=boolean, helpstring=string, helpstringdll=string, helpfile=string, helpcontext=integer, helpstringcontext=integer, hidden=boolean, restricted=boolean, custom=string, resource_name=string,) ];
```

### <a name="parameters"></a>Parametreler

*türüyle*<br/>
Seçim Aşağıdakilerden biri olabilir:

- `dll` Sonuçta ortaya çıkan DLL 'nin işlem içi COM sunucusu olarak çalışmasına izin veren işlevler ve sınıflar ekler. Varsayılan değer budur.

- `exe` Sonuçta elde edilen yürütülebilir dosyanın işlem dışı COM sunucusu olarak çalışmasına izin veren işlevler ve sınıflar ekler.

- `service` Ortaya çıkan yürütülebilir dosyanın bir NT hizmeti olarak çalışmasına izin veren işlevler ve sınıflar ekler.

- `unspecified` Module özniteliğiyle ilgili ATL kodu ekleme işlemini devre dışı bırakır: ATL modül sınıfının, genel örnek _AtlModule ve giriş noktası işlevlerinin eklenmesine izin vermez. , Projedeki diğer öznitelikler nedeniyle ATL kodunun eklenmesine izin vermez.

*ada*<br/>
Seçim Kitaplık bloğunun adı.

*Sürüm*<br/>
Seçim Kitaplık bloğuna atamak istediğiniz sürüm numarası. Varsayılan değer 1,0 ' dir.

*uuid*<br/>
Kitaplığın benzersiz KIMLIĞI. Bu parametreyi atlarsanız, kitaplık için otomatik olarak bir KIMLIK oluşturulur. **__Uuidof (** *LibraryName* **)** tanımlayıcısını kullanarak yapabileceğiniz kitaplık blobunun *UUID* 'sini almanız gerekebilir.

*lcid*<br/>
Yerelleştirme parametresi. Daha fazla bilgi için bkz. [LCID](/windows/win32/Midl/lcid) .

*denetimle*<br/>
Seçim Kitaplıktaki tüm ortak sınıfların denetimlerin olduğunu belirtir.

*helpstring*<br/>
Tür kitaplığını belirtir.

*helpstringdll*<br/>
Seçim Belge dizesi aramasını gerçekleştirmek için kullanılacak. dll dosyasının adını ayarlar. Daha fazla bilgi için bkz. [helpstringdll](/windows/win32/Midl/helpstringdll) .

*helpfile*<br/>
Seçim Tür kitaplığı için **Yardım** dosyasının adı.

*helpcontext*<br/>
Seçim Bu tür kitaplığı için **Yardım kimliği** .

*helpstringcontext*<br/>
Seçim Daha fazla bilgi için bkz. [helpstringcontext](helpstringcontext.md) .

*gizli*<br/>
Seçim Tüm kitaplığın görüntülenmesini önler. Bu kullanım, denetimlerle birlikte kullanılmak üzere tasarlanmıştır. Ana bilgisayarların, denetimi genişletilmiş özelliklerle sarmalayan yeni bir tür kitaplığı oluşturması gerekir. Daha fazla bilgi için bkz. [Hidden](/windows/win32/Midl/hidden) MIDL özniteliği.

*dığından*<br/>
Seçim Kitaplığın üyeleri rasgele çağrılamaz. Daha fazla bilgi için bkz. [kısıtlı](/windows/win32/Midl/restricted) MIDL özniteliği.

*özel*<br/>
Seçim Bir veya daha fazla öznitelik; Bu [özel](custom-cpp.md) özniteliğe benzerdir. *Özel* için ilk parametre, özniteliğin GUID 'sidir. Örnek:

```
[module(custom={guid,1}, custom={guid1,2})]
```

*resource_name*<br/>
DLL, çalıştırılabilir veya hizmetin uygulama KIMLIĞINI kaydetmek için kullanılan. rgs dosyasının dize kaynak KIMLIĞI. Modül hizmet türünde olduğunda, bu bağımsız değişken aynı zamanda hizmet adını içeren dizenin KIMLIĞINI elde etmek için de kullanılır.

> [!NOTE]
> Hem. rgs dosyası hem de hizmet adını içeren dize aynı sayısal değeri içermelidir.

## <a name="remarks"></a>Açıklamalar

*Kısıtlanmış* parametresini [emitidl](emitidl.md)olarak belirtmediğiniz müddetçe, C++ özniteliklerini kullanan herhangi bir programda **Modül** gereklidir.

**Modül** özniteliğine ek olarak, kaynak kodu de [dispınterface](dispinterface.md), [Dual](dual.md), [Object](object-cpp.md)veya [coclass](coclass.md)öğesini gerektiren bir özniteliği de kullanıyorsa, kitaplık bloğu oluşturulacaktır.

Bir. IDL dosyasında bir kitaplık bloğuna izin verilir. Kaynak kodundaki birden çok modül girişi, uygulanan en son parametre değerleriyle birleştirilir.

Bu öznitelik, ATL kullanan bir proje içinde kullanılıyorsa, öznitelik davranışı değişir. Yukarıdaki davranışa ek olarak öznitelik, doğru türdeki (adlı) genel bir nesne `_AtlModule` ve ek destek kodu da ekler. Özniteliği tek başına ise doğru modül türünden türetilmiş bir sınıf ekler. Özniteliği bir sınıfa uygulanırsa doğru modül türünün bir Taban sınıfını ekler. Doğru tür, *tür* parametresinin değeri tarafından belirlenir:

- `type` = **dosyasını**

   [Catldllmodület](../../atl/reference/catldllmodulet-class.md) , temel sınıf olarak ve bir com sunucusu için gereken standart dll giriş noktaları olarak kullanılır. Bu giriş noktaları [DllMain](/windows/win32/Dlls/dllmain), [DllRegisterServer](/windows/win32/api/olectl/nf-olectl-dllregisterserver), [DllUnregisterServer](/windows/win32/api/olectl/nf-olectl-dllunregisterserver), [DllCanUnloadNow](/windows/win32/api/combaseapi/nf-combaseapi-dllcanunloadnow)ve [DllGetClassObject](/windows/win32/api/combaseapi/nf-combaseapi-dllgetclassobject).

- `type` = **exe**

   [Catlexemodület](../../atl/reference/catlexemodulet-class.md) , temel sınıf olarak ve standart çalıştırılabilir [giriş noktası olarak](/windows/win32/api/winbase/nf-winbase-winmain)kullanılır.

- `type` = **hizmetle**

   [CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md) , temel sınıf olarak ve standart çalıştırılabilir [giriş noktası olarak](/windows/win32/api/winbase/nf-winbase-winmain)kullanılır.

- `type` = **Memesi**

   Module özniteliğiyle ilgili ATL kodu ekleme işlemini devre dışı bırakır.

## <a name="example"></a>Örnek

Aşağıdaki kod, oluşturulan. IDL dosyasında bir kitaplık bloğunun nasıl oluşturulacağını gösterir.

```cpp
// cpp_attr_ref_module1.cpp
// compile with: /LD
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];
```

Aşağıdaki kod, **modülü**kullanmanın sonucu olarak eklenen kodda görünecek bir işlev uygulamanızı sağlayabileceğinizi gösterir. Eklenen kodu görüntüleme hakkında daha fazla bilgi için bkz. [/FX](../../build/reference/fx-merge-injected-code.md) . **Modül** özniteliği tarafından eklenen işlevlerden birini geçersiz kılmak için, işlev uygulamanızı içerecek bir sınıf oluşturun ve **Modül** özniteliğinin bu sınıfa uygulanmasını sağlayın.

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Her yer|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[Tek başına öznitelikler](stand-alone-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[usesgetlasterror](usesgetlasterror.md)<br/>
[Kitaplığı](/windows/win32/Midl/library)<br/>
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)<br/>
[helpfile](helpfile.md)<br/>
[Sürüm](version-cpp.md)
