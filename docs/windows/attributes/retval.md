---
title: retval (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.retval
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
ms.openlocfilehash: 9f5ad86a289f8904278a58636e66809ae0edd55b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407412"
---
# <a name="retval"></a>retval

Üyenin dönüş değerini alan parametreyi belirler.

## <a name="syntax"></a>Sözdizimi

```cpp
[retval]
```

## <a name="remarks"></a>Açıklamalar

**Retval** C++ özniteliği ile aynı işlevlere sahip [retval](/windows/desktop/Midl/retval) MIDL özniteliği.

**retval** son bağımsız değişken işlevin bildiriminde yer almalıdır.

## <a name="example"></a>Örnek

Örneğin bakın [bağlanabilir](bindable.md) örnek kullanımı için **retval**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Arabirimi parametresi, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|**out**|
|**Geçersiz öznitelikler**|**in**|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)