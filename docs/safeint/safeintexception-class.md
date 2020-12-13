---
description: 'Daha fazla bilgi edinin: SafeIntException sınıfı'
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
ms.openlocfilehash: 6a7be21b0dfa42a23ba60eac7eb3f4ebbf1629ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149584"
---
# <a name="safeintexception-class"></a>SafeIntException Sınıfı

`SafeInt`Sınıfı, `SafeIntException` bir matematik işleminin neden tamamlanamadığına ilişkin olarak ' i kullanır.

> [!NOTE]
> Bu kitaplığın en son sürümü konumunda bulunur [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt) .

## <a name="syntax"></a>Syntax

```cpp
class SafeIntException;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                    | Açıklama
------------------------------------------------------- | ------------------------------------
[SafeIntException::SafeIntException](#safeintexception) | Bir `SafeIntException` nesnesi oluşturur.

## <a name="remarks"></a>Açıklamalar

[SafeInt sınıfı](safeint-class.md) , sınıfını kullanan tek sınıftır `SafeIntException` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SafeIntException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** SafeInt. h

**Ad alanı:** MSL:: Utilities

## <a name="safeintexceptionsafeintexception"></a><a name="safeintexception"></a> SafeIntException:: SafeIntException

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
