---
title: idl_module (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.idl_module
helpviewer_keywords:
- idl_module attribute
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
ms.openlocfilehash: 651d2e133d7ef08fce48feded1b7a5aff458adb1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845230"
---
# <a name="idl_module"></a>idl_module

Bir. dll dosyasında bir giriş noktası belirtir.

## <a name="syntax"></a>Söz dizimi

```cpp
[ idl_module (name=module_name, dllname=dll, uuid="uuid", helpstring="help text", helpstringcontext=helpcontextID, helpcontext=helpcontext, hidden, restricted) ]
function declaration
```

### <a name="parameters"></a>Parametreler

*ada*<br/>
Kod bloğu için. IDL dosyasında görünecek Kullanıcı tanımlı bir ad.

*dll*<br/>
Seçim Dışarı aktarmayı içeren. dll dosyası.

*uuid*<br/>
Seçim Benzersiz bir KIMLIK.

*helpstring*<br/>
Seçim Tür kitaplığını anlatmak için kullanılan bir karakter dizesi.

*helpstringcontext*<br/>
Seçim Bir. hlp veya. chm dosyasındaki Yardım konusunun KIMLIĞI.

*helpcontext*<br/>
Seçim Bu tür kitaplığı için yardım KIMLIĞI.

*gizli*<br/>
Seçim Kitaplığın görüntülenmesini önleyen bir parametre. Daha fazla bilgi için bkz. [Hidden](/windows/win32/Midl/hidden) MIDL özniteliği.

*dığından*<br/>
Seçim Kitaplığın üyeleri rastgele olarak çağrılamaz. Daha fazla bilgi için bkz. [kısıtlı](/windows/win32/Midl/restricted) MIDL özniteliği.

*işlev bildirimi*<br/>
Tanımlayacağınızı belirten işlev.

## <a name="remarks"></a>Açıklamalar

**İdl_module** C++ özniteliği, giriş noktasını bir. dll dosyasından almanızı sağlayan bir. dll dosyasında belirtmenize olanak tanır.

**İdl_module** özniteliği [, MIDL](/windows/win32/Midl/module) özniteliğine benzer işlevlere sahiptir.

Bir. DL dosyasının Kitaplık bloğuna DLL giriş noktası koyarak bir. dll dosyasından dışarı aktarmak için bir COM nesnesinden herhangi bir şeyi dışarı aktarabilirsiniz.

**İdl_module** iki adımda kullanmanız gerekir. İlk olarak, bir ad/DLL çifti tanımlamanız gerekir. Ardından, bir giriş noktası belirtmek için **idl_module** kullandığınızda, adı ve ek öznitelikleri belirtin.

## <a name="example"></a>Örnek

Aşağıdaki kod **idl_module** özniteliğinin nasıl kullanılacağını gösterir:

```cpp
// cpp_attr_ref_idl_module.cpp
// compile with: /LD
[idl_quote("midl_pragma warning(disable:2461)")];
[module(name="MyLibrary"), idl_module(name="MyLib", dllname="xxx.dll")];
[idl_module(name="MyLib"), entry(4), usesgetlasterror]
void FuncName(int i);
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
[Tek başına öznitelikler](stand-alone-attributes.md)<br/>
[girişte](entry.md)
