---
title: "CComCurrency sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
helpviewer_keywords: CComCurrency class
ms.assetid: a1c3d10a-bba6-40cc-8bcf-aed9023c8a9e
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1e9466c2081b7d9622776702d367ccae64a36b4f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomcurrency-class"></a>CComCurrency sınıfı
`CComCurrency`yöntemleri ve işleçler oluşturmak ve bir para birimi nesnesi yönetmek için vardır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComCurrency
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCurrency::CComCurrency](#ccomcurrency)|Oluşturucusu bir `CComCurrency` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCurrency::GetCurrencyPtr](#getcurrencyptr)|Adresini döndürür bir `m_currency` veri üyesi.|  
|[CComCurrency::GetFraction](#getfraction)|Kesirli bileşeninin döndürmek için bu yöntemi çağırabilmeniz bir `CComCurrency` nesnesi.|  
|[CComCurrency::GetInteger](#getinteger)|Tamsayı bileşeninin döndürmek için bu yöntemi çağırabilmeniz bir `CComCurrency` nesnesi.|  
|[CComCurrency::Round](#round)|Yuvarlamak için bu yöntemi çağırın bir `CComCurrency` en yakın tam sayı değerine nesnesi.|  
|[CComCurrency::SetFraction](#setfraction)|Kesirli bileşeninin ayarlamak için bu yöntemi çağırın bir `CComCurrency` nesnesi.|  
|[CComCurrency::SetInteger](#setinteger)|Tamsayı bileşeninin ayarlamak için bu yöntemi çağırın bir `CComCurrency` nesnesi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCurrency::operator-](#operator_-)|Bu işleç çıkarma yapmak için kullanılan bir `CComCurrency` nesnesi.|  
|[CComCurrency::operator! =](#operator_neq)|İki karşılaştırır `CComCurrency` eşitsizlik nesneleri.|  
|[CComCurrency::operator *](#operator_star)|Bu işleç çarpma gerçekleştirmek için kullanılan bir `CComCurrency` nesnesi.|  
|[CComCurrency::operator * =](#operator_star_eq)|Bu işleç çarpma gerçekleştirmek için kullanılan bir `CComCurrency` nesne ve sonucu atayın.|  
|[CComCurrency::operator /](#operator_div)|Bu işleç bölme gerçekleştirmek için kullanılan bir `CComCurrency` nesnesi.|  
|[CComCurrency::operator / =](#operator_div_eq)|Bu işleç bölme gerçekleştirmek için kullanılan bir `CComCurrency` nesne ve sonucu atayın.|  
|[CComCurrency::operator +](#operator_add)|Bu işleç toplama gerçekleştirmek için kullanılan bir `CComCurrency` nesnesi.|  
|[CComCurrency::operator +=](#operator_add_eq)|Bu işleç toplama gerçekleştirmek için kullanılan bir `CComCurrency` nesne ve geçerli nesneye sonucu atayın.|  
|[CComCurrency::operator <](#operator_lt)|Bu işleç iki karşılaştırır `CComCurrency` küçük olanı belirlemek için nesneleri.|  
|[CComCurrency::operator < =](#operator_lt_eq)|Bu işleç iki karşılaştırır `CComCurrency` eşitlik veya daha düşük belirlemek için nesneleri.|  
|[CComCurrency::operator =](#operator_eq)|Bu işleç atar `CComCurrency` yeni bir değer nesnesi.|  
|[CComCurrency::operator-=](#operator_-_eq)|Bu işleç çıkarma yapmak için kullanılan bir `CComCurrency` nesne ve sonucu atayın.|  
|[CComCurrency::operator ==](#operator_eq_eq)|Bu işleç iki karşılaştırır `CComCurrency` nesneleri eşitlik için.|  
|[CComCurrency::operator >](#operator_gt)|Bu işleç iki karşılaştırır `CComCurrency` büyük belirlemek için nesneleri.|  
|[CComCurrency::operator > =](#operator_gt_eq)|Bu işleç iki karşılaştırır `CComCurrency` eşitlik veya büyük belirlemek için nesneleri.|  
|[CComCurrency::operator para birimi](#operator_currency)|Atamalar bir `CURRENCY` nesnesi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComCurrency::m_currency](#m_currency)|`CURRENCY` Sınıfı örneği tarafından oluşturulan değişkeni.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComCurrency`için sarmalayıcı olan **para birimi** veri türü. **Para birimi** 10.000 ölçeğinde bir 8 bayt ikiye tamsayı değeri olarak uygulanır. Bu seçenek, bir sabit noktalı ondalık ayırıcının sol tarafındaki 15 basamağa numarasıyla ve 4 basamak sağa sağlar. **Para birimi** veri türü olan para içeren hesaplamalar için ya da tüm sabit noktalı hesaplamalar için son derece yararlı doğruluğunu önemli olduğu.  
  
 **CComCurrency** sarmalayıcı bu sabit noktalı türü için aritmetik, atama ve karşılaştırma işlemlerini uygular. Desteklenen uygulamaların sabit noktalı hesaplamalar sırasında oluşabilecek yuvarlama hataları denetlemek için seçilmedi.  
  
 `CComCurrency` Nesnesi, her iki tarafında iki bileşenden biçiminde ondalık konumun sayılara erişim sağlar: Ondalık ayırıcının sol tarafındaki değerine depolayan bir tamsayı bileşeni ve sağındaki değeri depolayan kesirli bir bileşeni Ondalık ayırıcının. Kesirli bileşen-9999 arasında bir tamsayı değeri olarak dahili olarak depolanır ( **CY_MIN_FRACTION**) ve +9999 ( **CY_MAX_FRACTION**). Yöntem [CComCurrency::GetFraction](#getfraction) 10000 faktörüyle ölçeklendirilmiş bir değer döndürür ( **CY_SCALE**).  
  
 Tamsayı ve kesirli bileşenlerinin belirtirken bir **CComCurrency** nesne, kesirli bileşen 0-9999 aralığında bir sayı olduğunu unutmayın. Bu, ondalık ayırıcıdan sonra yalnızca iki önemli basamak kullanarak tutarlar yoğunlaştıracaklardır ABD Doları gibi bir para birimi ile ilgilenirken önemlidir. Son iki basamak görüntülenmez olsa da, bunlar göz önünde bulundurulması gerekir.  
  
|Değer|Olası CComCurrency atamaları|  
|-----------|---------------------------------------|  
|$10.50|CComCurrency(10,5000) *veya* CComCurrency(10.50)|  
|$10.05|CComCurrency(10,500) *veya* CComCurrency(10.05)|  
  
 Değerleri **CY_MIN_FRACTION**, **CY_MAX_FRACTION**, ve **CY_SCALE** atlcur.h tanımlanır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcur.h  
  
##  <a name="ccomcurrency"></a>CComCurrency::CComCurrency  
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
 `curSrc`  
 Varolan bir `CComCurrency` nesnesi.  
  
 `cySrc`  
 Türünde bir değişken **para birimi**.  
  
 `bSrc`, `dSrc`, `fSrc`, `lSrc`, *sSrc*, *ulSrc, usSrc*  
 Üye değişkeni için verilen ilk değer `m_currency`.  
  
 `cSrc`  
 Üye değişkeni için verilen ilk değer içeren bir karakter `m_currency`.  
  
 `nInteger`, *nFraction*  
 Tamsayı ve kesirli bileşenleri ilk para değeri. Bkz: [CComCurrency](../../atl/reference/ccomcurrency-class.md) daha fazla bilgi için.  
  
 `pDispSrc`  
 Bir `IDispatch` işaretçi.  
  
 *varSrc*  
 Türünde bir değişken **değişken**. Geçerli iş parçacığı yerel dönüştürme gerçekleştirmek için kullanılır.  
  
 `szSrc`  
 Başlangıç değeri içeren bir Unicode veya ANSI dize. Geçerli iş parçacığı yerel dönüştürme gerçekleştirmek için kullanılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Yapıcı başlangıç değerini ayarlar [CComCurrency::m_currency](#m_currency)ve veri türleri, tamsayı, dize, kayan nokta sayıları dahil olmak üzere çeşitli kabul eden **para birimi** değişkenleri ve diğer `CComCurrency` nesneleri. Herhangi bir değer sağlanmazsa, `m_currency` 0 olarak ayarlayın.  
  
 Taşma, bir boş özel durum belirtimi eksik oluşturucular gibi bir hata durumunda ( **throw()**) çağrı `AtlThrow` hatayı açıklayan bir HRESULT.  
  
 Kayan nokta ya da çift değerleri bir değer atamaya kullanırken dikkat edin **CComCurrency(10.50)** eşdeğerdir **CComCurrency(10,5000)** ve **CComCurrency(10,50)**.  
  
##  <a name="getcurrencyptr"></a>CComCurrency::GetCurrencyPtr  
 Adresini döndürür bir `m_currency` veri üyesi.  
  
```
CURRENCY* GetCurrencyPtr() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Adresini döndürür bir `m_currency` veri üyesi  
  
##  <a name="getfraction"></a>CComCurrency::GetFraction  
 Kesirli bileşeninin döndürmek için bu yöntemi çağırabilmeniz `CComCurrency` nesnesi.  
  
```
SHORT GetFraction() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kesirli bileşenini döndürür `m_currency` veri üyesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kesirli bileşen-9999 arasında bir 4 basamaklı bir tamsayı değerdir ( **CY_MIN_FRACTION**) ve +9999 ( **CY_MAX_FRACTION**). `GetFraction`10000 tarafından ölçeklendirilmiş bu değeri döndürür ( **CY_SCALE**). Değerlerini **CY_MIN_FRACTION**, **CY_MAX_FRACTION**, ve **CY_SCALE** atlcur.h tanımlanır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#50](../../atl/codesnippet/cpp/ccomcurrency-class_1.cpp)]  
  
##  <a name="getinteger"></a>CComCurrency::GetInteger  
 Tamsayı bileşeni almak için bu yöntemi çağırın bir `CComCurrency` nesnesi.  
  
```
LONGLONG GetInteger() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tamsayı bileşenini döndürür `m_currency` veri üyesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#51](../../atl/codesnippet/cpp/ccomcurrency-class_2.cpp)]  
  
##  <a name="m_currency"></a>CComCurrency::m_currency  
 **Para birimi** veri üyesi.  
  
```
CURRENCY m_currency;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye erişilen ve bu sınıf yöntemler tarafından işlenemez para birimi tutar.  
  
##  <a name="operator_-"></a>CComCurrency::operator-  
 Bu işleç çıkarma yapmak için kullanılan bir `CComCurrency` nesnesi.  
  
```
CComCurrency operator-() const;
CComCurrency operator-(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `cur`  
 A `CComCurrency` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir `CComCurrency` çıkarma sonucunu temsil eden nesne. Bu işleç, taşma gibi bir hata durumunda çağırır `AtlThrow` hatayı açıklayan bir HRESULT.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#55](../../atl/codesnippet/cpp/ccomcurrency-class_3.cpp)]  
  
##  <a name="operator_neq"></a>CComCurrency::operator! =  
 Bu işleç eşitsizlik açısından iki nesneyi karşılaştırır.  
  
```
bool operator!= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `cur`  
 `CComCurrency` Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** karşılaştırılan öğesi eşit değilse `CComCurrency` nesne; Aksi halde, **false**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#56](../../atl/codesnippet/cpp/ccomcurrency-class_4.cpp)]  
  
##  <a name="operator_star"></a>CComCurrency::operator *  
 Bu işleç çarpma gerçekleştirmek için kullanılan bir `CComCurrency` nesnesi.  
  
```
CComCurrency operator*(long nOperand) const;
CComCurrency operator*(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `nOperand`  
 Çarpan.  
  
 `cur`  
 `CComCurrency` Çarpanı olarak kullanılan nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir `CComCurrency` Çarpım sonucunu temsil eden nesne. Bu işleç, taşma gibi bir hata durumunda çağırır `AtlThrow` hatayı açıklayan bir HRESULT.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#57](../../atl/codesnippet/cpp/ccomcurrency-class_5.cpp)]  
  
##  <a name="operator_star_eq"></a>CComCurrency::operator * =  
 Bu işleç çarpma gerçekleştirmek için kullanılan bir `CComCurrency` nesne ve sonucu atayın.  
  
```
const CComCurrency& operator*= (long nOperand);
const CComCurrency& operator*= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>Parametreler  
 `nOperand`  
 Çarpan.  
  
 `cur`  
 `CComCurrency` Çarpanı olarak kullanılan nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CComCurrency` nesnesi. Bu işleç, taşma gibi bir hata durumunda çağırır `AtlThrow` hatayı açıklayan bir HRESULT.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#58](../../atl/codesnippet/cpp/ccomcurrency-class_6.cpp)]  
  
##  <a name="operator_div"></a>CComCurrency::operator /  
 Bu işleç bölme gerçekleştirmek için kullanılan bir `CComCurrency` nesnesi.  
  
```
CComCurrency operator/(long nOperand) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `nOperand`  
 Bölen.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir `CComCurrency` bölme sonucunu temsil eden nesne. Bölen 0 ise, bir assert hata meydana gelir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#59](../../atl/codesnippet/cpp/ccomcurrency-class_7.cpp)]  
  
##  <a name="operator_div_eq"></a>CComCurrency::operator / =  
 Bu işleç bölme gerçekleştirmek için kullanılan bir `CComCurrency` nesne ve sonucu atayın.  
  
```
const CComCurrency& operator/= (long nOperand);
```  
  
### <a name="parameters"></a>Parametreler  
 `nOperand`  
 Bölen.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CComCurrency` nesnesi. Bölen 0 ise, bir assert hata meydana gelir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#60](../../atl/codesnippet/cpp/ccomcurrency-class_8.cpp)]  
  
##  <a name="operator_add"></a>CComCurrency::operator +  
 Bu işleç toplama gerçekleştirmek için kullanılan bir `CComCurrency` nesnesi.  
  
```
CComCurrency operator+(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `cur`  
 `CComCurrency` Özgün nesnesine eklenecek nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür bir `CComCurrency` eklenmesi sonucunu temsil eden nesne. Bu işleç, taşma gibi bir hata durumunda çağırır `AtlThrow` hatayı açıklayan bir HRESULT.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#61](../../atl/codesnippet/cpp/ccomcurrency-class_9.cpp)]  
  
##  <a name="operator_add_eq"></a>CComCurrency::operator +=  
 Bu işleç toplama gerçekleştirmek için kullanılan bir `CComCurrency` nesne ve geçerli nesneye sonucu atayın.  
  
```
const CComCurrency& operator+= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>Parametreler  
 `cur`  
 `CComCurrency` Nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CComCurrency` nesnesi. Bu işleç, taşma gibi bir hata durumunda çağırır `AtlThrow` hatayı açıklayan bir HRESULT.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#62](../../atl/codesnippet/cpp/ccomcurrency-class_10.cpp)]  
  
##  <a name="operator_lt"></a>CComCurrency::operator&lt;  
 Bu işleç iki karşılaştırır `CComCurrency` küçük olanı belirlemek için nesneleri.  
  
```
bool operator<(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `cur`  
 A `CComCurrency` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** ilk nesne düşükse ikinci daha **false** Aksi takdirde.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#63](../../atl/codesnippet/cpp/ccomcurrency-class_11.cpp)]  
  
##  <a name="operator_lt_eq"></a>CComCurrency::operator&lt;=  
 Bu işleç iki karşılaştırır `CComCurrency` eşitlik veya daha düşük belirlemek için nesneleri.  
  
```
bool operator<= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `cur`  
 A `CComCurrency` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** ilk nesne ikinci eşit veya daha az ise **false** Aksi takdirde.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#64](../../atl/codesnippet/cpp/ccomcurrency-class_12.cpp)]  
  
##  <a name="operator_eq"></a>CComCurrency::operator =  
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
 `curSrc`  
 A **CComCurrency** nesnesi.  
  
 `cySrc`  
 Türünde bir değişken **para birimi**.  
  
 *sSrc*, `fSrc`, `lSrc`, *bSrc*, *usSrc*, `dSrc`, *cSrc*, *ulSrc*,`dSrc`  
 Sayısal değer atamak için `CComCurrency` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CComCurrency` nesnesi. Bu işleç, taşma gibi bir hata durumunda çağırır `AtlThrow` hatayı açıklayan bir HRESULT.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#65](../../atl/codesnippet/cpp/ccomcurrency-class_13.cpp)]  
  
##  <a name="operator_-_eq"></a>CComCurrency::operator-=  
 Bu işleç çıkarma yapmak için kullanılan bir `CComCurrency` nesne ve sonucu atayın.  
  
```
const CComCurrency& operator-= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>Parametreler  
 `cur`  
 A `CComCurrency` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CComCurrency` nesnesi. Bu işleç, taşma gibi bir hata durumunda çağırır `AtlThrow` hatayı açıklayan bir HRESULT.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#66](../../atl/codesnippet/cpp/ccomcurrency-class_14.cpp)]  
  
##  <a name="operator_eq_eq"></a>CComCurrency::operator ==  
 Bu işleç iki karşılaştırır `CComCurrency` nesneleri eşitlik için.  
  
```
bool operator== (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `cur`  
 `CComCurrency` Karşılaştırılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** nesneleri eşitse (diğer bir deyişle, `m_currency` veri üyeleri, her iki tamsayı ve kesirli hem de nesneleri aynı değere sahip), **false** Aksi takdirde.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#67](../../atl/codesnippet/cpp/ccomcurrency-class_15.cpp)]  
  
##  <a name="operator_gt"></a>CComCurrency::operator&gt;  
 Bu işleç iki karşılaştırır `CComCurrency` büyük belirlemek için nesneleri.  
  
```
bool operator>(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `cur`  
 A `CComCurrency` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** ilk nesne ikinci büyükse, **false** Aksi takdirde.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#68](../../atl/codesnippet/cpp/ccomcurrency-class_16.cpp)]  
  
##  <a name="operator_gt_eq"></a>CComCurrency::operator&gt;=  
 Bu işleç iki karşılaştırır `CComCurrency` eşitlik veya büyük belirlemek için nesneleri.  
  
```
bool operator>= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `cur`  
 A `CComCurrency` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** ilk nesne ikinci eşit veya daha büyük ise **false** Aksi takdirde.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#69](../../atl/codesnippet/cpp/ccomcurrency-class_17.cpp)]  
  
##  <a name="operator_currency"></a>CComCurrency::operator para birimi  
 Bu işleçlere dönüştürmek için kullanılan bir `CComCurrency` nesnesine bir **para birimi** veri türü.  
  
```  
operator CURRENCY&() throw();
operator const CURRENCY&() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru döndürür bir **para birimi** nesnesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#70](../../atl/codesnippet/cpp/ccomcurrency-class_18.cpp)]  
  
##  <a name="round"></a>CComCurrency::Round  
 Belirtilen sayıda ondalık para birimi yuvarlamak için bu yöntemi çağırın.  
  
```
HRESULT Roundint nDecimals);
```  
  
### <a name="parameters"></a>Parametreler  
 *nDecimals*  
 Hangi basamak sayısı `m_currency` aralık 0 ile 4 yuvarlanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#52](../../atl/codesnippet/cpp/ccomcurrency-class_19.cpp)]  
  
##  <a name="setfraction"></a>CComCurrency::SetFraction  
 Kesirli bileşeninin ayarlamak için bu yöntemi çağırın bir `CComCurrency` nesnesi.  
  
```
HRESULT SetFraction(SHORT nFraction);
```  
  
### <a name="parameters"></a>Parametreler  
 *nFraction*  
 Kesirli bileşenine atanan değer `m_currency` veri üyesi. Kesirli bileşen oturum tamsayı bileşeni ile aynı olmalıdır ve değer-9999 aralığında olmalıdır ( **CY_MIN_FRACTION**) +9999 için ( **CY_MAX_FRACTION**).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#53](../../atl/codesnippet/cpp/ccomcurrency-class_20.cpp)]  
  
##  <a name="setinteger"></a>CComCurrency::SetInteger  
 Tamsayı bileşeninin ayarlamak için bu yöntemi çağırın bir `CComCurrency` nesnesi.  
  
```
HRESULT SetInteger(LONGLONG nInteger);
```  
  
### <a name="parameters"></a>Parametreler  
 `nInteger`  
 Tamsayı bileşenine atanan değer `m_currency` veri üyesi. Tamsayı bileşen oturum varolan kesirli bileşeni oturum eşleşmesi gerekir.  
  
 `nInteger`aralığında olmalıdır **CY_MIN_INTEGER** için **CY_MAX_INTEGER** (dahil) arasındadır. Bu değerleri atlcur.h içinde tanımlanmıştır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#54](../../atl/codesnippet/cpp/ccomcurrency-class_21.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COleCurrency sınıfı](../../mfc/reference/colecurrency-class.md)   
 [PARA BİRİMİ](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
