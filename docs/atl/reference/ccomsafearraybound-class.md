---
description: 'Daha fazla bilgi edinin: CComSafeArrayBound Class'
title: CComSafeArrayBound sınıfı
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
ms.openlocfilehash: 09672e4a74db8998b887a093e0f15202903cfcf9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142259"
---
# <a name="ccomsafearraybound-class"></a>CComSafeArrayBound sınıfı

Bu sınıf, [safearraybound](/windows/win32/api/oaidl/ns-oaidl-safearraybound) yapısına yönelik bir sarmalayıcıdır.

## <a name="syntax"></a>Syntax

```
class CComSafeArrayBound : public SAFEARRAYBOUND
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|İşlev|Açıklama|
|-|-|
|[CComSafeArrayBound](#ccomsafearraybound)|Oluşturucu.|
|[GetCount](#getcount)|Öğe sayısını döndürmek için bu yöntemi çağırın.|
|[Getharfe göre sınırı](#getlowerbound)|Alt sınır döndürmek için bu yöntemi çağırın.|
|[Getüstsınırı](#getupperbound)|Üst sınırı döndürmek için bu yöntemi çağırın.|
|[SetCount](#setcount)|Öğe sayısını ayarlamak için bu yöntemi çağırın.|
|[Setalmi sınırı](#setlowerbound)|Alt sınır ayarlamak için bu yöntemi çağırın.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#operator_eq)|' İ `CComSafeArrayBound` Yeni bir değere ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, `SAFEARRAYBOUND` [CComSafeArray](../../atl/reference/ccomsafearray-class.md)tarafından kullanılan yapı için bir sarmalayıcıdır. Bir nesnenin tek boyutunun `CComSafeArray` ve içerdiği öğe sayısının üst ve alt sınırlarını sorgulamak ve ayarlamak için yöntemler sağlar. Çok boyutlu bir `CComSafeArray` nesne `CComSafeArrayBound` , her boyut için bir dizi nesne kullanır. Bu nedenle, [GetCount](#getcount)gibi yöntemleri kullanırken, bu yöntemin çok boyutlu bir dizideki toplam öğe sayısını döndürmeyeceği farkında olun.

**Üstbilgi:** atlsafe. h

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsafe. h

## <a name="ccomsafearrayboundccomsafearraybound"></a><a name="ccomsafearraybound"></a> CComSafeArrayBound::CComSafeArrayBound

Oluşturucu.

```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```

### <a name="parameters"></a>Parametreler

*ulCount*<br/>
Dizideki öğelerin sayısı

*Lall sınırı*<br/>
Dizinin numaralandırıldığı alt sınır.

### <a name="remarks"></a>Açıklamalar

Diziye bir C++ programından erişiliyorsa, alt sınırın 0 olarak tanımlanması önerilir. Dizi Visual Basic gibi diğer dillerle birlikte kullanılacaksa, farklı bir alt sınır değeri kullanılması tercih edilebilir.

## <a name="ccomsafearrayboundgetcount"></a><a name="getcount"></a> CComSafeArrayBound:: GetCount

Öğe sayısını döndürmek için bu yöntemi çağırın.

```
ULONG GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Öğe sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

İlişkili `CComSafeArray` nesne bir çok boyutlu diziyi temsil ediyorsa, bu yöntem yalnızca en sağdaki boyuttaki öğelerin toplam sayısını döndürür. Toplam öğe sayısını almak için [CComSafeArray:: GetCount](../../atl/reference/ccomsafearray-class.md#getcount) kullanın.

## <a name="ccomsafearrayboundgetlowerbound"></a><a name="getlowerbound"></a> CComSafeArrayBound:: Getharfe dayalı

Alt sınır döndürmek için bu yöntemi çağırın.

```
LONG GetLowerBound() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin alt sınırını döndürür `CComSafeArrayBound` .

## <a name="ccomsafearrayboundgetupperbound"></a><a name="getupperbound"></a> CComSafeArrayBound:: Getüstsınırı

Üst sınırı döndürmek için bu yöntemi çağırın.

```
LONG GetUpperBound() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin üst sınırını döndürür `CComSafeArrayBound` .

### <a name="remarks"></a>Açıklamalar

Üst sınır, öğe sayısına ve alt sınır değerine bağlıdır. Örneğin, alt sınır 0 ise ve öğe sayısı 10 ise, üst sınır otomatik olarak 9 olarak ayarlanır.

## <a name="ccomsafearrayboundoperator-"></a><a name="operator_eq"></a> CComSafeArrayBound:: operator =

' İ `CComSafeArrayBound` Yeni bir değere ayarlar.

```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```

### <a name="parameters"></a>Parametreler

*bağlı*<br/>
Bir `CComSafeArrayBound` nesnesi.

*ulCount*<br/>
Öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Nesneye bir işaretçi döndürür `CComSafeArrayBound` .

### <a name="remarks"></a>Açıklamalar

`CComSafeArrayBound`Nesne, var olan `CComSafeArrayBound` veya öğe sayısını sağlayarak atanabilir veya alt sınır varsayılan olarak 0 olarak ayarlanır.

## <a name="ccomsafearrayboundsetcount"></a><a name="setcount"></a> CComSafeArrayBound:: SetCount

Öğe sayısını ayarlamak için bu yöntemi çağırın.

```
ULONG SetCount(ULONG ulCount) throw();
```

### <a name="parameters"></a>Parametreler

*ulCount*<br/>
Öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki öğe sayısını döndürür `CComSafeArrayBound` .

## <a name="ccomsafearrayboundsetlowerbound"></a><a name="setlowerbound"></a> CComSafeArrayBound:: Setalni sınırı

Alt sınır ayarlamak için bu yöntemi çağırın.

```
LONG SetLowerBound(LONG lLowerBound) throw();
```

### <a name="parameters"></a>Parametreler

*Lall sınırı*<br/>
Alt sınır.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin yeni alt sınırını döndürür `CComSafeArrayBound` .

### <a name="remarks"></a>Açıklamalar

Diziye bir Visual C++ programından erişiliyorsa, alt sınırın 0 olarak tanımlanması önerilir. Dizi Visual Basic gibi diğer dillerle birlikte kullanılacaksa, farklı bir alt sınır değeri kullanılması tercih edilebilir.

Üst sınır, öğe sayısına ve alt sınır değerine bağlıdır. Örneğin, alt sınır 0 ise ve öğe sayısı 10 ise, üst sınır otomatik olarak 9 olarak ayarlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
