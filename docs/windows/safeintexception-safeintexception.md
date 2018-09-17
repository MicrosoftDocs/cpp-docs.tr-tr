---
title: Safeıntexception::safeıntexception | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException, constructor
ms.assetid: 8e5a0c24-a56b-4c80-9ee8-876604b1e7dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 749ef965520732c37457613f44e0a23e213023db
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700979"
---
# <a name="safeintexceptionsafeintexception"></a>SafeIntException::SafeIntException

Oluşturur bir **Safeıntexception** nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>Parametreler

*Kod*<br/>
[in] Oluşan hatayı açıklayan bir numaralandırılmış veri değeri.

## <a name="remarks"></a>Açıklamalar

Olası değerler için *kod* Safeint.h dosyasında tanımlanır. Kolaylık olması için olası değerler de burada listelenir.

- `SafeIntNoError`

- `SafeIntArithmeticOverflow`

- `SafeIntDivideByZero`

## <a name="requirements"></a>Gereksinimler

**Başlık:** safeint.h

**Namespace:** msl::utilities

## <a name="see-also"></a>Ayrıca Bkz.

[SafeInt Kitaplığı](../windows/safeint-library.md)  
[SafeIntException Sınıfı](../windows/safeintexception-class.md)  
[SafeInt Sınıfı](../windows/safeint-class.md)