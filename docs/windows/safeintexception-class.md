---
title: Safeıntexception sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeIntException Class
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException class
- SafeIntException, constructor
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4ffd82f80b8af0b53ca86ca3daded84580e1e07b
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235743"
---
# <a name="safeintexception-class"></a>SafeIntException Sınıfı

`SafeInt` Sınıfının kullandığı `SafeIntException` matematiksel işlem tamamlanamıyor nedenini belirlemek için.

## <a name="syntax"></a>Sözdizimi

```cpp
class SafeIntException;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                    | Açıklama
------------------------------------------------------- | ------------------------------------
[SafeIntException::SafeIntException](#safeintexception) | Oluşturur bir `SafeIntException` nesne.

## <a name="remarks"></a>Açıklamalar

[SafeInt sınıfı](../windows/safeint-class.md) kullanan tek sınıftır `SafeIntException` sınıfı.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SafeIntException`

## <a name="requirements"></a>Gereksinimler

**Başlık:** safeint.h

**Namespace:** msl::utilities

## <a name="safeintexception"></a>Safeıntexception::safeıntexception

Oluşturur bir `SafeIntException` nesne.

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>Parametreler

*Kod*<br/>
[in] Oluşan hatayı açıklayan bir numaralandırılmış veri değeri.

### <a name="remarks"></a>Açıklamalar

Olası değerler için *kod* Safeint.h dosyasında tanımlanır. Kolaylık olması için olası değerler de burada listelenir.

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`
