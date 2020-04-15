---
title: CComCurrency Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComCurrency
- ATLCUR/ATL::CComCurrency
- ATLCUR/ATL::CComCurrency::CComCurrency
- ATLCUR/ATL::CComCurrency::GetCurrencyPtr
- ATLCUR/ATL::CComCurrency::GetFraction
- ATLCUR/ATL::CComCurrency::GetInteger
- ATLCUR/ATL::CComCurrency::Round
- ATLCUR/ATL::CComCurrency::SetFraction
- ATLCUR/ATL::CComCurrency::SetInteger
- ATLCUR/ATL::CComCurrency::m_currency
helpviewer_keywords:
- CComCurrency class
ms.assetid: a1c3d10a-bba6-40cc-8bcf-aed9023c8a9e
ms.openlocfilehash: 541944e03e9caf6cba15612cf9e7cbbd239555ca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327939"
---
# <a name="ccomcurrency-class"></a>CComCurrency Sınıfı

`CComCurrency`bir CURRENCY nesnesi oluşturmak ve yönetmek için yöntemler ve işleçler vardır.

## <a name="syntax"></a>Sözdizimi

```
class CComCurrency
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Ccomcurrency::ccomcurrency](#ccomcurrency)|Bir `CComCurrency` nesnenin oluşturucusu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComCurrency::GetCurrencyPtr](#getcurrencyptr)|Veri `m_currency` üyesinin adresini döndürür.|
|[Ccomcurrency::GetFraction](#getfraction)|Bir `CComCurrency` nesnenin kesirli bileşenini döndürmek için bu yöntemi çağırın.|
|[CComCurrency::GetInteger](#getinteger)|Bir `CComCurrency` nesnenin tamsayı bileşenini döndürmek için bu yöntemi çağırın.|
|[Ccomcurrency::Yuvarlak](#round)|Bir `CComCurrency` nesneyi en yakın tamsayı değerine yuvarlamak için bu yöntemi çağırın.|
|[Ccomcurrency::setfraction](#setfraction)|Bir `CComCurrency` nesnenin kesirli bileşenini ayarlamak için bu yöntemi çağırın.|
|[CComCurrency::SetInteger](#setinteger)|Bir `CComCurrency` nesnenin tamsayı bileşenini ayarlamak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CComCurrency::operatör -](#operator_-)|Bu işleç bir `CComCurrency` nesne üzerinde çıkarma gerçekleştirmek için kullanılır.|
|[CComCurrency::operatör !=](#operator_neq)|Eşitsizlik için `CComCurrency` iki nesneyi karşılaştırır.|
|[CComCurrency::operatör *](#operator_star)|Bu işleç bir `CComCurrency` nesne üzerinde çarpma gerçekleştirmek için kullanılır.|
|[CComCurrency::operatör *=](#operator_star_eq)|Bu işleç bir `CComCurrency` nesne üzerinde çarpma gerçekleştirmek ve sonucu atamak için kullanılır.|
|[CComCurrency::operatör /](#operator_div)|Bu işleç bir `CComCurrency` nesne üzerinde bölme gerçekleştirmek için kullanılır.|
|[CComCurrency::operatör /=](#operator_div_eq)|Bu işleç bir `CComCurrency` nesne üzerinde bölme gerçekleştirmek ve sonucu atamak için kullanılır.|
|[CComCurrency::operatör +](#operator_add)|Bu işleç bir `CComCurrency` nesneye ekleme gerçekleştirmek için kullanılır.|
|[CComCurrency::operatör +=](#operator_add_eq)|Bu işleç bir `CComCurrency` nesneye ekleme gerçekleştirmek ve sonucu geçerli nesneye atamak için kullanılır.|
|[CComCurrency::operatör <](#operator_lt)|Bu işleç `CComCurrency` daha az belirlemek için iki nesne karşılaştırır.|
|[CComCurrency::operatör <=](#operator_lt_eq)|Bu işleç `CComCurrency` eşitliği veya daha az ını belirlemek için iki nesneyi karşılaştırır.|
|[CComCurrency::operator =](#operator_eq)|Bu işleç `CComCurrency` nesneyi yeni bir değere atar.|
|[CComCurrency::operatör -=](#operator_-_eq)|Bu işleç bir `CComCurrency` nesne üzerinde çıkarma gerçekleştirmek ve sonucu atamak için kullanılır.|
|[CComCurrency::operator ==](#operator_eq_eq)|Bu işleç `CComCurrency` eşitlik için iki nesneyi karşılaştırır.|
|[CComCurrency::operatör >](#operator_gt)|Bu işleç `CComCurrency` büyük belirlemek için iki nesne karşılaştırır.|
|[CComCurrency::operatör >=](#operator_gt_eq)|Bu işleç `CComCurrency` eşitliği veya daha büyük belirlemek için iki nesneyi karşılaştırır.|
|[CComCurrency::operatör PARA Bİrİmİ](#operator_currency)|Bir PARA BIRIMI nesnesi atar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CComCurrency::m_currency](#m_currency)|Sınıf örneğiniz tarafından oluşturulan PARA Birimi değişkeni.|

## <a name="remarks"></a>Açıklamalar

`CComCurrency`CURRENCY veri türü için bir sarmalayıcıdır. PARA BIRIMI, 10.000 ölçeklenmiş 8 baytlık iki tamamlayıcı bir tümsek değeri olarak uygulanır. Bu ondalık noktanın solunda 15 basamak ve sağda 4 basamak olan sabit nokta numarası verir. PARA Birimi veri türü, para içeren hesaplamalar veya doğruluğun önemli olduğu sabit noktalı hesaplamalar için son derece yararlıdır.

Sarıcı, `CComCurrency` bu sabit nokta türü için aritmetik, atama ve karşılaştırma işlemleri uygular. Desteklenen uygulamalar, sabit noktahesaplamaları sırasında oluşabilecek yuvarlama hatalarını denetlemek için seçilmiştir.

Nesne, `CComCurrency` ondalık noktanın her iki tarafındaki sayılara iki bileşen biçiminde erişim sağlar: ondalık noktanın solundaki değeri depolayan bir tamsayı bileşeni ve ondalık noktanın sağındaki değeri depolayan kesirli bir bileşen. Kesirli bileşen ,9999 (CY_MIN_FRACTION) ile +9999 (CY_MAX_FRACTION) arasında tamsayı değeri olarak dahili olarak depolanır. [CComCurrency::GetFraction](#getfraction) 10000 (CY_SCALE) faktörüyle ölçeklenen bir değeri döndürür.

Bir `CComCurrency` nesnenin tamsayı ve kesirli bileşenlerini belirtirken, kesirli bileşenin 0 ile 9999 aralığındabir sayı olduğunu unutmayın. Bu, ondalık noktadan sonra yalnızca iki önemli basamak kullanarak tutarları ifade eden ABD doları gibi bir para birimiyle uğraşırken önemlidir. Son iki basamak görüntülenmese bile, bunlar dikkate alınmalıdır.

|Değer|Olası CComCurrency atamaları|
|-----------|---------------------------------------|
|10,50 $|CComCurrency(10.5000) *veya* CComCurrency(10,50)|
|10,05 $|CComCurrency(10.500) *veya* CComCurrency(10,05)|

CY_MIN_FRACTION, CY_MAX_FRACTION ve CY_SCALE değerleri atlcur.h'de tanımlanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcur.h

## <a name="ccomcurrencyccomcurrency"></a><a name="ccomcurrency"></a>Ccomcurrency::ccomcurrency

Oluşturucu.

```
CComCurrency() throw();
CComCurrency(const CComCurrency& curSrc) throw();
CComCurrency(CURRENCY cySrc) throw();
CComCurrency(DECIMAL dSrc);
CComCurrency(ULONG ulSrc);
CComCurrency(USHORT usSrc);
CComCurrency(CHAR cSrc);
CComCurrency(DOUBLE dSrc);
CComCurrency(FLOAT fSrc);
CComCurrency(LONG lSrc);
CComCurrency(SHORT sSrc);
CComCurrency(BYTE bSrc);
CComCurrency(LONGLONG nInteger, SHORT nFraction);
explicit CComCurrency(LPDISPATCH pDispSrc);
explicit CComCurrency(const VARIANT& varSrc);
explicit CComCurrency(LPCWSTR szSrc);
explicit CComCurrency(LPCSTR szSrc);
```

### <a name="parameters"></a>Parametreler

*curSrc*<br/>
Varolan bir `CComCurrency` nesnesi.

*cySrc*<br/>
Para birimi türünde bir değişken.

*bSrc*, *dSrc*, *fSrc*, *lSrc*, *sSrc*, *ulSrc, usSrc*<br/>
Üye değişkene `m_currency`verilen ilk değer.

*Csrc*<br/>
Üye değişkene `m_currency`verilen ilk değeri içeren bir karakter.

*nInteger*, *nFraction*<br/>
İlk parasal değerin tümseci ve kesirli bileşenleri. Daha fazla bilgi için [CComCurrency](../../atl/reference/ccomcurrency-class.md) genel görünümüne bakın.

*pDispSrc*<br/>
Bir `IDispatch` işaretçi.

*varSrc*<br/>
Tür VARYANT bir değişken. Dönüştürme gerçekleştirmek için geçerli iş parçacığının yerel bilgisayarı kullanılır.

*szSrc*<br/>
İlk değeri içeren Bir Unicode veya ANSI dizesi. Dönüştürme gerçekleştirmek için geçerli iş parçacığının yerel bilgisayarı kullanılır.

### <a name="remarks"></a>Açıklamalar

Oluşturucu [CComCurrency başlangıç değerini ayarlar::m_currency](#m_currency)ve tamsayılar, dizeleri, kayan nokta numaraları, PARA Birimi değişkenleri ve diğer `CComCurrency` nesneler de dahil olmak üzere veri türleri geniş bir yelpazede kabul eder. Değer sağlanmadıysa, `m_currency` 0 olarak ayarlanır.

Taşma gibi bir hata durumunda, boş bir özel durum belirtimi **(throw()** `AtlThrow` olmayan yapıcılar hatayı açıklayan bir HRESULT ile çağrı kurarlar.

Bir değer atamak için kayan nokta veya çift `CComCurrency(10.50)` değerleri `CComCurrency(10,5000)` kullanırken, eşdeğer ve değil. `CComCurrency(10,50)`

## <a name="ccomcurrencygetcurrencyptr"></a><a name="getcurrencyptr"></a>CComCurrency::GetCurrencyPtr

Veri `m_currency` üyesinin adresini döndürür.

```
CURRENCY* GetCurrencyPtr() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Veri `m_currency` üyesinin adresini verir

## <a name="ccomcurrencygetfraction"></a><a name="getfraction"></a>Ccomcurrency::GetFraction

Nesnenin kesirli bileşenini döndürmek `CComCurrency` için bu yöntemi çağırın.

```
SHORT GetFraction() const;
```

### <a name="return-value"></a>Dönüş Değeri

Veri üyesinin kesirli bileşenini `m_currency` döndürür.

### <a name="remarks"></a>Açıklamalar

Kesirli bileşen -9999 (CY_MIN_FRACTION) ile +9999 (CY_MAX_FRACTION) arasında 4 basamaklı tamsayı değeridir. `GetFraction`10000 (CY_SCALE) ölçeğine göre ölçeklenen bu değeri döndürür. CY_MIN_FRACTION, CY_MAX_FRACTION ve CY_SCALE değerleri atlcur.h'de tanımlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#50](../../atl/codesnippet/cpp/ccomcurrency-class_1.cpp)]

## <a name="ccomcurrencygetinteger"></a><a name="getinteger"></a>CComCurrency::GetInteger

Bir `CComCurrency` nesnenin tamsayı bileşenini almak için bu yöntemi arayın.

```
LONGLONG GetInteger() const;
```

### <a name="return-value"></a>Dönüş Değeri

Veri üyesinin tümseci bileşenini `m_currency` döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#51](../../atl/codesnippet/cpp/ccomcurrency-class_2.cpp)]

## <a name="ccomcurrencym_currency"></a><a name="m_currency"></a>CComCurrency::m_currency

PARA Birimi veri üyesi.

```
CURRENCY m_currency;
```

### <a name="remarks"></a>Açıklamalar

Bu üye, bu sınıfın yöntemleri tarafından erişilen ve manipüle edilen para birimini tutar.

## <a name="ccomcurrencyoperator--"></a><a name="operator_-"></a>CComCurrency::operatör -

Bu işleç bir `CComCurrency` nesne üzerinde çıkarma gerçekleştirmek için kullanılır.

```
CComCurrency operator-() const;
CComCurrency operator-(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Cur*<br/>
Bir `CComCurrency` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Çıkarma `CComCurrency` sonucunu temsil eden bir nesne döndürür. Taşma gibi bir hata durumunda, bu işleç `AtlThrow` hatayı açıklayan bir HRESULT ile çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#55](../../atl/codesnippet/cpp/ccomcurrency-class_3.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_neq"></a>CComCurrency::operatör !=

Bu işleç eşitsizlik için iki nesneyi karşılaştırır.

```
bool operator!= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Cur*<br/>
Karşılaştırılacak `CComCurrency` nesne.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe `CComCurrency` nesneye eşit değilse TRUE döndürür; aksi takdirde, YANLIŞ.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#56](../../atl/codesnippet/cpp/ccomcurrency-class_4.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_star"></a>CComCurrency::operatör *

Bu işleç bir `CComCurrency` nesne üzerinde çarpma gerçekleştirmek için kullanılır.

```
CComCurrency operator*(long nOperand) const;
CComCurrency operator*(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*nOperand*<br/>
Çarpan.

*Cur*<br/>
Çarpan `CComCurrency` olarak kullanılan nesne.

### <a name="return-value"></a>Dönüş Değeri

Çarpma `CComCurrency` nın sonucunu temsil eden bir nesne döndürür. Taşma gibi bir hata durumunda, bu işleç `AtlThrow` hatayı açıklayan bir HRESULT ile çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#57](../../atl/codesnippet/cpp/ccomcurrency-class_5.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_star_eq"></a>CComCurrency::operatör\*=

Bu işleç bir `CComCurrency` nesne üzerinde çarpma gerçekleştirmek ve sonucu atamak için kullanılır.

```
const CComCurrency& operator*= (long nOperand);
const CComCurrency& operator*= (const CComCurrency& cur);
```

### <a name="parameters"></a>Parametreler

*nOperand*<br/>
Çarpan.

*Cur*<br/>
Çarpan `CComCurrency` olarak kullanılan nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CComCurrency` nesneyi döndürür. Taşma gibi bir hata durumunda, bu işleç `AtlThrow` hatayı açıklayan bir HRESULT ile çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#58](../../atl/codesnippet/cpp/ccomcurrency-class_6.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_div"></a>CComCurrency::operatör /

Bu işleç bir `CComCurrency` nesne üzerinde bölme gerçekleştirmek için kullanılır.

```
CComCurrency operator/(long nOperand) const;
```

### <a name="parameters"></a>Parametreler

*nOperand*<br/>
Bölen.

### <a name="return-value"></a>Dönüş Değeri

Bölünme `CComCurrency` sonucunu temsil eden bir nesne döndürür. Bölen 0 ise, bir assert hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#59](../../atl/codesnippet/cpp/ccomcurrency-class_7.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_div_eq"></a>CComCurrency::operatör /=

Bu işleç bir `CComCurrency` nesne üzerinde bölme gerçekleştirmek ve sonucu atamak için kullanılır.

```
const CComCurrency& operator/= (long nOperand);
```

### <a name="parameters"></a>Parametreler

*nOperand*<br/>
Bölen.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CComCurrency` nesneyi döndürür. Bölen 0 ise, bir assert hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#60](../../atl/codesnippet/cpp/ccomcurrency-class_8.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_add"></a>CComCurrency::operatör +

Bu işleç bir `CComCurrency` nesneye ekleme gerçekleştirmek için kullanılır.

```
CComCurrency operator+(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Cur*<br/>
Özgün `CComCurrency` nesneye eklenecek nesne.

### <a name="return-value"></a>Dönüş Değeri

Ekleme `CComCurrency` sonucunu temsil eden bir nesne döndürür. Taşma gibi bir hata durumunda, bu işleç `AtlThrow` hatayı açıklayan bir HRESULT ile çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#61](../../atl/codesnippet/cpp/ccomcurrency-class_9.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_add_eq"></a>CComCurrency::operatör +=

Bu işleç bir `CComCurrency` nesneye ekleme gerçekleştirmek ve sonucu geçerli nesneye atamak için kullanılır.

```
const CComCurrency& operator+= (const CComCurrency& cur);
```

### <a name="parameters"></a>Parametreler

*Cur*<br/>
`CComCurrency` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CComCurrency` nesneyi döndürür. Taşma gibi bir hata durumunda, bu işleç `AtlThrow` hatayı açıklayan bir HRESULT ile çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#62](../../atl/codesnippet/cpp/ccomcurrency-class_10.cpp)]

## <a name="ccomcurrencyoperator-lt"></a><a name="operator_lt"></a>CComCurrency::operatör&lt;

Bu işleç `CComCurrency` daha az belirlemek için iki nesne karşılaştırır.

```
bool operator<(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Cur*<br/>
Bir `CComCurrency` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne ikinciden küçükse TRUE döndürür, aksi takdirde FALSE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#63](../../atl/codesnippet/cpp/ccomcurrency-class_11.cpp)]

## <a name="ccomcurrencyoperator-lt"></a><a name="operator_lt_eq"></a>CComCurrency::operatör&lt;=

Bu işleç `CComCurrency` eşitliği veya daha az ını belirlemek için iki nesneyi karşılaştırır.

```
bool operator<= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Cur*<br/>
Bir `CComCurrency` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne ikinciden küçük veya eşitse TRUE döndürür, aksi takdirde FALSE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#64](../../atl/codesnippet/cpp/ccomcurrency-class_12.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_eq"></a>CComCurrency::operator =

Bu işleç `CComCurrency` nesneyi yeni bir değere atar.

```
const CComCurrency& operator= (const CComCurrency& curSrc) throw();
const CComCurrency& operator= (CURRENCY cySrc) throw();
const CComCurrency& operator= (FLOAT fSrc);
const CComCurrency& operator= (SHORT sSrc);
const CComCurrency& operator= (LONG lSrc);
const CComCurrency& operator= (BYTE bSrc);
const CComCurrency& operator= (USHORT usSrc);
const CComCurrency& operator= (DOUBLE dSrc);
const CComCurrency& operator= (CHAR cSrc);
const CComCurrency& operator= (ULONG ulSrc);
const CComCurrency& operator= (DECIMAL dSrc);
```

### <a name="parameters"></a>Parametreler

*curSrc*<br/>
Bir `CComCurrency` nesnesi.

*cySrc*<br/>
Para birimi türünde bir değişken.

*sSrc*, *fSrc*, *lSrc*, *bSrc*, *usSrc*, *dSrc*, *cSrc*, *ulSrc*, *dSrc*<br/>
`CComCurrency` Nesneye atamak için sayısal değer.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CComCurrency` nesneyi döndürür. Taşma gibi bir hata durumunda, bu işleç `AtlThrow` hatayı açıklayan bir HRESULT ile çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#65](../../atl/codesnippet/cpp/ccomcurrency-class_13.cpp)]

## <a name="ccomcurrencyoperator--"></a><a name="operator_-_eq"></a>CComCurrency::operatör -=

Bu işleç bir `CComCurrency` nesne üzerinde çıkarma gerçekleştirmek ve sonucu atamak için kullanılır.

```
const CComCurrency& operator-= (const CComCurrency& cur);
```

### <a name="parameters"></a>Parametreler

*Cur*<br/>
Bir `CComCurrency` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CComCurrency` nesneyi döndürür. Taşma gibi bir hata durumunda, bu işleç `AtlThrow` hatayı açıklayan bir HRESULT ile çağırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#66](../../atl/codesnippet/cpp/ccomcurrency-class_14.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_eq_eq"></a>CComCurrency::operator ==

Bu işleç `CComCurrency` eşitlik için iki nesneyi karşılaştırır.

```
bool operator== (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Cur*<br/>
Karşılaştırılacak `CComCurrency` nesne.

### <a name="return-value"></a>Dönüş Değeri

Nesneler eşitse (diğer bir deyişle, `m_currency` her iki nesnede de tamsayı ve kesirli veri üyeleri aynı değere sahipse), FALSE döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#67](../../atl/codesnippet/cpp/ccomcurrency-class_15.cpp)]

## <a name="ccomcurrencyoperator-gt"></a><a name="operator_gt"></a>CComCurrency::operatör&gt;

Bu işleç `CComCurrency` büyük belirlemek için iki nesne karşılaştırır.

```
bool operator>(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Cur*<br/>
Bir `CComCurrency` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne ikinciden büyükse TRUE döndürür, aksi takdirde FALSE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#68](../../atl/codesnippet/cpp/ccomcurrency-class_16.cpp)]

## <a name="ccomcurrencyoperator-gt"></a><a name="operator_gt_eq"></a>CComCurrency::operatör&gt;=

Bu işleç `CComCurrency` eşitliği veya daha büyük belirlemek için iki nesneyi karşılaştırır.

```
bool operator>= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Cur*<br/>
Bir `CComCurrency` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne ikinciden büyük veya eşitse TRUE döndürür, aksi takdirde FALSE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#69](../../atl/codesnippet/cpp/ccomcurrency-class_17.cpp)]

## <a name="ccomcurrencyoperator-currency"></a><a name="operator_currency"></a>CComCurrency::operatör PARA Bİrİmİ

Bu işleçler, `CComCurrency` bir nesneyi PARA Birimi veri türüne dökmek için kullanılır.

```
operator CURRENCY&() throw();
operator const CURRENCY&() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir PARA BIRIMI nesnesine başvuru verir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#70](../../atl/codesnippet/cpp/ccomcurrency-class_18.cpp)]

## <a name="ccomcurrencyround"></a><a name="round"></a>Ccomcurrency::Yuvarlak

Para birimini belirli sayıda ondalık basamaklara yuvarlamak için bu yöntemi çağırın.

```
HRESULT Roundint nDecimals);
```

### <a name="parameters"></a>Parametreler

*nOncimals*<br/>
0 ile 4 aralığında `m_currency` yuvarlanacak basamak sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#52](../../atl/codesnippet/cpp/ccomcurrency-class_19.cpp)]

## <a name="ccomcurrencysetfraction"></a><a name="setfraction"></a>Ccomcurrency::setfraction

Bir `CComCurrency` nesnenin kesirli bileşenini ayarlamak için bu yöntemi çağırın.

```
HRESULT SetFraction(SHORT nFraction);
```

### <a name="parameters"></a>Parametreler

*nKıfraksiyon*<br/>
Veri üyesinin kesirli bileşenine `m_currency` atanacak değer. Kesirli bileşenin işareti tamsayı bileşeniyle aynı olmalı ve değer -9999 (CY_MIN_FRACTION) ile +9999 (CY_MAX_FRACTION) aralığında olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#53](../../atl/codesnippet/cpp/ccomcurrency-class_20.cpp)]

## <a name="ccomcurrencysetinteger"></a><a name="setinteger"></a>CComCurrency::SetInteger

Bir `CComCurrency` nesnenin tamsayı bileşenini ayarlamak için bu yöntemi çağırın.

```
HRESULT SetInteger(LONGLONG nInteger);
```

### <a name="parameters"></a>Parametreler

*nInteger*<br/>
Veri üyesinin tümseci bileşenine `m_currency` atanacak değer. Birsonraki bileşenin işareti, varolan kesirli bileşenin işaretiyle eşleşmelidir.

*nInteger* dahil CY_MAX_INTEGER CY_MIN_INTEGER aralığında olmalıdır. Bu değerler atlcur.h olarak tanımlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#54](../../atl/codesnippet/cpp/ccomcurrency-class_21.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[COleCurrency Sınıfı](../../mfc/reference/colecurrency-class.md)<br/>
[Para birimi](/windows/win32/api/wtypes/ns-wtypes-cy~r1)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
