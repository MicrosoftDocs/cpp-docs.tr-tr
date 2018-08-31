---
title: HelpString | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstring
dev_langs:
- C++
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ae2d5121e17a9325ec45143e7e90e7d2a211f380
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43223104"
---
# <a name="helpstring"></a>helpstring

Uygulandığı öğe açıklamak için kullanılan bir karakter dizesi belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ helpstring(
   "string"
) ]
```

### <a name="parameters"></a>Parametreler

*string*  
Yardım dizesi metni.

## <a name="remarks"></a>Açıklamalar

**Helpstring** C++ özniteliği ile aynı işlevlere sahip [helpstring](/windows/desktop/Midl/helpstring) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [defaultvalue](../windows/defaultvalue.md) nasıl kullanılacağına ilişkin bir örnek **helpstring**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**arabirimi**, **typedef**, **sınıfı**, yöntem, özellik|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)  
[Arabirim Öznitelikleri](../windows/interface-attributes.md)  
[Sınıf Öznitelikleri](../windows/class-attributes.md)  
[Yöntem Öznitelikleri](../windows/method-attributes.md)  
[Typedef, Enum, Union ve Struct Öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)  
[helpfile](../windows/helpfile.md)  
[helpcontext](../windows/helpcontext.md)  