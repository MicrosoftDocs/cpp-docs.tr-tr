---
title: CComCurrency sınıfı
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
ms.openlocfilehash: 2b3c260f250fdb198c8317355628fa2fe62c44eb
ms.sourcegitcommit: 13f42c339fb7af935e3a93ac80e350d5e784c9f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2020
ms.locfileid: "87470790"
---
# <a name="ccomcurrency-class"></a>CComCurrency sınıfı

`CComCurrency`, bir para BIRIMI nesnesi oluşturmak ve yönetmek için yöntemler ve işleçler içerir.

## <a name="syntax"></a>Syntax

```
class CComCurrency
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComCurrency:: CComCurrency](#ccomcurrency)|Bir nesne için Oluşturucu `CComCurrency` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComCurrency:: GetCurrencyPtr](#getcurrencyptr)|Bir veri üyesinin adresini döndürür `m_currency` .|
|[CComCurrency:: Getkesir](#getfraction)|Bir nesnenin kesirli bileşenini döndürmek için bu yöntemi çağırın `CComCurrency` .|
|[CComCurrency:: GetInteger](#getinteger)|Bir nesnenin tamsayı bileşenini döndürmek için bu yöntemi çağırın `CComCurrency` .|
|[CComCurrency:: Round](#round)|Bir `CComCurrency` nesneyi en yakın tamsayı değerine yuvarlamak için bu yöntemi çağırın.|
|[CComCurrency:: Setkesir](#setfraction)|Bir nesnenin kesirli bileşenini ayarlamak için bu yöntemi çağırın `CComCurrency` .|
|[CComCurrency:: Setınteger](#setinteger)|Bir nesnenin tamsayı bileşenini ayarlamak için bu yöntemi çağırın `CComCurrency` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CComCurrency:: operator-](#operator_-)|Bu işleç, bir nesne üzerinde çıkarma gerçekleştirmek için kullanılır `CComCurrency` .|
|[CComCurrency:: operator! =](#operator_neq)|`CComCurrency`Eşitsizlik için iki nesneyi karşılaştırır.|
|[CComCurrency:: operator *](#operator_star)|Bu işleç, bir nesne üzerinde çarpma gerçekleştirmek için kullanılır `CComCurrency` .|
|[CComCurrency:: operator * =](#operator_star_eq)|Bu işleç, bir nesne üzerinde çarpma gerçekleştirmek `CComCurrency` ve sonuca atamak için kullanılır.|
|[CComCurrency:: operator/](#operator_div)|Bu işleç, bir nesne üzerinde bölme gerçekleştirmek için kullanılır `CComCurrency` .|
|[CComCurrency:: operator/=](#operator_div_eq)|Bu işleç, bir nesne üzerinde bölme gerçekleştirmek `CComCurrency` ve sonuca atamak için kullanılır.|
|[CComCurrency:: operator +](#operator_add)|Bu işleç, bir nesnesine ekleme yapmak için kullanılır `CComCurrency` .|
|[CComCurrency:: operator + =](#operator_add_eq)|Bu işleç, bir nesnesine ekleme yapmak `CComCurrency` ve sonucu geçerli nesneye atamak için kullanılır.|
|[CComCurrency:: operator <](#operator_lt)|Bu işleç, daha `CComCurrency` az anlamak için iki nesneyi karşılaştırır.|
|[CComCurrency:: operator <=](#operator_lt_eq)|Bu işleç `CComCurrency` , eşitlik veya daha küçük bir şekilde belirlenmesi için iki nesneyi karşılaştırır.|
|[CComCurrency:: operator =](#operator_eq)|Bu işleç, `CComCurrency` nesneyi yeni bir değere atar.|
|[CComCurrency:: operator-=](#operator_-_eq)|Bu işleç, bir nesne üzerinde çıkarma gerçekleştirmek `CComCurrency` ve sonuca atamak için kullanılır.|
|[CComCurrency:: operator = =](#operator_eq_eq)|Bu işleç, `CComCurrency` eşitlik için iki nesneyi karşılaştırır.|
|[CComCurrency:: operator >](#operator_gt)|Bu işleç `CComCurrency` , daha büyük olduğunu anlamak için iki nesneyi karşılaştırır.|
|[CComCurrency:: operator >=](#operator_gt_eq)|Bu işleç `CComCurrency` , eşitlik veya daha büyük bir şekilde belirlenmesi için iki nesneyi karşılaştırır.|
|[CComCurrency:: operator para BIRIMI](#operator_currency)|Bir para BIRIMI nesnesini yayınlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComCurrency:: m_currency](#m_currency)|Sınıf örneğiniz tarafından oluşturulan para BIRIMI değişkeni.|

## <a name="remarks"></a>Açıklamalar

`CComCurrency`, para BIRIMI veri türü için bir sarmalayıcıdır. PARA BIRIMI, 10.000 ile ölçeklendirilmiş bir 8 baytlık ikiye tamamlama tamsayı değeri olarak uygulanır. Bu, ondalık noktanın solunda 15 basamakla sabit noktalı bir sayı ve sağına 4 basamak verir. PARA BIRIMI veri türü, parayla ilgili hesaplamalar veya doğruluk açısından önemli olan sabit noktalı hesaplamalar için son derece kullanışlıdır.

`CComCurrency`Sarmalayıcı, bu sabit nokta türü için aritmetik, atama ve karşılaştırma işlemleri uygular. Desteklenen uygulamalar, sabit noktalı hesaplamalar sırasında oluşabilecek yuvarlama hatalarını denetlemek için seçilmiştir.

`CComCurrency`Nesnesi, iki bileşen biçiminde ondalık noktanın her iki tarafındaki sayılara erişim sağlar: ondalık noktanın solundaki değeri depolayan bir tamsayı bileşeni ve değeri ondalık noktanın sağına depolayan bir kesirli bileşen. Kesirli bileşen dahili olarak-9999 (CY_MIN_FRACTION) ve + 9999 (CY_MAX_FRACTION) arasında bir tamsayı değeri olarak depolanır. [CComCurrency:: Getkesir](#getfraction) yöntemi, 10000 faktörüyle (cy_scale) ölçeklendirilmiş bir değer döndürür.

Bir nesnenin tamsayı ve kesir bileşenlerini belirtirken `CComCurrency` kesirli bileşenin 0 ile 9999 aralığında bir sayı olduğunu unutmayın. Bu, ondalık ayırıcıdan sonra yalnızca iki önemli basamak kullanarak miktarları ifade eden ABD Doları gibi bir para birimi ile ilgilenirken önemlidir. Son iki basamak görüntülenmese de, bunların hesaba alınması gerekir.

|Değer|Olası CComCurrency atamaları|
|-----------|---------------------------------------|
|$10,50|CComCurrency (10, 5000) *veya* CComCurrency (10.50 olan)|
|$10,05|CComCurrency (10500) *veya* CComCurrency (10.05)|

CY_MIN_FRACTION, CY_MAX_FRACTION ve CY_SCALE değerleri atlcur. h içinde tanımlanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcur. h

## <a name="ccomcurrencyccomcurrency"></a><a name="ccomcurrency"></a>CComCurrency:: CComCurrency

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
PARA BIRIMI türünde bir değişken.

*Bsrc*, *DSRC*, *FSRC*, *lsrc*, *SSRC*, *ulsrc, ussrc*<br/>
Üye değişkenine verilen ilk değer `m_currency` .

*cSrc*<br/>
Üye değişkenine verilen ilk değeri içeren bir karakter `m_currency` .

*Nınteger*, *nkesir*<br/>
İlk parasal değerin tamsayı ve kesirli bileşenleri. Daha fazla bilgi için bkz. [CComCurrency](../../atl/reference/ccomcurrency-class.md) Overview.

*pDispSrc*<br/>
Bir `IDispatch` işaretçi.

*varSrc*<br/>
Değişken türünde bir değişken. Geçerli iş parçacığının yerel ayarı dönüştürmeyi gerçekleştirmek için kullanılır.

*szSrc*<br/>
Başlangıçtaki değeri içeren bir Unicode veya ANSI dizesi. Geçerli iş parçacığının yerel ayarı dönüştürmeyi gerçekleştirmek için kullanılır.

### <a name="remarks"></a>Açıklamalar

Oluşturucu, [CComCurrency:: m_currency](#m_currency)başlangıç değerini ayarlar ve tamsayılar, dizeler, kayan noktalı SAYıLAR, para birimi değişkenleri ve diğer nesneler dahil olmak üzere çok çeşitli veri türlerini kabul eder `CComCurrency` . Değer sağlanmazsa, `m_currency` 0 olarak ayarlanır.

Taşma gibi bir hata durumunda, oluşturucular, hatayı açıklayan bir HRESULT ile boş bir özel durum belirtimi (**throw ()**) çağrısı zorunda değildir `AtlThrow` .

Bir değer atamak için kayan nokta veya Double değerleri kullanırken, öğesinin eşdeğer olduğunu unutmayın `CComCurrency(10.50)` `CComCurrency(10,5000)` `CComCurrency(10,50)` .

## <a name="ccomcurrencygetcurrencyptr"></a><a name="getcurrencyptr"></a>CComCurrency:: GetCurrencyPtr

Bir veri üyesinin adresini döndürür `m_currency` .

```
CURRENCY* GetCurrencyPtr() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir veri üyesinin adresini döndürür `m_currency`

## <a name="ccomcurrencygetfraction"></a><a name="getfraction"></a>CComCurrency:: Getkesir

Nesnenin kesirli bileşenini döndürmek için bu yöntemi çağırın `CComCurrency` .

```
SHORT GetFraction() const;
```

### <a name="return-value"></a>Dönüş Değeri

Veri üyesinin kesirli bileşenini döndürür `m_currency` .

### <a name="remarks"></a>Açıklamalar

Kesirli bileşen-9999 (CY_MIN_FRACTION) ve + 9999 (CY_MAX_FRACTION) arasında 4 basamaklı bir tamsayı değeridir. `GetFraction`Bu değeri 10000 (CY_SCALE) ile ölçeklendirerek döndürür. CY_MIN_FRACTION, CY_MAX_FRACTION ve CY_SCALE değerleri atlcur. h içinde tanımlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#50](../../atl/codesnippet/cpp/ccomcurrency-class_1.cpp)]

## <a name="ccomcurrencygetinteger"></a><a name="getinteger"></a>CComCurrency:: GetInteger

Bir nesnenin tamsayı bileşenini almak için bu yöntemi çağırın `CComCurrency` .

```
LONGLONG GetInteger() const;
```

### <a name="return-value"></a>Dönüş Değeri

Veri üyesinin tamsayı bileşenini döndürür `m_currency` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#51](../../atl/codesnippet/cpp/ccomcurrency-class_2.cpp)]

## <a name="ccomcurrencym_currency"></a><a name="m_currency"></a>CComCurrency:: m_currency

PARA BIRIMI veri üyesi.

```
CURRENCY m_currency;
```

### <a name="remarks"></a>Açıklamalar

Bu üye, bu sınıfın yöntemleri tarafından erişilen ve yönetilen para birimini tutar.

## <a name="ccomcurrencyoperator--"></a><a name="operator_-"></a>CComCurrency:: operator-

Bu işleç, bir nesne üzerinde çıkarma gerçekleştirmek için kullanılır `CComCurrency` .

```
CComCurrency operator-() const;
CComCurrency operator-(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*geçerli*<br/>
Bir `CComCurrency` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`CComCurrency`Çıkarma sonucunu temsil eden bir nesne döndürür. Taşma gibi bir hata durumunda bu işleç, `AtlThrow` hatayı açıklayan BIR HRESULT ile çağrı yapılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#55](../../atl/codesnippet/cpp/ccomcurrency-class_3.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_neq"></a>CComCurrency:: operator! =

Bu işleç, eşitsizlik için iki nesneyi karşılaştırır.

```
bool operator!= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*geçerli*<br/>
`CComCurrency`Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe nesneye eşitse TRUE `CComCurrency` , DEĞILSE false döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#56](../../atl/codesnippet/cpp/ccomcurrency-class_4.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_star"></a>CComCurrency:: operator *

Bu işleç, bir nesne üzerinde çarpma gerçekleştirmek için kullanılır `CComCurrency` .

```
CComCurrency operator*(long nOperand) const;
CComCurrency operator*(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Noperve*<br/>
Çarpan.

*geçerli*<br/>
`CComCurrency`Çarpan olarak kullanılan nesne.

### <a name="return-value"></a>Dönüş Değeri

`CComCurrency`Çarpma sonucunu temsil eden bir nesne döndürür. Taşma gibi bir hata durumunda bu işleç, `AtlThrow` hatayı açıklayan BIR HRESULT ile çağrı yapılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#57](../../atl/codesnippet/cpp/ccomcurrency-class_5.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_star_eq"></a>CComCurrency:: işleci\*=

Bu işleç, bir nesne üzerinde çarpma gerçekleştirmek `CComCurrency` ve sonuca atamak için kullanılır.

```
const CComCurrency& operator*= (long nOperand);
const CComCurrency& operator*= (const CComCurrency& cur);
```

### <a name="parameters"></a>Parametreler

*Noperve*<br/>
Çarpan.

*geçerli*<br/>
`CComCurrency`Çarpan olarak kullanılan nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneyi döndürür `CComCurrency` . Taşma gibi bir hata durumunda bu işleç, `AtlThrow` hatayı açıklayan BIR HRESULT ile çağrı yapılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#58](../../atl/codesnippet/cpp/ccomcurrency-class_6.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_div"></a>CComCurrency:: operator/

Bu işleç, bir nesne üzerinde bölme gerçekleştirmek için kullanılır `CComCurrency` .

```
CComCurrency operator/(long nOperand) const;
```

### <a name="parameters"></a>Parametreler

*Noperve*<br/>
Bölen.

### <a name="return-value"></a>Dönüş Değeri

`CComCurrency`Bölümün sonucunu temsil eden bir nesne döndürür. Bölen 0 ise, bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#59](../../atl/codesnippet/cpp/ccomcurrency-class_7.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_div_eq"></a>CComCurrency:: operator/=

Bu işleç, bir nesne üzerinde bölme gerçekleştirmek `CComCurrency` ve sonuca atamak için kullanılır.

```
const CComCurrency& operator/= (long nOperand);
```

### <a name="parameters"></a>Parametreler

*Noperve*<br/>
Bölen.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneyi döndürür `CComCurrency` . Bölen 0 ise, bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#60](../../atl/codesnippet/cpp/ccomcurrency-class_8.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_add"></a>CComCurrency:: operator +

Bu işleç, bir nesnesine ekleme yapmak için kullanılır `CComCurrency` .

```
CComCurrency operator+(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*geçerli*<br/>
`CComCurrency`Özgün nesneye eklenecek nesne.

### <a name="return-value"></a>Dönüş Değeri

`CComCurrency`Toplama sonucunu temsil eden bir nesne döndürür. Taşma gibi bir hata durumunda bu işleç, `AtlThrow` hatayı açıklayan BIR HRESULT ile çağrı yapılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#61](../../atl/codesnippet/cpp/ccomcurrency-class_9.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_add_eq"></a>CComCurrency:: operator + =

Bu işleç, bir nesnesine ekleme yapmak `CComCurrency` ve sonucu geçerli nesneye atamak için kullanılır.

```
const CComCurrency& operator+= (const CComCurrency& cur);
```

### <a name="parameters"></a>Parametreler

*geçerli*<br/>
`CComCurrency` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneyi döndürür `CComCurrency` . Taşma gibi bir hata durumunda bu işleç, `AtlThrow` hatayı açıklayan BIR HRESULT ile çağrı yapılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#62](../../atl/codesnippet/cpp/ccomcurrency-class_10.cpp)]

## <a name="ccomcurrencyoperator-lt"></a><a name="operator_lt"></a>CComCurrency:: işleci&lt;

Bu işleç, daha `CComCurrency` az anlamak için iki nesneyi karşılaştırır.

```
bool operator<(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*geçerli*<br/>
Bir `CComCurrency` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne ikinciden küçükse TRUE, aksi takdirde FALSE döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#63](../../atl/codesnippet/cpp/ccomcurrency-class_11.cpp)]

## <a name="ccomcurrencyoperator-lt"></a><a name="operator_lt_eq"></a>CComCurrency:: işleci&lt;=

Bu işleç `CComCurrency` , eşitlik veya daha küçük bir şekilde belirlenmesi için iki nesneyi karşılaştırır.

```
bool operator<= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*geçerli*<br/>
Bir `CComCurrency` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne ikinciden küçükse TRUE, aksi takdirde FALSE döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#64](../../atl/codesnippet/cpp/ccomcurrency-class_12.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_eq"></a>CComCurrency:: operator =

Bu işleç, `CComCurrency` nesneyi yeni bir değere atar.

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
PARA BIRIMI türünde bir değişken.

*SSRC*, *FSRC*, *lsrc*, *bsrc*, *ussrc*, *DSRC*, *CSRC*, *ulsrc*, *DSRC*<br/>
Nesneye atanacak sayısal değer `CComCurrency` .

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneyi döndürür `CComCurrency` . Taşma gibi bir hata durumunda bu işleç, `AtlThrow` hatayı açıklayan BIR HRESULT ile çağrı yapılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#65](../../atl/codesnippet/cpp/ccomcurrency-class_13.cpp)]

## <a name="ccomcurrencyoperator--"></a><a name="operator_-_eq"></a>CComCurrency:: operator-=

Bu işleç, bir nesne üzerinde çıkarma gerçekleştirmek `CComCurrency` ve sonuca atamak için kullanılır.

```
const CComCurrency& operator-= (const CComCurrency& cur);
```

### <a name="parameters"></a>Parametreler

*geçerli*<br/>
Bir `CComCurrency` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneyi döndürür `CComCurrency` . Taşma gibi bir hata durumunda bu işleç, `AtlThrow` hatayı açıklayan BIR HRESULT ile çağrı yapılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#66](../../atl/codesnippet/cpp/ccomcurrency-class_14.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_eq_eq"></a>CComCurrency:: operator = =

Bu işleç, `CComCurrency` eşitlik için iki nesneyi karşılaştırır.

```
bool operator== (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*geçerli*<br/>
`CComCurrency`Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Nesneler eşitse TRUE, bu, `m_currency` her iki nesnede de tamsayı ve kesir olan veri üyeleri aynı değere sahiptir; aksi takdırde false değerini döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#67](../../atl/codesnippet/cpp/ccomcurrency-class_15.cpp)]

## <a name="ccomcurrencyoperator-gt"></a><a name="operator_gt"></a>CComCurrency:: işleci&gt;

Bu işleç `CComCurrency` , daha büyük olduğunu anlamak için iki nesneyi karşılaştırır.

```
bool operator>(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*geçerli*<br/>
Bir `CComCurrency` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne ikinciden büyükse TRUE, aksi takdirde FALSE döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#68](../../atl/codesnippet/cpp/ccomcurrency-class_16.cpp)]

## <a name="ccomcurrencyoperator-gt"></a><a name="operator_gt_eq"></a>CComCurrency:: işleci&gt;=

Bu işleç `CComCurrency` , eşitlik veya daha büyük bir şekilde belirlenmesi için iki nesneyi karşılaştırır.

```
bool operator>= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*geçerli*<br/>
Bir `CComCurrency` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne ikinciden büyükse ya da eşitse TRUE, aksi takdirde FALSE döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#69](../../atl/codesnippet/cpp/ccomcurrency-class_17.cpp)]

## <a name="ccomcurrencyoperator-currency"></a><a name="operator_currency"></a>CComCurrency:: operator para BIRIMI

Bu işleçler, bir `CComCurrency` nesneyi BIR para birimi veri türüne dönüştürmek için kullanılır.

```
operator CURRENCY&() throw();
operator const CURRENCY&() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir para BIRIMI nesnesine bir başvuru döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#70](../../atl/codesnippet/cpp/ccomcurrency-class_18.cpp)]

## <a name="ccomcurrencyround"></a><a name="round"></a>CComCurrency:: Round

Para birimini belirtilen sayıda ondalık basamağa yuvarlamak için bu yöntemi çağırın.

```
HRESULT Roundint nDecimals);
```

### <a name="parameters"></a>Parametreler

*Nondalıklar*<br/>
`m_currency`0 ile 4 arasında yuvarlanacak basamak sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#52](../../atl/codesnippet/cpp/ccomcurrency-class_19.cpp)]

## <a name="ccomcurrencysetfraction"></a><a name="setfraction"></a>CComCurrency:: Setkesir

Bir nesnenin kesirli bileşenini ayarlamak için bu yöntemi çağırın `CComCurrency` .

```
HRESULT SetFraction(SHORT nFraction);
```

### <a name="parameters"></a>Parametreler

*Nkesir*<br/>
Veri üyesinin kesirli bileşenine atanacak değer `m_currency` . Kesirli bileşenin işareti, tamsayı bileşeniyle aynı olmalıdır ve değer-9999 (CY_MIN_FRACTION) ile + 9999 (CY_MAX_FRACTION) arasında olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#53](../../atl/codesnippet/cpp/ccomcurrency-class_20.cpp)]

## <a name="ccomcurrencysetinteger"></a><a name="setinteger"></a>CComCurrency:: Setınteger

Bir nesnenin tamsayı bileşenini ayarlamak için bu yöntemi çağırın `CComCurrency` .

```
HRESULT SetInteger(LONGLONG nInteger);
```

### <a name="parameters"></a>Parametreler

*Ntamsayı*<br/>
Veri üyesinin tamsayı bileşenine atanacak değer `m_currency` . Tamsayı bileşenin işareti, var olan kesirli bileşenin işaretiyle eşleşmelidir.

*Nınteger* , CY_MAX_INTEGER için CY_MIN_INTEGER aralığında olmalıdır. Bu değerler, atlcur. h içinde tanımlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#54](../../atl/codesnippet/cpp/ccomcurrency-class_21.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Cotacurrency sınıfı](../../mfc/reference/colecurrency-class.md)<br/>
[PARA BİRİMİ](/windows/win32/api/wtypes/ns-wtypes-cy-r1)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
