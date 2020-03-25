---
title: uısesgetlasterror (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: f58929db01a1710e811a973c0559ad29b242b4eb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166139"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

Çağrıyı yapana, bu işlevi çağırırken bir hata oluşursa, çağıran daha sonra hata kodunu almak için `GetLastError` çağırabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>Açıklamalar

**Uısesgetlasterror** C++ özniteliği, [uısesgetlasterror](/windows/win32/Midl/usesgetlasterror) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**Uısesgetlasterror**'un nasıl kullanılacağına ilişkin bir örnek için [idl_module](idl-module.md) örneğe bakın.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**module** özniteliği|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)
