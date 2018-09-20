---
title: HStringReference::CopyTo yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 179d9b14-1ced-4b16-b297-19ca1e92a462
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 61474e3891def73114f8efc101e1132d5d2593b1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402739"
---
# <a name="hstringreferencecopyto-method"></a>HStringReference::CopyTo Yöntemi

Geçerli kopyalar **HStringReference** nesnesini bir HSTRING nesnesine.

## <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Kopyayı alan HSTRING.

## <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı [WindowsDuplicateString](https://msdn.microsoft.com/library/br224634.aspx) işlevi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[HStringReference Sınıfı](../windows/hstringreference-class.md)