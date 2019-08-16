---
title: retval (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.retval
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
ms.openlocfilehash: 2a2865c1eda229f1a2fcd457c22119b2908c1caa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514052"
---
# <a name="retval"></a>retval

Üyenin dönüş değerini alan parametreyi belirler.

## <a name="syntax"></a>Sözdizimi

```cpp
[retval]
```

## <a name="remarks"></a>Açıklamalar

**Retval** C++ özniteliği, [retval](/windows/win32/Midl/retval) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

**retval** , bir işlevin bildiriminde yer alan son bağımsız değişkende yer almalıdır.

## <a name="example"></a>Örnek

**Retval**öğesinin örnek kullanımı için [bağlanabilir](bindable.md) örneğine bakın.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Arabirim parametresi, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|**out**|
|**Geçersiz öznitelikler**|**in**|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)