---
title: HString::CopyTo yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: a1fd2ef0-e175-4c18-927b-550e02a89e43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f8ea15c56bb974cc297c8fc396205d5f172e9bfd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388088"
---
# <a name="hstringcopyto-method"></a>HString::CopyTo Yöntemi

Geçerli kopyalar **Hstrıng** nesnesini bir HSTRING nesnesine.

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

[HString Sınıfı](../windows/hstring-class.md)