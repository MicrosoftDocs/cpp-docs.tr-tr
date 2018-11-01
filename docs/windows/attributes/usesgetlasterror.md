---
title: usesgetlasterror (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: 44a1a55114bcf2466aa5b084f2b53c5457f1a0aa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487028"
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
|**İçin geçerlidir**|**Modül** özniteliği|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)