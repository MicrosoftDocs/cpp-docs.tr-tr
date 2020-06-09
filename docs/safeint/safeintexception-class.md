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
ms.openlocfilehash: 8149a5e1216e26fafc1e0cd4a489cdad0551607c
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615416"
---
# <a name="safeintexception-class"></a>SafeIntException Sınıfı

`SafeInt`Sınıfı, `SafeIntException` bir matematik işleminin neden tamamlanamadığına ilişkin olarak ' i kullanır.

> [!NOTE]
> Bu kitaplığın en son sürümü konumunda bulunur [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt) .

## <a name="syntax"></a>Söz dizimi

```cpp
class SafeIntException;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Name                                                    | Açıklama
------------------------------------------------------- | ------------------------------------
[SafeIntException::SafeIntException](#safeintexception) | Bir `SafeIntException` nesnesi oluşturur.

## <a name="remarks"></a>Açıklamalar

[SafeInt sınıfı](safeint-class.md) , sınıfını kullanan tek sınıftır `SafeIntException` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SafeIntException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** SafeInt. h

**Ad alanı:** MSL:: Utilities

## <a name="safeintexceptionsafeintexception"></a><a name="safeintexception"></a>SafeIntException:: SafeIntException

Bir `SafeIntException` nesnesi oluşturur.

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>Parametreler

*kodudur*<br/>
'ndaki Oluşan hatayı açıklayan bir numaralandırılmış veri değeri.

### <a name="remarks"></a>Açıklamalar

*Kod* için olası değerler SafeInt. h dosyasında tanımlanmıştır. Kolaylık sağlaması için, olası değerler de burada listelenmiştir.

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`
