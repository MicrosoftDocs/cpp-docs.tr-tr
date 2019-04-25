---
title: SafeIntException Sınıfı
ms.date: 10/22/2018
ms.topic: reference
f1_keywords:
- SafeIntException Class
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
helpviewer_keywords:
- SafeIntException class
- SafeIntException, constructor
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
ms.openlocfilehash: 2998bbb83fd568d7ff627d6598c32fb5b17c1e40
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179328"
---
# <a name="safeintexception-class"></a>SafeIntException Sınıfı

`SafeInt` Sınıfının kullandığı `SafeIntException` matematiksel işlem tamamlanamıyor nedenini belirlemek için.

> [!NOTE]
> Bu kitaplık en son sürümünü şu konumdadır [ https://github.com/dcleblanc/SafeInt ](https://github.com/dcleblanc/SafeInt).

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

[SafeInt sınıfı](../safeint/safeint-class.md) kullanan tek sınıftır `SafeIntException` sınıfı.

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
