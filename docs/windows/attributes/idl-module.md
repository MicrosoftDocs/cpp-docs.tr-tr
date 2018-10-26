---
title: idl_module (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.idl_module
dev_langs:
- C++
helpviewer_keywords:
- idl_module attribute
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 54fcef3c7b2ef86273a570e483f65b34b3b2efc2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063106"
---
# <a name="idlmodule"></a>idl_module

Bir .dll dosyasına bir giriş noktası belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ idl_module (name=module_name, dllname=dll, uuid="uuid", helpstring="help text", helpstringcontext=helpcontextID, helpcontext=helpcontext, hidden, restricted) ]
function declaration
```

### <a name="parameters"></a>Parametreler

*Adı*<br/>
Kullanıcı tanımlı bir ad .idl dosyasında görünür kod bloğu için.

*dll adı*<br/>
(İsteğe bağlı) Dışarı aktarma içeren .dll dosyası.

*uuid*<br/>
(İsteğe bağlı) Benzersiz kimliği

*helpstring*<br/>
(İsteğe bağlı) Tür kitaplığını açıklamak için kullanılan bir karakter dizesi.

*helpstringcontext*<br/>
(İsteğe bağlı) Bir Yardım konusu .hlp veya .chm dosyasındaki kimliği.

*helpcontext*<br/>
(İsteğe bağlı) Bu tür kitaplığı Yardım kimliği.

*hidden*<br/>
(İsteğe bağlı) Kitaplık görüntülenmesini engeller. bir parametre. Bkz: [gizli](/windows/desktop/Midl/hidden) daha fazla bilgi için MIDL özniteliği.

*restricted*<br/>
(İsteğe bağlı) Kitaplık üyelerini rasgele çağrılamaz. Bkz: [kısıtlı](/windows/desktop/Midl/restricted) daha fazla bilgi için MIDL özniteliği.

*işlev bildirimi*<br/>
Tanımladığınız bir işlev.

## <a name="remarks"></a>Açıklamalar

**İdl_module** C++ özniteliği bir .dll dosyasından almanızı sağlayan bir .dll dosyası içinde giriş noktasını belirtmenize olanak sağlar.

**İdl_module** özniteliğine sahip benzer işlevselliği [Modülü](/windows/desktop/Midl/module) MIDL özniteliği.

Herhangi bir COM nesnesinden bir .idl dosyası kitaplığı bloğu içinde bir DLL giriş noktası koyarak bir .dll dosyasından dışarı aktarabilirsiniz verebilirsiniz.

Kullanmalısınız **idl_module** iki adımda. İlk olarak, bir ad/DLL çifti tanımlamanız gerekir. Ardından kullandığınızda **idl_module** bir giriş noktası belirtmek için adı ve diğer ek öznitelikleri belirtin.

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanılacağını gösterir **idl_module** özniteliği:

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
|**İçin geçerlidir**|Her yerde|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[entry](entry.md)