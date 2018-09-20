---
title: propput | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.propput
dev_langs:
- C++
helpviewer_keywords:
- propput attribute
ms.assetid: 1f84dda9-9cce-4e16-aaf0-b2c5219827f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5c8d9038fc8ded02afe02169731692b290466df6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442818"
---
# <a name="propput"></a>propput

Bir özellik ayarı işlevi belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[propput]
```

## <a name="remarks"></a>Açıklamalar

**Propput** C++ özniteliği ile aynı işlevlere sahip [propput](/windows/desktop/Midl/propput) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [bağlanabilir](../windows/bindable.md) örnek kullanımı için **propput**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Yöntem|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|`propget`, `propputref`|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)<br/>
[Yöntem Öznitelikleri](../windows/method-attributes.md)<br/>
[propget](../windows/propget.md)<br/>
[propputref](../windows/propputref.md)