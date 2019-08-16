---
title: idl_module (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.idl_module
helpviewer_keywords:
- idl_module attribute
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
ms.openlocfilehash: 8838a833552ae7066dbcf17b4f676d6626c069f8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514678"
---
# <a name="idl_module"></a>idl_module

Bir. dll dosyasında bir giriş noktası belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ idl_module (name=module_name, dllname=dll, uuid="uuid", helpstring="help text", helpstringcontext=helpcontextID, helpcontext=helpcontext, hidden, restricted) ]
function declaration
```

### <a name="parameters"></a>Parametreler

*name*<br/>
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

**İdl_module** C++ özniteliği, bir. dll dosyasından içeri aktarmanızı sağlayan bir. dll dosyasında giriş noktasını belirtmenize olanak tanır.

**İdl_module** özniteliği, MIDL özniteliğine benzer işlevlere [](/windows/win32/Midl/module) sahiptir.

Bir. DL dosyasının Kitaplık bloğuna DLL giriş noktası koyarak bir. dll dosyasından dışarı aktarmak için bir COM nesnesinden herhangi bir şeyi dışarı aktarabilirsiniz.

İki adımda **idl_module** kullanmanız gerekir. İlk olarak, bir ad/DLL çifti tanımlamanız gerekir. Ardından, bir giriş noktası belirtmek için **idl_module** kullandığınızda, adı ve ek öznitelikleri belirtin.

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
|**Gerekli öznitelikler**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[entry](entry.md)