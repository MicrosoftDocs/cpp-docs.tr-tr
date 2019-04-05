---
title: usesgetlasterror (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: 9f050bbf69edf1ab8327a283299cb5e687ce5380
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032212"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

Bu işlev çağrılırken bir hata ise sonra çağıran ardından çağırabileceğiniz çağıran söyler `GetLastError` hata kodu alınamıyor.

## <a name="syntax"></a>Sözdizimi

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>Açıklamalar

**Usesgetlasterror** C++ özniteliği ile aynı işlevlere sahip [usesgetlasterror](/windows/desktop/Midl/usesgetlasterror) MIDL özniteliği.

## <a name="example"></a>Örnek

Bkz: [idl_module](idl-module.md) nasıl kullanılacağına ilişkin bir örnek için örnek **usesgetlasterror**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|**Modül** özniteliği|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|None|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)