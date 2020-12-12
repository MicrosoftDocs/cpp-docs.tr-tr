---
description: 'Daha fazla bilgi edinin: usesgetlasterror'
title: uısesgetlasterror (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: f43ae005e2f888f4318900cbde58f449011bd15e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329517"
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
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)
