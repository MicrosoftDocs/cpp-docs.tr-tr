---
title: uısesgetlasterror (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: e3d3c292554350d85296971a9bd3620909ef47c7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831638"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

Çağrıyı yapana, bu işlevi çağırırken bir hata oluşursa, çağıran daha sonra `GetLastError` hata kodunu almak için çağırabilirler.

## <a name="syntax"></a>Syntax

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>Açıklamalar

**Uısesgetlasterror** C++ özniteliği, [uısesgetlasterror](/windows/win32/Midl/usesgetlasterror) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**Uısesgetlasterror**'un nasıl kullanılacağına ilişkin bir örnek için [idl_module](idl-module.md) örneğe bakın.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**module** özniteliği|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)
