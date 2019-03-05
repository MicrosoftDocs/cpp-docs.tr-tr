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
ms.openlocfilehash: b2c07bc9c0b1e96f34798b20207dc0eb0362e534
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57277732"
---
# <a name="ccomcurrency-class"></a>CComCurrency sınıfı

`CComCurrency` yöntemleri ve işleçleri oluşturma ve bir para birimi nesnesi yönetmek için vardır.

## <a name="syntax"></a>Sözdizimi

```
class CComCurrency
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComCurrency::CComCurrency](#ccomcurrency)|Oluşturucusu bir `CComCurrency` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComCurrency::GetCurrencyPtr](#getcurrencyptr)|Adresini döndürür bir `m_currency` veri üyesi.|
|[CComCurrency::GetFraction](#getfraction)|Kesirli bileşeninin döndürmek için bu yöntemi çağıran bir `CComCurrency` nesne.|
|[CComCurrency::GetInteger](#getinteger)|Tamsayı bileşeninin döndürmek için bu yöntemi çağıran bir `CComCurrency` nesne.|
|[CComCurrency::Round](#round)|Yuvarlamak için bu yöntemi çağıran bir `CComCurrency` en yakın tamsayı değerine nesne.|
|[CComCurrency::SetFraction](#setfraction)|Kesirli bileşeninin ayarlamak için bu yöntemi çağıran bir `CComCurrency` nesne.|
|[CComCurrency::SetInteger](#setinteger)|Tamsayı bileşeninin ayarlamak için bu yöntemi çağıran bir `CComCurrency` nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CComCurrency::operator-](#operator_-)|Bu işleç çıkarma gerçekleştirmek için kullanılan bir `CComCurrency` nesne.|
|[CComCurrency::operator! =](#operator_neq)|İki karşılaştırır `CComCurrency` nesneleri için eşitsizlik.|
|[CComCurrency::operator *](#operator_star)|Bu işleç çarpma işlemi gerçekleştirmek için kullanılan bir `CComCurrency` nesne.|
|[CComCurrency::operator * =](#operator_star_eq)|Bu işleç çarpma işlemi gerçekleştirmek için kullanılan bir `CComCurrency` nesne ve sonucu atayın.|
|[CComCurrency::operator /](#operator_div)|Bu işleç bölme gerçekleştirmek için kullanılan bir `CComCurrency` nesne.|
|[CComCurrency::operator / =](#operator_div_eq)|Bu işleç bölme gerçekleştirmek için kullanılan bir `CComCurrency` nesne ve sonucu atayın.|
|[CComCurrency::operator +](#operator_add)|Bu işleç ayrıca gerçekleştirmek için kullanılan bir `CComCurrency` nesne.|
|[CComCurrency::operator +=](#operator_add_eq)|Bu işleç ayrıca gerçekleştirmek için kullanılan bir `CComCurrency` nesne ve sonuç geçerli nesneye atayın.|
|[CComCurrency::operator <](#operator_lt)|Bu işleç iki karşılaştırır `CComCurrency` küçük olanı belirlemek için nesneleri.|
|[CComCurrency::operator < =](#operator_lt_eq)|Bu işleç iki karşılaştırır `CComCurrency` eşitlik ya da küçük olanı belirlemek için nesneleri.|
|[CComCurrency::operator =](#operator_eq)|Bu işleç atar `CComCurrency` yeni bir değer nesnesi.|
|[CComCurrency::operator-=](#operator_-_eq)|Bu işleç çıkarma gerçekleştirmek için kullanılan bir `CComCurrency` nesne ve sonucu atayın.|
|[CComCurrency::operator ==](#operator_eq_eq)|Bu işleç iki karşılaştırır `CComCurrency` eşitlik için nesneleri.|
|[CComCurrency::operator >](#operator_gt)|Bu işleç iki karşılaştırır `CComCurrency` büyük belirlemek için nesneleri.|
|[CComCurrency::operator > =](#operator_gt_eq)|Bu işleç iki karşılaştırır `CComCurrency` eşitlik ya da daha büyük belirlemek için nesneleri.|
|[CComCurrency::operator para birimi](#operator_currency)|Bir para birimi nesnesi çevirir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComCurrency::m_currency](#m_currency)|Para birimi, sınıf örneği tarafından oluşturulan değişken.|

## <a name="remarks"></a>Açıklamalar

`CComCurrency` para birimi veri türüne ilişkin bir sarmalayıcıdır. Para birimi 10.000 ölçeğinde bir ikiye tamamlayıcı 8 baytlık tamsayı olarak uygulanır. Bu seçenek, sabit noktalı bir sayı Ondalık ayırıcının solundaki 15 basamakla ve 4 rakamdan sağa sağlar. Para birimi veri türüne doğruluğu önemli olduğu parayla veya herhangi bir hesaplamalardaki fazlasıyla yararlı bir özelliktir.

`CComCurrency` Sarmalayıcı bu sabit nokta türü için aritmetik, atama ve karşılaştırma işlemleri uygular. Desteklenen uygulamaların, hesaplamalardaki sırasında oluşabilecek yuvarlama hataları denetlemek için seçilmedi.

`CComCurrency` Nesnesi sayılar ondalık biçiminde iki bileşenden her iki tarafındaki erişim sağlar: Ondalık ayırıcının solundaki değeri depolayan bir tam sayı bileşenine ve sağındaki değer depolayan kesirli bir bileşeni ondalık noktası. Kesirli bileşen -9999 (CY_MIN_FRACTION) ve +9999 (CY_MAX_FRACTION) arasında bir tamsayı değeri olarak dahili olarak depolanır. Yöntem [CComCurrency::GetFraction](#getfraction) 10000 (CY_SCALE) faktörüyle ölçeklendirilmiş bir değer döndürür.

Tamsayı ve kesirli bileşenlerinin belirtirken bir `CComCurrency` nesne, kesirli bileşen 0-9999 aralığında bir sayı olduğunu unutmayın. Bu, bir para birimi gibi ondalık ayırıcıdan sonra yalnızca iki önemli basamak kullanarak tutarları ifade ABD doları ile ilgilenirken önemlidir. Son iki basamak görüntülenmez olsa da, bunlar göz önünde bulundurulması gerekir.

|Değer|Olası CComCurrency atamaları|
|-----------|---------------------------------------|
|$10.50|CComCurrency(10,5000) *veya* CComCurrency(10.50)|
|$10.05|CComCurrency(10,500) *veya* CComCurrency(10.05)|

Değerlerin CY_MIN_FRACTION CY_MAX_FRACTION ve CY_SCALE atlcur.h içinde tanımlanır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcur.h

##  <a name="ccomcurrency"></a>  CComCurrency::CComCurrency

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

*cysrc &*<br/>
Para birimi türünde bir değişken.

*bSrc*, *dSrc*, *fSrc*, *lSrc*, *sSrc*, *ulSrc, usSrc*<br/>
Üye değişkeni için verilen ilk değer `m_currency`.

*cSrc*<br/>
Üye değişkeni için verilen ilk değer içeren bir karakter `m_currency`.

*nInteger*, *nFraction*<br/>
İlk parasal değerinin kesirli bileşenlerin ve tamsayı. Bkz: [CComCurrency](../../atl/reference/ccomcurrency-class.md) daha fazla bilgi için.

*pDispSrc*<br/>
Bir `IDispatch` işaretçi.

*varSrc*<br/>
DEĞİŞKEN türünde bir değişken. Geçerli iş parçacığının yerel ayarı, dönüştürme gerçekleştirmek için kullanılır.

*szSrc*<br/>
Başlangıç değeri içeren bir Unicode veya ANSI dize. Geçerli iş parçacığının yerel ayarı, dönüştürme gerçekleştirmek için kullanılır.

### <a name="remarks"></a>Açıklamalar

Yapıcı başlangıç değerini ayarlar [CComCurrency::m_currency](#m_currency)ve çok çeşitli veri türleri, tamsayı, dizeler, kayan noktalı sayıların, para birimi değişkenleri ve diğer dahil olmak üzere kabul `CComCurrency` nesneleri. Hiçbir değer sağlanmışsa `m_currency` 0 olarak ayarlayın.

Taşma, boş bir özel durum belirtimi eksik oluşturucular gibi bir hata durumunda (**throw()**) çağrı `AtlThrow` hatayı açıklayan bir HRESULT.

Kayan nokta veya çift değer, bir değer atamak için kullanırken dikkat `CComCurrency(10.50)` eşdeğerdir `CComCurrency(10,5000)` değil `CComCurrency(10,50)`.

##  <a name="getcurrencyptr"></a>  CComCurrency::GetCurrencyPtr

Adresini döndürür bir `m_currency` veri üyesi.

```
CURRENCY* GetCurrencyPtr() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Adresini döndürür bir `m_currency` veri üyesi

##  <a name="getfraction"></a>  CComCurrency::GetFraction

Kesirli bileşeninin döndürmek için bu yöntemi çağırın `CComCurrency` nesne.

```
SHORT GetFraction() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kesirli bileşenini döndürür `m_currency` veri üyesi.

### <a name="remarks"></a>Açıklamalar

Bir 4 basamaklı bir tamsayı değeri -9999 (CY_MIN_FRACTION) ve +9999 (CY_MAX_FRACTION) arasında kesirli bileşendir. `GetFraction` 10000 (CY_SCALE) göre ölçeği bu değeri döndürür. CY_MIN_FRACTION CY_MAX_FRACTION ve CY_SCALE değerlerini atlcur.h içinde tanımlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#50](../../atl/codesnippet/cpp/ccomcurrency-class_1.cpp)]

##  <a name="getinteger"></a>  CComCurrency::GetInteger

Tamsayı bileşeninin almak için bu yöntemi çağıran bir `CComCurrency` nesne.

```
LONGLONG GetInteger() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tamsayı bileşenini döndürür `m_currency` veri üyesi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#51](../../atl/codesnippet/cpp/ccomcurrency-class_2.cpp)]

##  <a name="m_currency"></a>  CComCurrency::m_currency

Para birimi veri üyesi.

```
CURRENCY m_currency;
```

### <a name="remarks"></a>Açıklamalar

Bu üye, erişilebilir ve bu sınıftaki yöntemleri tarafından yönetilen para birimi tutar.

##  <a name="operator_-"></a>  CComCurrency::operator-

Bu işleç çıkarma gerçekleştirmek için kullanılan bir `CComCurrency` nesne.

```
CComCurrency operator-() const;
CComCurrency operator-(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Yinele*<br/>
A `CComCurrency` nesne.

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir `CComCurrency` çıkarma işleminin sonucu temsil eden nesne. Bir taşma gibi bir hata olması durumunda bu işleci çağırır `AtlThrow` hatayı açıklayan bir HRESULT.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#55](../../atl/codesnippet/cpp/ccomcurrency-class_3.cpp)]

##  <a name="operator_neq"></a>  CComCurrency::operator! =

Bu işleç, eşitsizlik açısından iki nesneyi karşılaştırır.

```
bool operator!= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Yinele*<br/>
`CComCurrency` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğesi eşit değilse TRUE döndürür `CComCurrency` nesne; Aksi takdirde FALSE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#56](../../atl/codesnippet/cpp/ccomcurrency-class_4.cpp)]

##  <a name="operator_star"></a>  CComCurrency::operator *

Bu işleç çarpma işlemi gerçekleştirmek için kullanılan bir `CComCurrency` nesne.

```
CComCurrency operator*(long nOperand) const;
CComCurrency operator*(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*nOperand*<br/>
Çarpan.

*Yinele*<br/>
`CComCurrency` Çarpanı olarak kullanılan nesne.

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir `CComCurrency` çarpma işleminin sonucunu temsil eden nesne. Bir taşma gibi bir hata olması durumunda bu işleci çağırır `AtlThrow` hatayı açıklayan bir HRESULT.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#57](../../atl/codesnippet/cpp/ccomcurrency-class_5.cpp)]

##  <a name="operator_star_eq"></a>  CComCurrency::operator \*=

Bu işleç çarpma işlemi gerçekleştirmek için kullanılan bir `CComCurrency` nesne ve sonucu atayın.

```
const CComCurrency& operator*= (long nOperand);
const CComCurrency& operator*= (const CComCurrency& cur);
```

### <a name="parameters"></a>Parametreler

*nOperand*<br/>
Çarpan.

*Yinele*<br/>
`CComCurrency` Çarpanı olarak kullanılan nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş döndürür `CComCurrency` nesne. Bir taşma gibi bir hata olması durumunda bu işleci çağırır `AtlThrow` hatayı açıklayan bir HRESULT.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#58](../../atl/codesnippet/cpp/ccomcurrency-class_6.cpp)]

##  <a name="operator_div"></a>  CComCurrency::operator /

Bu işleç bölme gerçekleştirmek için kullanılan bir `CComCurrency` nesne.

```
CComCurrency operator/(long nOperand) const;
```

### <a name="parameters"></a>Parametreler

*nOperand*<br/>
Bölen.

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir `CComCurrency` bölme sonucunu temsil eden nesne. Bölen 0 ise, bir onay hata meydana gelir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#59](../../atl/codesnippet/cpp/ccomcurrency-class_7.cpp)]

##  <a name="operator_div_eq"></a>  CComCurrency::operator / =

Bu işleç bölme gerçekleştirmek için kullanılan bir `CComCurrency` nesne ve sonucu atayın.

```
const CComCurrency& operator/= (long nOperand);
```

### <a name="parameters"></a>Parametreler

*nOperand*<br/>
Bölen.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş döndürür `CComCurrency` nesne. Bölen 0 ise, bir onay hata meydana gelir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#60](../../atl/codesnippet/cpp/ccomcurrency-class_8.cpp)]

##  <a name="operator_add"></a>  CComCurrency::operator +

Bu işleç ayrıca gerçekleştirmek için kullanılan bir `CComCurrency` nesne.

```
CComCurrency operator+(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Yinele*<br/>
`CComCurrency` Özgün nesneye eklenecek nesne.

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir `CComCurrency` toplamın sonucunu temsil eden nesne. Bir taşma gibi bir hata olması durumunda bu işleci çağırır `AtlThrow` hatayı açıklayan bir HRESULT.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#61](../../atl/codesnippet/cpp/ccomcurrency-class_9.cpp)]

##  <a name="operator_add_eq"></a>  CComCurrency::operator +=

Bu işleç ayrıca gerçekleştirmek için kullanılan bir `CComCurrency` nesne ve sonuç geçerli nesneye atayın.

```
const CComCurrency& operator+= (const CComCurrency& cur);
```

### <a name="parameters"></a>Parametreler

*Yinele*<br/>
`CComCurrency` Nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş döndürür `CComCurrency` nesne. Bir taşma gibi bir hata olması durumunda bu işleci çağırır `AtlThrow` hatayı açıklayan bir HRESULT.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#62](../../atl/codesnippet/cpp/ccomcurrency-class_10.cpp)]

##  <a name="operator_lt"></a>  CComCurrency::operator &lt;

Bu işleç iki karşılaştırır `CComCurrency` küçük olanı belirlemek için nesneleri.

```
bool operator<(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Yinele*<br/>
A `CComCurrency` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesnenin küçükse TRUE döndürür, yanlış ikinciden Aksi takdirde.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#63](../../atl/codesnippet/cpp/ccomcurrency-class_11.cpp)]

##  <a name="operator_lt_eq"></a>  CComCurrency::operator &lt;=

Bu işleç iki karşılaştırır `CComCurrency` eşitlik ya da küçük olanı belirlemek için nesneleri.

```
bool operator<= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Yinele*<br/>
A `CComCurrency` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesnenin saniyeye eşit veya aksi durumda FALSE ise true değeri döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#64](../../atl/codesnippet/cpp/ccomcurrency-class_12.cpp)]

##  <a name="operator_eq"></a>  CComCurrency::operator =

Bu işleç atar `CComCurrency` yeni bir değer nesnesi.

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
A `CComCurrency` nesne.

*cysrc &*<br/>
Para birimi türünde bir değişken.

*sSrc*, *fSrc*, *lSrc*, *bSrc*, *usSrc*, *dSrc*, *cSrc*, *ulSrc*, *dSrc*<br/>
Sayısal bir değer atamak için `CComCurrency` nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş döndürür `CComCurrency` nesne. Bir taşma gibi bir hata olması durumunda bu işleci çağırır `AtlThrow` hatayı açıklayan bir HRESULT.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#65](../../atl/codesnippet/cpp/ccomcurrency-class_13.cpp)]

##  <a name="operator_-_eq"></a>  CComCurrency::operator-=

Bu işleç çıkarma gerçekleştirmek için kullanılan bir `CComCurrency` nesne ve sonucu atayın.

```
const CComCurrency& operator-= (const CComCurrency& cur);
```

### <a name="parameters"></a>Parametreler

*Yinele*<br/>
A `CComCurrency` nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş döndürür `CComCurrency` nesne. Bir taşma gibi bir hata olması durumunda bu işleci çağırır `AtlThrow` hatayı açıklayan bir HRESULT.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#66](../../atl/codesnippet/cpp/ccomcurrency-class_14.cpp)]

##  <a name="operator_eq_eq"></a>  CComCurrency::operator ==

Bu işleç iki karşılaştırır `CComCurrency` eşitlik için nesneleri.

```
bool operator== (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Yinele*<br/>
`CComCurrency` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Nesneler eşitse TRUE döndürür (diğer bir deyişle, `m_currency` veri üyeleri, iki tamsayı ve hem de kesirli nesneler aynı değere sahip) false Aksi takdirde.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#67](../../atl/codesnippet/cpp/ccomcurrency-class_15.cpp)]

##  <a name="operator_gt"></a>  CComCurrency::operator &gt;

Bu işleç iki karşılaştırır `CComCurrency` büyük belirlemek için nesneleri.

```
bool operator>(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Yinele*<br/>
A `CComCurrency` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesnenin Aksi takdirde FALSE ikincisinden büyük ise true değeri döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#68](../../atl/codesnippet/cpp/ccomcurrency-class_16.cpp)]

##  <a name="operator_gt_eq"></a>  CComCurrency::operator &gt;=

Bu işleç iki karşılaştırır `CComCurrency` eşitlik ya da daha büyük belirlemek için nesneleri.

```
bool operator>= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parametreler

*Yinele*<br/>
A `CComCurrency` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesnenin aksi değerinden büyük veya ikinciye, FALSE ise, TRUE döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#69](../../atl/codesnippet/cpp/ccomcurrency-class_17.cpp)]

##  <a name="operator_currency"></a>  CComCurrency::operator para birimi

Bu işleçler dönüştürmek için kullanılan bir `CComCurrency` bir para birimi veri türüne nesne.

```
operator CURRENCY&() throw();
operator const CURRENCY&() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Para birimi nesnesine bir başvuru döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#70](../../atl/codesnippet/cpp/ccomcurrency-class_18.cpp)]

##  <a name="round"></a>  CComCurrency::Round

Para birimi belirtilen ondalık basamak sayısına yuvarlar için bu yöntemi çağırın.

```
HRESULT Roundint nDecimals);
```

### <a name="parameters"></a>Parametreler

*nDecimals*<br/>
Hangi basamak sayısı `m_currency` 0-4 aralığında yuvarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#52](../../atl/codesnippet/cpp/ccomcurrency-class_19.cpp)]

##  <a name="setfraction"></a>  CComCurrency::SetFraction

Kesirli bileşeninin ayarlamak için bu yöntemi çağıran bir `CComCurrency` nesne.

```
HRESULT SetFraction(SHORT nFraction);
```

### <a name="parameters"></a>Parametreler

*nFraction*<br/>
Kesirli bileşeninin atanacak değer `m_currency` veri üyesi. Kesirli bileşeni'nin tam sayı bileşenine aynı olmalıdır ve değerin +9999 (CY_MAX_FRACTION) için (CY_MIN_FRACTION) -9999 aralığında olması gerekir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#53](../../atl/codesnippet/cpp/ccomcurrency-class_20.cpp)]

##  <a name="setinteger"></a>  CComCurrency::SetInteger

Tamsayı bileşeninin ayarlamak için bu yöntemi çağıran bir `CComCurrency` nesne.

```
HRESULT SetInteger(LONGLONG nInteger);
```

### <a name="parameters"></a>Parametreler

*nInteger*<br/>
Tamsayı bileşeni için atanan değer `m_currency` veri üyesi. Varolan kesirli bileşeni'nin tam sayı bileşenine işaretini eşleşmelidir.

*nInteger* CY_MAX_INTEGER kapsamlı için CY_MIN_INTEGER aralığında olması gerekir. Bu değerleri atlcur.h içinde tanımlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#54](../../atl/codesnippet/cpp/ccomcurrency-class_21.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[COleCurrency Sınıfı](../../mfc/reference/colecurrency-class.md)<br/>
[PARA BİRİMİ](/windows/desktop/api/wtypes/ns-wtypes-tagcy)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
