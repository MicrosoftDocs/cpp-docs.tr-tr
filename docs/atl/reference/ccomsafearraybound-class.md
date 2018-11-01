---
title: CComSafeArrayBound sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: d57e038a4ebc55d08b4518f25e37b4f2d9cee05d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429222"
---
# <a name="ccomsafearraybound-class"></a>CComSafeArrayBound sınıfı

Bu sınıf için bir sarmalayıcı olan bir [SAFEARRAYBOUND](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagsafearraybound) yapısı.

## <a name="syntax"></a>Sözdizimi

```
class CComSafeArrayBound : public SAFEARRAYBOUND
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CComSafeArrayBound](#ccomsafearraybound)|Oluşturucu.|
|[GetCount](#getcount)|Öğe sayısını döndürmek için bu yöntemi çağırın.|
|[GetLowerBound](#getlowerbound)|Alt sınır döndürmek için bu yöntemi çağırın.|
|[GetUpperBound](#getupperbound)|Üst sınır döndürmek için bu yöntemi çağırın.|
|[SetCount](#setcount)|Öğe sayısını ayarlamak için bu yöntemi çağırın.|
|[SetLowerBound](#setlowerbound)|Alt sınır ayarlamak için bu yöntemi çağırın.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#operator_eq)|Kümeleri `CComSafeArrayBound` yeni bir değer.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf için bir sarmalayıcı olan `SAFEARRAYBOUND` yapısı tarafından kullanılan [CComSafeArray](../../atl/reference/ccomsafearray-class.md). Sorgulama ve tek bir boyutunun üst ve alt sınırları ayarlama için yöntemleri sağlar bir `CComSafeArray` nesne ve içerdiği öğelerin sayısı. Bir çok boyutlu `CComSafeArray` nesnesini kullanan bir dizi `CComSafeArrayBound` nesneleri, her boyut için bir tane. Bu nedenle, yöntemler gibi kullanırken [GetCount](#getcount), bu yöntem çok boyutlu bir dizideki öğelerin toplam sayısını döndürmez unutmayın.

**Başlık:** atlsafe.h

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsafe.h

##  <a name="ccomsafearraybound"></a>  CComSafeArrayBound::CComSafeArrayBound

Oluşturucu.

```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```

### <a name="parameters"></a>Parametreler

*ulCount*<br/>
Dizideki öğelerin sayısı

*lLowerBound*<br/>
Dizi numaralandırılmış gelen alt sınır.

### <a name="remarks"></a>Açıklamalar

Visual C++ program erişilecek dizi ise, alt sınırı 0 tanımlanması önerilir. Visual Basic gibi diğer dilleri ile kullanılmak üzere bir dizi ise, farklı alt sınır değeri kullanılması tercih olabilir.

##  <a name="getcount"></a>  CComSafeArrayBound::GetCount

Öğe sayısını döndürmek için bu yöntemi çağırın.

```
ULONG GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Varsa ilişkili `CComSafeArray` nesnesini temsil eder, çok boyutlu bir dizi, bu yöntem yalnızca en sağdaki boyuta öğelerin toplam sayısını döndürür. Kullanım [CComSafeArray::GetCount](../../atl/reference/ccomsafearray-class.md#getcount) öğelerin toplam sayısını elde edilir.

##  <a name="getlowerbound"></a>  CComSafeArrayBound::GetLowerBound

Alt sınır döndürmek için bu yöntemi çağırın.

```
LONG GetLowerBound() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Alt sınırı döndürür `CComSafeArrayBound` nesne.

##  <a name="getupperbound"></a>  CComSafeArrayBound::GetUpperBound

Üst sınır döndürmek için bu yöntemi çağırın.

```
LONG GetUpperBound() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Üst sınırını döndürür `CComSafeArrayBound` nesne.

### <a name="remarks"></a>Açıklamalar

Üst sınır öğeler ve alt sınır değeri sayısına bağlıdır. Örneğin, alt sınırı 0'dır ve 10 öğe sayısını ise, üst sınırı otomatik 9'a ayarlanacaktır.

##  <a name="operator_eq"></a>  CComSafeArrayBound::operator =

Kümeleri `CComSafeArrayBound` yeni bir değer.

```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```

### <a name="parameters"></a>Parametreler

*bağlı*<br/>
A `CComSafeArrayBound` nesne.

*ulCount*<br/>
Öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi döndürür `CComSafeArrayBound` nesne.

### <a name="remarks"></a>Açıklamalar

`CComSafeArrayBound` Var olan bir nesne atanabilir `CComSafeArrayBound`, ya da hangi durumu alt sınırı 0 olarak ayarlanmış varsayılan olarak, öğelerin sayısını belirtin.

##  <a name="setcount"></a>  CComSafeArrayBound::SetCount

Öğe sayısını ayarlamak için bu yöntemi çağırın.

```
ULONG SetCount(ULONG ulCount) throw();
```

### <a name="parameters"></a>Parametreler

*ulCount*<br/>
Öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

İçindeki öğelerin sayısını döndürür `CComSafeArrayBound` nesne.

##  <a name="setlowerbound"></a>  CComSafeArrayBound::SetLowerBound

Alt sınır ayarlamak için bu yöntemi çağırın.

```
LONG SetLowerBound(LONG lLowerBound) throw();
```

### <a name="parameters"></a>Parametreler

*lLowerBound*<br/>
Alt sınır.

### <a name="return-value"></a>Dönüş Değeri

Yeni alt sınırı döndürür `CComSafeArrayBound` nesne.

### <a name="remarks"></a>Açıklamalar

Visual C++ program erişilecek dizi ise, alt sınırı 0 tanımlanması önerilir. Visual Basic gibi diğer dilleri ile kullanılmak üzere bir dizi ise, farklı alt sınır değeri kullanılması tercih olabilir.

Üst sınır öğeler ve alt sınır değeri sayısına bağlıdır. Örneğin, alt sınırı 0'dır ve 10 öğe sayısını ise, üst sınırı otomatik 9'a ayarlanacaktır.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
