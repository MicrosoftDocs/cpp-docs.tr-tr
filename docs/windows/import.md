---
title: içeri aktarma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.import
dev_langs:
- C++
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 78bfc20bd88aa9691c80483c8c315cd5305d7b96
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43216597"
---
# <a name="import"></a>içeri aktar

, Ana IDL başvurmak istediğiniz tanımlarını içeren başka bir .idl, .odl veya üst bilgi dosyasını belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ import(
   idl_file
) ];
```

### <a name="parameters"></a>Parametreler

*idl_file*  
Geçerli proje türü kitaplığına içeri aktarılan istediğiniz bir .idl dosyasının adı.

## <a name="remarks"></a>Açıklamalar

**Alma** C++ öznitelik neden bir `#import` altına yerleştirilecek deyimi `import "docobj.idl"` oluşturulan .idl dosyasındaki deyimi. **Alma** özniteliği ile aynı işlevlere sahip [alma](/windows/desktop/Midl/import) MIDL özniteliği.

**Alma** özniteliği yalnızca yerleştirir belirtilen dosya; projeniz tarafından oluşturulan .idl dosyasına **alma** özniteliği, yapıları belirtilen dosyada kaynak koddan çağrı vermez Projenizde.  Kaynak kodu, projenizdeki belirtilen dosyada yapıları çağırmak için kullanın ya da [#import](../preprocessor/hash-import-directive-cpp.md) ve `embedded_idl` veya özniteliği için .h dosyası içerebilir *idl_file*, .h dosyası varsa.

## <a name="example"></a>Örnek

Aşağıdaki kodu:

```cpp
// cpp_attr_ref_import.cpp
// compile with: /LD
[module(name="MyLib")];
[import(import.idl)];
```

oluşturulan .idl dosyasına aşağıdaki kodu üretir:

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
|**İçin geçerlidir**|Her yerde|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)  
[Tek Başına Öznitelikler](../windows/stand-alone-attributes.md)  
[importidl](../windows/importidl.md)  
[importlib](../windows/importlib.md)  
[İçerir](../windows/include-cpp.md)  
[includelib](../windows/includelib-cpp.md)  