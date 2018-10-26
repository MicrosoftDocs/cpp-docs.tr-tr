---
title: usesgetlasterror (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.usesgetlasterror
dev_langs:
- C++
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb08e2442e34c4d579e568c68d240accdfdbde59
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074247"
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