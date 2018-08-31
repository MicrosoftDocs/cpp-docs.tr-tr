---
title: HelpContext | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpcontext
dev_langs:
- C++
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5644f99e15685f8f1784cc40886709b05a9a06bd
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221290"
---
# <a name="helpcontext"></a>helpcontext

Bu öğe ile ilgili kullanıcı bilgilerini görüntüle sağlayan bir bağlam kimliği belirtir **yardımcı** dosya.

## <a name="syntax"></a>Sözdizimi

```cpp
[ helpcontext(
   id
) ]
```

### <a name="parameters"></a>Parametreler

*id*  
Yardım içeriği kimliği. Bkz: [HTML Help: Context-Sensitive Help for Your Programs](../mfc/html-help-context-sensitive-help-for-your-programs.md) bağlam kimlikleri hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

**Helpcontext** C++ özniteliği ile aynı işlevlere sahip [helpcontext](/windows/desktop/Midl/helpcontext) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [defaultvalue](../windows/defaultvalue.md) nasıl kullanılacağına ilişkin bir örnek **helpcontext**.

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
[helpstring](../windows/helpstring.md)  