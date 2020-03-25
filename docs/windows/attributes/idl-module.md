---
title: idl_module (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.idl_module
helpviewer_keywords:
- idl_module attribute
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
ms.openlocfilehash: 6dd0a34d5d957838613bde2c9e05d5ef26a1f678
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168050"
---
# <a name="idl_module"></a>idl_module

Bir. dll dosyasında bir giriş noktası belirtir.

## <a name="syntax"></a>Sözdizimi

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

*hidden*<br/>
Seçim Kitaplığın görüntülenmesini önleyen bir parametre. Daha fazla bilgi için bkz. [Hidden](/windows/win32/Midl/hidden) MIDL özniteliği.

*restricted*<br/>
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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Yerdeki|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[entry](entry.md)
