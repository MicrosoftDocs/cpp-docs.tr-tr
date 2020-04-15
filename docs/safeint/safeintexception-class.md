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
ms.openlocfilehash: e118d7e3cce47ebb93cef16319a8fc45aab1118b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349953"
---
# <a name="safeintexception-class"></a>SafeIntException Sınıfı

Sınıf, `SafeInt` `SafeIntException` matematiksel bir işlemin neden tamamlanamayacağını belirlemek için kullanır.

> [!NOTE]
> Bu kitaplığın en son sürümü [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt).

## <a name="syntax"></a>Sözdizimi

```cpp
class SafeIntException;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                                    | Açıklama
------------------------------------------------------- | ------------------------------------
[SafeIntException::SafeIntException](#safeintexception) | Bir `SafeIntException` nesnesi oluşturur.

## <a name="remarks"></a>Açıklamalar

[SafeInt sınıfı](../safeint/safeint-class.md) `SafeIntException` sınıfı kullanan tek sınıftır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SafeIntException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** safeint.h

**Ad alanı:** msl::yardımcı programlar

## <a name="safeintexceptionsafeintexception"></a><a name="safeintexception"></a>SafeIntException::SafeIntException

Bir `SafeIntException` nesnesi oluşturur.

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>Parametreler

*Kod*<br/>
[içinde] Oluşan hatayı açıklayan numaralandırılmış bir veri değeri.

### <a name="remarks"></a>Açıklamalar

*Kod* için olası değerler Safeint.h dosyasında tanımlanır. Kolaylık sağlamak için, olası değerler de burada listelenir.

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`
