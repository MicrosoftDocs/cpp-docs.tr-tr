---
title: CComSafeArrayBound Sınıfı
ms.date: 05/06/2019
f1_keywords:
- CComSafeArrayBound
- ATLSAFE/ATL::CComSafeArrayBound
- ATLSAFE/ATL::GetCount
- ATLSAFE/ATL::GetLowerBound
- ATLSAFE/ATL::GetUpperBound
- ATLSAFE/ATL::SetCount
- ATLSAFE/ATL::SetLowerBound
helpviewer_keywords:
- CComSafeArrayBound class
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
ms.openlocfilehash: 2c2f8b787e5366ec893538a88049f6f53dc35caf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327378"
---
# <a name="ccomsafearraybound-class"></a>CComSafeArrayBound Sınıfı

Bu sınıf [SAFEARRAYBOUND](/windows/win32/api/oaidl/ns-oaidl-safearraybound) yapısı için bir sarmalayıcıdır.

## <a name="syntax"></a>Sözdizimi

```
class CComSafeArrayBound : public SAFEARRAYBOUND
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CcomsafeArrayBound](#ccomsafearraybound)|Oluşturucu.|
|[GetCount](#getcount)|Öğe sayısını döndürmek için bu yöntemi arayın.|
|[Getlowerbound](#getlowerbound)|Alt sınırı döndürmek için bu yöntemi arayın.|
|[Getupperbound](#getupperbound)|Üst sınırı döndürmek için bu yöntemi arayın.|
|[SetCount](#setcount)|Öğe sayısını ayarlamak için bu yöntemi çağırın.|
|[SetLowerBound](#setlowerbound)|Alt sınırı ayarlamak için bu yöntemi arayın.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#operator_eq)|Yeni `CComSafeArrayBound` bir değer ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf `SAFEARRAYBOUND` [CComSafeArray](../../atl/reference/ccomsafearray-class.md)tarafından kullanılan yapı için bir sarmalayıcıdır. Bir `CComSafeArray` nesnenin tek bir boyutunun üst ve alt sınırlarını ve içerdiği öğe sayısını sorgulama ve ayarlama yöntemleri sağlar. Çok boyutlu `CComSafeArray` bir nesne, `CComSafeArrayBound` her boyut için bir dizi nesne kullanır. Bu nedenle, [GetCount](#getcount)gibi yöntemleri kullanırken, bu yöntemin çok boyutlu bir dizideki toplam öğe sayısını döndürmeyeceğini unutmayın.

**Üstbilgi:** atlsafe.h

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsafe.h

## <a name="ccomsafearrayboundccomsafearraybound"></a><a name="ccomsafearraybound"></a>Ccomsafearraybound::ccomsafearraybound

Oluşturucu.

```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```

### <a name="parameters"></a>Parametreler

*ulCount*<br/>
Dizideki öğelerin sayısı

*lLowerBound*<br/>
Dizinin numaralandığı alt sınır.

### <a name="remarks"></a>Açıklamalar

Diziye bir C++ programından erişilecekse, alt sınır 0 olarak tanımlanması önerilir. Dizi Visual Basic gibi diğer dillerde kullanılacaksa, farklı bir alt sınır değeri kullanmak tercih edilebilir.

## <a name="ccomsafearrayboundgetcount"></a><a name="getcount"></a>Ccomsafearraybound::getcount

Öğe sayısını döndürmek için bu yöntemi arayın.

```
ULONG GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Öğe sayısını verir.

### <a name="remarks"></a>Açıklamalar

İlişkili `CComSafeArray` nesne çok boyutlu bir diziyi temsil ederse, bu yöntem yalnızca en doğru boyuttaki toplam öğe sayısını döndürecektir. Toplam öğe sayısını elde etmek için [CComSafeArray::GetCount'ı](../../atl/reference/ccomsafearray-class.md#getcount) kullanın.

## <a name="ccomsafearrayboundgetlowerbound"></a><a name="getlowerbound"></a>Ccomsafearraybound::GetLowerBound

Alt sınırı döndürmek için bu yöntemi arayın.

```
LONG GetLowerBound() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin alt sınırını `CComSafeArrayBound` döndürür.

## <a name="ccomsafearrayboundgetupperbound"></a><a name="getupperbound"></a>Ccomsafearraybound::Getupperbound

Üst sınırı döndürmek için bu yöntemi arayın.

```
LONG GetUpperBound() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin üst sınırını `CComSafeArrayBound` döndürür.

### <a name="remarks"></a>Açıklamalar

Üst sınır, öğelerin sayısına ve alt sınır değerine bağlıdır. Örneğin, alt sınır 0 ve eleman sayısı 10 ise, üst sınır otomatik olarak 9 olarak ayarlanır.

## <a name="ccomsafearrayboundoperator-"></a><a name="operator_eq"></a>CComSafeArrayBound::operatör =

Yeni `CComSafeArrayBound` bir değer ayarlar.

```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```

### <a name="parameters"></a>Parametreler

*Bağlı*<br/>
Bir `CComSafeArrayBound` nesnesi.

*ulCount*<br/>
Öğelerin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Nesneye bir `CComSafeArrayBound` işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Nesne `CComSafeArrayBound` varolan `CComSafeArrayBound`bir kullanarak veya eleman sayısını sağlayarak atanabilir, bu durumda alt sınır varsayılan olarak 0 olarak ayarlanır.

## <a name="ccomsafearrayboundsetcount"></a><a name="setcount"></a>Ccomsafearraybound::setsayısı

Öğe sayısını ayarlamak için bu yöntemi çağırın.

```
ULONG SetCount(ULONG ulCount) throw();
```

### <a name="parameters"></a>Parametreler

*ulCount*<br/>
Öğelerin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki `CComSafeArrayBound` öğe sayısını döndürür.

## <a name="ccomsafearrayboundsetlowerbound"></a><a name="setlowerbound"></a>Ccomsafearraybound::setlowerbound

Alt sınırı ayarlamak için bu yöntemi arayın.

```
LONG SetLowerBound(LONG lLowerBound) throw();
```

### <a name="parameters"></a>Parametreler

*lLowerBound*<br/>
Alt sınır.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin yeni alt `CComSafeArrayBound` sınırını döndürür.

### <a name="remarks"></a>Açıklamalar

Diziye Visual C++ programından erişilecekse, alt sınır 0 olarak tanımlanması önerilir. Dizi Visual Basic gibi diğer dillerde kullanılacaksa, farklı bir alt sınır değeri kullanmak tercih edilebilir.

Üst sınır, öğelerin sayısına ve alt sınır değerine bağlıdır. Örneğin, alt sınır 0 ve eleman sayısı 10 ise, üst sınır otomatik olarak 9 olarak ayarlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
