---
title: uısesgetlasterror (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: b14316bd929f4b41b13a76c41e94b31b7534e9d8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513886"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

Çağrıyı yapana, bu işlevi çağırırken bir hata oluşursa, çağıran daha sonra hata kodunu almak için çağırabilirler `GetLastError` .

## <a name="syntax"></a>Sözdizimi

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>Açıklamalar

**Uısesgetlasterror** C++ özniteliği, [uısesgetlasterror](/windows/win32/Midl/usesgetlasterror) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**Uısesgetlasterror**kullanımı örneği için [idl_module](idl-module.md) örneğine bakın.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**module** özniteliği|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)