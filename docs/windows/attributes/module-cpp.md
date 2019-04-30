---
title: Modül (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.module
helpviewer_keywords:
- module attributes
ms.assetid: 02223b2a-62b5-4262-832f-564b1e11e58e
ms.openlocfilehash: 5c69e0aa9e3444ec9b43470f8feb4d1f870dc9c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409193"
---
# <a name="module-c"></a>modül (C++)

Kitaplık blok .idl dosyasında tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ module (type=dll, name=string, version=1.0, uuid=uuid, lcid=integer, control=boolean, helpstring=string, helpstringdll=string, helpfile=string, helpcontext=integer, helpstringcontext=integer, hidden=boolean, restricted=boolean, custom=string, resource_name=string,) ];
```

### <a name="parameters"></a>Parametreler

*type*<br/>
(İsteğe bağlı) Aşağıdakilerden biri olabilir:

- `dll` İşlevleri ve işlemde COM sunucusu olarak çalışabilmesi ortaya çıkan DLL'yi izin sınıflar ekler. Varsayılan değer budur.

- `exe` İşlevleri ve ortaya çıkan izin sınıflar ekler işlevi görecek bir giden işlem COM sunucusunun yürütülebilir.

- `service` İşlevleri ve ortaya çıkan izin sınıflar ekler işlevi görecek bir NT hizmeti çalıştırılabilir.

- `unspecified` Modül özniteliği için ilgili ATL kod ekleme devre dışı bırakır: ekleme ATL modül sınıfı, genel örnek _AtlModule ve giriş noktası işlevleri. ATL kod projesinde diğer öznitelikleri nedeniyle ekleme devre dışı bırakmaz.

*Adı*<br/>
(İsteğe bağlı) Kitaplık blok adı.

*version*<br/>
(İsteğe bağlı) Kitaplığını bloğuna atamak istediğiniz sürüm numarası. 1.0 varsayılan değerdir.

*uuid*<br/>
Kitaplık için benzersiz kimliği. Bu parametreyi unutursanız, kitaplık için bir kimliği otomatik olarak oluşturulur. Almanız gerekebilir *UUID* tanımlayıcısını kullanarak bunu yapabilirsiniz, kitaplık bloğunun **__uuidof (** *libraryname* **)**.

*lcid*<br/>
Yerelleştirme parametre. Bkz: [LCID](/windows/desktop/Midl/lcid) daha fazla bilgi için.

*control*<br/>
(İsteğe bağlı) Kitaplığı'nda, tüm coclass'ları denetimleri olduğunu belirtir.

*helpstring*<br/>
Tür kitaplığını belirtir.

*helpstringdll*<br/>
(İsteğe bağlı) Bir belge dize araması gerçekleştirmek için kullanılacak .dll dosyasının adını ayarlar. Bkz: [helpstringdll](/windows/desktop/Midl/helpstringdll) daha fazla bilgi için.

*helpfile*<br/>
(İsteğe bağlı) Adını **yardımcı** tür kitaplığı dosyası.

*helpcontext*<br/>
(İsteğe bağlı) **Yardımcı kimliği** bu tür kitaplığı için.

*helpstringcontext*<br/>
(İsteğe bağlı) Bkz: [helpstringcontext](helpstringcontext.md) daha fazla bilgi için.

*hidden*<br/>
(İsteğe bağlı) Tüm Kitaplığı görüntülenmesini engeller. Bu kullanım denetimleri ile kullanıma yöneliktir. Genişletilmiş özelliklere sahip bir denetim sarmalayan yeni bir tür kitaplığı oluşturmak konakları gerekir. Bkz: [gizli](/windows/desktop/Midl/hidden) daha fazla bilgi için MIDL özniteliği.

*restricted*<br/>
(İsteğe bağlı) Kitaplık üyelerini rasgele çağrılamaz. Bkz: [kısıtlı](/windows/desktop/Midl/restricted) daha fazla bilgi için MIDL özniteliği.

*custom*<br/>
(İsteğe bağlı) Bir veya daha fazla öznitelik varsa Bu benzer [özel](custom-cpp.md) özniteliği. İlk parametre olarak *özel* özniteliğinin GUID'dir. Örneğin:

```
[module(custom={guid,1}, custom={guid1,2})]
```

*resource_name*<br/>
Uygulama Kimliği dll, yürütülebilir veya hizmet kaydetmek için kullanılan .rgs dosya dize kaynak kimliği. Modül türü hizmetidir, bu bağımsız değişken hizmet adını içeren dize Kimliğini almak için de kullanılır.

> [!NOTE]
> Aynı sayısal değere .rgs dosya hem de hizmet adını içeren dize içermelidir.

## <a name="remarks"></a>Açıklamalar

Siz belirtmediğiniz sürece *kısıtlı* parametresi [emitidl](emitidl.md), **Modülü** C++ öznitelikleri kullanan herhangi bir programda gereklidir.

Bir kitaplık bloğu, oluşturulacak ek olarak **Modülü** özniteliği, kaynak kodu da kullandığı [dispinterface](dispinterface.md), [çift](dual.md), [nesne](object-cpp.md), veya gelir bir öznitelik [coclass'ı](coclass.md).

Bir .idl dosyasında bir kitaplığını bloğuna izin verilir. Kaynak kodunda birden çok modül girişi, uygulanan en son parametre değerleriniz ile birleştirilir.

Bu öznitelik ATL kullanan bir proje içinde kullanılıyorsa, öznitelik davranışını değiştirir. Yukarıdaki davranışa ek olarak, öznitelik genel nesne de ekler (adlı `_AtlModule`) doğru tür ve ek destek kodu. Öznitelik, tek başına ise, doğru modül türünden türetilmiş bir sınıf ekler. Öznitelik bir sınıfa uygulandığında doğru modül türünün bir temel sınıf ekler. Doğru türü değeri tarafından belirlenir *türü* parametresi:

- `type` = **dll**

   [CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md) taban sınıfı ve standart DLL girdi kullanılan noktaları için bir COM sunucusu gerekir. Bu giriş noktalarıdır [DllMain](/windows/desktop/Dlls/dllmain), [DllRegisterServer](/windows/desktop/api/olectl/nf-olectl-dllregisterserver), [DllUnRegisterServer](/windows/desktop/api/olectl/nf-olectl-dllunregisterserver), [DllCanUnloadNow](/windows/desktop/api/combaseapi/nf-combaseapi-dllcanunloadnow), ve [ DllGetClassObject](https://msdn.microsoft.com/library/windows/desktop/dd797891).

- `type` = **exe**

   [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md) taban sınıfı ve standart bir yürütülebilir giriş noktası kullanılan [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain).

- `type` = **Hizmet**

   [CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md) taban sınıfı ve standart bir yürütülebilir giriş noktası kullanılan [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain).

- `type` = **Belirtilmemiş**

   Modül özniteliği için ilgili ATL kod ekleme devre dışı bırakır.

## <a name="example"></a>Örnek

Aşağıdaki kod, oluşturulan .idl dosyasında kitaplığı blok oluşturulacağını gösterir.

```cpp
// cpp_attr_ref_module1.cpp
// compile with: /LD
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];
```

Aşağıdaki kod, kendi kullanmanın sonucu eklenen kod içinde görünecek bir işlev uygulaması sağlayabilirsiniz gösterir **Modülü**. Bkz: [/Fx](../../build/reference/fx-merge-injected-code.md) eklenen kodu görüntüleme hakkında daha fazla bilgi. Tarafından eklenen işlevlerden biri geçersiz kılmak için **Modülü** özniteliği, ve uygulamanıza işlev içeren bir sınıf olun **Modülü** özniteliği o sınıfa uygulayın.

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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Her yerde|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[usesgetlasterror](usesgetlasterror.md)<br/>
[Kitaplık](/windows/desktop/Midl/library)<br/>
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)<br/>
[helpfile](helpfile.md)<br/>
[version](version-cpp.md)