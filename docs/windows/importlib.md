---
title: importlib | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.importlib
dev_langs:
- C++
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b9522db579641d79b8b77cc870cd1df6f03c0413
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607679"
---
# <a name="importlib"></a>importlib

Zaten başka bir tür kitaplığına oluşturulan tür kitaplığı için kullanılabilir derlenmiştir türleri sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ importlib(
   "tlb_file"
) ];
```

### <a name="parameters"></a>Parametreler

*tlb_file*  
Geçerli proje türü kitaplığına içeri aktarılan istediğiniz tırnak içinde .tlb dosyasının adı.

## <a name="remarks"></a>Açıklamalar

**İmportlib** C++ öznitelik neden olan bir `importlib` oluşturulan .idl dosyasının kitaplığı bloğunda yerleştirilecek deyimi. **İmportlib** özniteliği ile aynı işlevlere sahip [importlib](http://msdn.microsoft.com/library/windows/desktop/aa367050) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği nasıl kullanılacağını gösterir **importlib**:

```cpp
// cpp_attr_ref_importlib.cpp
// compile with: /LD
[module(name="MyLib")];
[importlib("importlib.tlb")];
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

[Derleyici Öznitelikleri](../windows/compiler-attributes.md)  
[Tek Başına Öznitelikler](../windows/stand-alone-attributes.md)  
[import](../windows/import.md)  
[importidl](../windows/importidl.md)  
[İçerir](../windows/include-cpp.md)  
[includelib](../windows/includelib-cpp.md)