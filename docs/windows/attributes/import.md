---
title: İçeri AktarC++ (com özniteliği)
ms.date: 10/03/2018
f1_keywords:
- vc-attr.import
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
ms.openlocfilehash: f9ed80bdcc04302c0dee85935f377c8e3dbfd37f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514626"
---
# <a name="import"></a>içeri aktar

Ana IDL 'ınızdan başvurmak istediğiniz tanımları içeren başka bir. IDL,. odl veya üst bilgi dosyasını belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ import(
   idl_file
) ];
```

### <a name="parameters"></a>Parametreler

*idl_file*<br/>
Geçerli projenin tür kitaplığına içeri aktarılmasını istediğiniz. IDL dosyasının adı.

## <a name="remarks"></a>Açıklamalar

**İmport** C++ özniteliği, bir `#import` `import "docobj.idl"` deyimin oluşturulan. IDL dosyasındaki deyimin altına yerleştirilmesine neden olur. **İmport** özniteliği [içeri aktarma](/windows/win32/Midl/import) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

**İçeri aktarma** özniteliği yalnızca, belirtilen dosyayı projeniz tarafından oluşturulacak. IDL dosyasına koyar; **Import** özniteliği, projenizdeki kaynak koddan belirtilen dosyadaki yapıları çağırmasına izin vermez.  Projenizdeki kaynak koddan belirtilen dosyadaki yapıları çağırmak için [#import](../../preprocessor/hash-import-directive-cpp.md) ve `embedded_idl` özniteliğini kullanın ya da bir. h dosyası varsa, *idl_file*için. h dosyasını dahil edebilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki kod:

```cpp
// cpp_attr_ref_import.cpp
// compile with: /LD
[module(name="MyLib")];
[import(import.idl)];
```

oluşturulan. IDL dosyasında aşağıdaki kodu üretir:

```
import "docobj.idl";
import "import.idl";

[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]
library MyLib {
   importlib("stdole2.tlb");
   importlib("olepro32.dll");
...
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
[importidl](importidl.md)<br/>
[importlib](importlib.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)