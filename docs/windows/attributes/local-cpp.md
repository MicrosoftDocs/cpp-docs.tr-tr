---
title: Yerel (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.local
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
ms.openlocfilehash: d3710eee748a43a1daa5c07d8b3feb6beb8f64fa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214753"
---
# <a name="local-c"></a>yerel (C++)

Arabirim üstbilgisinde kullanıldığında, MıDL derleyicisini üst bilgi Oluşturucu olarak kullanmanıza olanak tanır. Tek bir işlevde kullanıldığında, hiçbir saplamalar üretilmeden önce bir yerel yordam belirler.

## <a name="syntax"></a>Sözdizimi

```cpp
[local]
```

## <a name="remarks"></a>Açıklamalar

**Yerel** C++ öznitelik, [Yerel](/windows/win32/Midl/local) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**Yerel**kullanım hakkında bir örnek için bkz. [call_as](call-as.md) .

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**Interface**, Interface yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|`dispinterface`|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[call_as](call-as.md)
