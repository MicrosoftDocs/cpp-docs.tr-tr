---
title: Yerel (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.local
dev_langs:
- C++
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d0b45106609c4bc93684e0d89737bb0753e36fb4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421095"
---
# <a name="local-c"></a>yerel (C++)

Arabirimi başlığı kullanıldığında, MIDL derleyici üstbilgi Oluşturucu olarak kullanmanıza olanak tanır. Tek bir işlevde kullanıldığında, hiçbir saptamalar oluşturulan yerel bir yordam belirler.

## <a name="syntax"></a>Sözdizimi

```cpp
[local]
```

## <a name="remarks"></a>Açıklamalar

**Yerel** C++ özniteliği ile aynı işlevlere sahip [yerel](/windows/desktop/Midl/local) MIDL özniteliği.

## <a name="example"></a>Örnek

Bkz: [call_as](../windows/call-as.md) nasıl kullanılacağına ilişkin bir örnek **yerel**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**arabirimi**, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|`dispinterface`|

Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)<br/>
[Arabirim Öznitelikleri](../windows/interface-attributes.md)<br/>
[Yöntem Öznitelikleri](../windows/method-attributes.md)<br/>
[call_as](../windows/call-as.md)  