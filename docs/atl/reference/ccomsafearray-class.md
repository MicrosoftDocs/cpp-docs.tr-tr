---
title: "CComSafeArray sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSafeArray
- ATLSAFE/ATL::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::Add
- ATLSAFE/ATL::CComSafeArray::Attach
- ATLSAFE/ATL::CComSafeArray::CopyFrom
- ATLSAFE/ATL::CComSafeArray::CopyTo
- ATLSAFE/ATL::CComSafeArray::Create
- ATLSAFE/ATL::CComSafeArray::Destroy
- ATLSAFE/ATL::CComSafeArray::Detach
- ATLSAFE/ATL::CComSafeArray::GetAt
- ATLSAFE/ATL::CComSafeArray::GetCount
- ATLSAFE/ATL::CComSafeArray::GetDimensions
- ATLSAFE/ATL::CComSafeArray::GetLowerBound
- ATLSAFE/ATL::CComSafeArray::GetSafeArrayPtr
- ATLSAFE/ATL::CComSafeArray::GetType
- ATLSAFE/ATL::CComSafeArray::GetUpperBound
- ATLSAFE/ATL::CComSafeArray::IsSizable
- ATLSAFE/ATL::CComSafeArray::MultiDimGetAt
- ATLSAFE/ATL::CComSafeArray::MultiDimSetAt
- ATLSAFE/ATL::CComSafeArray::Resize
- ATLSAFE/ATL::CComSafeArray::SetAt
- ATLSAFE/ATL::CComSafeArray::m_psa
dev_langs:
- C++
helpviewer_keywords:
- CComSafeArray class
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7bed846015090ef9c4da841adff4968c91d8719d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomsafearray-class"></a>CComSafeArray sınıfı
Bu sınıf için sarmalayıcı, **SAFEARRAY** yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename T, VARTYPE _vartype = _ATL_AutomationType<T>::type>
class CComSafeArray
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Dizideki depolanması için veri türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComSafeArray::CComSafeArray](#ccomsafearray)|Oluşturucu.|  
|[CComSafeArray:: ~ CComSafeArray](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComSafeArray::Add](#add)|Bir veya daha fazla öğe ekler veya **SAFEARRAY** yapısı, çok bir `CComSafeArray`.|  
|[CComSafeArray::Attach](#attach)|Bağlayan bir **SAFEARRAY** için yapı bir `CComSafeArray` nesnesi.|  
|[CComSafeArray::CopyFrom](#copyfrom)|İçeriğini kopyalar bir **SAFEARRAY** içine yapısı `CComSafeArray` nesnesi.|  
|[CComSafeArray::CopyTo](#copyto)|Bir kopyasını oluşturur `CComSafeArray` nesnesi.|  
|[CComSafeArray::Create](#create)|Oluşturur bir `CComSafeArray` nesnesi.|  
|[CComSafeArray::Destroy](#destroy)|Bozar bir `CComSafeArray` nesnesi.|  
|[CComSafeArray::Detach](#detach)|Ayırır bir **SAFEARRAY** gelen bir `CComSafeArray` nesnesi.|  
|[CComSafeArray::GetAt](#getat)|Tek boyutlu bir array tek bir öğe alır.|  
|[CComSafeArray::GetCount](#getcount)|Dizide öğe sayısını döndürür.|  
|[CComSafeArray::GetDimensions](#getdimensions)|Dizideki boyut sayısını döndürür.|  
|[CComSafeArray::GetLowerBound](#getlowerbound)|Belirli bir boyut dizinin alt sınır döndürür.|  
|[CComSafeArray::GetSafeArrayPtr](#getsafearrayptr)|Adresini döndürür `m_psa` veri üyesi.|  
|[CComSafeArray::GetType](#gettype)|Dizideki depolanan verilerin türünü döndürür.|  
|[CComSafeArray::GetUpperBound](#getupperbound)|Dizinin tüm boyutu üst sınırı döndürür.|  
|[CComSafeArray::IsSizable](#issizable)|Testleri bir `CComSafeArray` nesnesi yeniden boyutlandırılabilir.|  
|[CComSafeArray::MultiDimGetAt](#multidimgetat)|Tek bir öğeye çok boyutlu bir diziye alır.|  
|[CComSafeArray::MultiDimSetAt](#multidimsetat)|Çok boyutlu bir diziye bir öğe değerini ayarlar.|  
|[CComSafeArray::Resize](#resize)|Yeniden boyutlandırır bir `CComSafeArray` nesnesi.|  
|[CComSafeArray::SetAt](#setat)|Tek boyutlu bir dizide bir öğenin değerini ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComSafeArray::operator LPSAFEARRAY](#operator_lpsafearray)|Bir değere bıraktığı bir **SAFEARRAY** işaretçi.|  
|[CComSafeArray::operator\[\]](ccomsafearray-class.md#operator_at)|Bir öğenin diziden alır.|  
|[CComSafeArray::operator =](#operator_eq)|Atama işleci.|  

  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComSafeArray::m_psa](#m_psa)|Bu veri üyesi adresini tutar **SAFEARRAY** yapısı.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComSafeArray`için sarmalayıcı sağlar [SAFEARRAY veri türü](http://msdn.microsoft.com/en-us/9ec8025b-4763-4526-ab45-390c5d8b3b1e) oluşturmak ve tek ve çok boyutlu diziler neredeyse herhangi bir değişken desteklenen türlerini yönetmek için atmaktan kolaylaştırarak sınıfı.  
  
 `CComSafeArray`dizileri geçirme işlemleri arasındaki basitleştirir ve ayrıca dizi dizini değerlerini üst ve alt sınırlarını denetleyerek ek güvenlik sağlar.  
  
 Alt sınır değeri bir `CComSafeArray` tüm kullanıcı tanımlı değerinde başlatabilirsiniz; ancak, C++ erişilen diziler alt sınırı 0 kullanmanız gerekir. Visual Basic gibi diğer dilleri sınırlayıcı diğer değerleri (örneğin, -10-10) kullanabilir.  
  
 Kullanım [CComSafeArray::Create](#create) oluşturmak için bir `CComSafeArray` nesnesi ve [CComSafeArray::Destroy](#destroy) silmek için.  
  
 A `CComSafeArray` değişken veri türleri aşağıdaki alt içerebilir:  
  
|VARTYPE|Açıklama|  
|-------------|-----------------|  
|VT_I1|char|  
|VT_I2|short|  
|VT_I4|int|  
|VT_I4|long|  
|VT_I8|longlong|  
|VT_UI1|byte|  
|VT_UI2|ushort|  
|VT_UI4|uint|  
|VT_UI4|ulong|  
|VT_UI8|ULONGLONG|  
|VT_R4|float|  
|VT_R8|çift|  
|VT_DECIMAL|ondalık işaretçi|  
|VT_VARIANT|değişken işaretçi|  
|VT_CY|Currency veri türü|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsafe.h  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#75](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]  
  
##  <a name="add"></a>CComSafeArray::Add  
 Bir veya daha fazla öğe ekler veya **SAFEARRAY** yapısı, çok bir `CComSafeArray`.  
  
```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `psaSrc`  
 Bir işaretçi bir **SAFEARRAY** nesnesi.  
  
 `ulCount`  
 Diziye eklemek için nesnelerin sayısı.  
  
 *pT*  
 Dizi olarak eklenecek bir veya daha fazla nesneler için bir işaretçi.  
  
 *t*  
 Dizi olarak eklenecek nesne bir başvuru.  
  
 `bCopy`  
 Verilerin bir kopyasını oluşturulması gerekip gerekmediğini gösterir. Varsayılan değer **doğru**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni nesne var olan sonuna eklenir **SAFEARRAY** nesnesi. Bir nesne bir çok boyutlu görünümden ekleme **SAFEARRAY** nesnesi desteklenmiyor. Var olan bir nesneler dizisi eklerken, iki dizi öğeleri aynı türde içermesi gerekir.  
  
 `bCopy` Bayrağı dikkate alınır, türündeki öğeler `BSTR` veya **değişken** bir diziye eklenir. Varsayılan değer olan **TRUE** öğesi diziye eklendiğinde, yeni bir kopya verilerinin yapılmasını sağlar.  
  
##  <a name="attach"></a>CComSafeArray::Attach  
 Bağlayan bir **SAFEARRAY** için yapı bir `CComSafeArray` nesnesi.  
  
```
HRESULT Attach(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `psaSrc`  
 Bir işaretçi **SAFEARRAY** yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İliştirir bir **SAFEARRAY** için yapı bir `CComSafeArray` nesnesi, varolan yapma `CComSafeArray` yöntemleri kullanılabilir.  
  
##  <a name="ccomsafearray"></a>CComSafeArray::CComSafeArray  
 Oluşturucu.  
  
```
CComSafeArray();
CComSafeArray(const SAFEARRAYBOUND& bound);
CComSafeArray(ULONG  ulCount, LONG lLBound = 0);
CComSafeArray(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
CComSafeArray(const CComSafeArray& saSrc);
CComSafeArray(const SAFEARRAY& saSrc);
CComSafeArray(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `bound`  
 A **SAFEARRAYBOUND** yapısı.  
  
 `ulCount`  
 Dizideki öğelerin sayısı  
  
 `lLBound`  
 Alt sınır değeri; diğer bir deyişle, dizideki ilk öğenin dizini.  
  
 `pBound`  
 Bir işaretçi bir **SAFEARRAYBOUND** yapısı.  
  
 `uDims`  
 Dizi boyutları sayısı.  
  
 `saSrc`  
 Bir başvuru bir **SAFEARRAY** yapısı veya `CComSafeArray` nesnesi. Her iki durumda da Oluşturucusu dizi sonra yapım başvurulmuyor dizisinin bir kopyasını olmak için bu başvuru kullanır.  
  
 `psaSrc`  
 Bir işaretçi bir **SAFEARRAY** yapısı. Oluşturucusu bu adresi dizi sonra yapım başvurulmuyor dizisinin bir kopyasını olmak için kullanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturur bir `CComSafeArray` nesnesi.  
  
##  <a name="dtor"></a>CComSafeArray:: ~ CComSafeArray  
 Yok Edicisi.  
  
```
~CComSafeArray() throw()
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="copyfrom"></a>CComSafeArray::CopyFrom  
 İçeriğini kopyalar bir **SAFEARRAY** içine yapısı `CComSafeArray` nesnesi.  
  
```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```  
  
### <a name="parameters"></a>Parametreler  
 `ppArray`  
 İşaretçi **SAFEARRAY** kopyalamak için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, içeriğini kopyalar bir **SAFEARRAY** geçerli `CComSafeArray` nesnesi. Mevcut dizinin içeriğini değiştirilir.  
  
##  <a name="copyto"></a>CComSafeArray::CopyTo  
 Bir kopyasını oluşturur `CComSafeArray` nesnesi.  
  
```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```  
  
### <a name="parameters"></a>Parametreler  
 `ppArray`  
 Bir işaretçi oluşturulacağı yeni bir konuma **SAFEARRAY**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, içeriğini kopyalar bir `CComSafeArray` içine nesne bir **SAFEARRAY** yapısı.  
  
##  <a name="create"></a>CComSafeArray::Create  
 Oluşturur bir `CComSafeArray`.  
  
```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `pBound`  
 Bir işaretçi bir **SAFEARRAYBOUND** nesnesi.  
  
 `uDims`  
 Dizi boyutları sayısı.  
  
 `ulCount`  
 Dizideki öğelerin sayısı  
  
 `lLBound`  
 Alt sınır değeri; diğer bir deyişle, dizideki ilk öğenin dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 A `CComSafeArray` varolan bir nesne oluşturulabilir **SAFEARRAYBOUND** yapısı ve boyutlarının veya dizinin ve alt sınırı öğe sayısını belirterek sayı. Visual C++ içinden erişilecek diziyse, alt sınırı 0 olmalıdır. Diğer diller diğer değerler alt sınırı (örneğin, Visual Basic destekler dizilerle -10-10 gibi bir aralık ile öğeleri) için izin verebilir.  
  
##  <a name="destroy"></a>CComSafeArray::Destroy  
 Bozar bir `CComSafeArray` nesnesi.  
  
```
HRESULT Destroy();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Var olan bozar `CComSafeArray` nesne ve tüm veriler.  
  
##  <a name="detach"></a>CComSafeArray::Detach  
 Ayırır bir **SAFEARRAY** gelen bir `CComSafeArray` nesnesi.  
  
```
LPSAFEARRAY Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi döndüren bir **SAFEARRAY** nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ayırır **SAFEARRAY** nesnesini `CComSafeArray` nesne.  
  
##  <a name="getat"></a>CComSafeArray::GetAt  
 Tek boyutlu bir array tek bir öğe alır.  
  
```
T& GetAt(LONG lIndex) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `lIndex`  
 Değer döndürmek için dizisindeki dizini sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gerekli dizi öğesi için bir başvuru döndürür.  
  
##  <a name="getcount"></a>CComSafeArray::GetCount  
 Dizide öğe sayısını döndürür.  
  
```
ULONG GetCount(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `uDim`  
 Dizi boyutu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizide öğe sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Çok boyutlu bir diziye ile kullanıldığında, bu yöntem yalnızca belirli bir boyuttaki öğe sayısını döndürür.  
  
##  <a name="getdimensions"></a>CComSafeArray::GetDimensions  
 Dizideki boyut sayısını döndürür.  
  
```
UINT GetDimensions() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizideki boyut sayısını döndürür.  
  
##  <a name="getlowerbound"></a>CComSafeArray::GetLowerBound  
 Belirli bir boyut dizinin alt sınır döndürür.  
  
```
LONG GetLowerBound(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `uDim`  
 Dizi boyutu alt sınırı almak istediğiniz. Atlanırsa, varsayılan değer 0'dır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Alt sınır döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Alt sınırı 0 ise, bu öğe numarası 0 olan ilk öğedir C benzeri dizi gösterir. Bir hata olması durumunda, geçersiz boyut bağımsız değişken, örneğin, bu yöntemi çağırır. `AtlThrow` hatayı açıklayan bir HRESULT.  
  
##  <a name="getsafearrayptr"></a>CComSafeArray::GetSafeArrayPtr  
 Adresini döndürür `m_psa` veri üyesi.  
  
```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi döndürür [CComSafeArray::m_psa](#m_psa) veri üyesi.  
  
##  <a name="gettype"></a>CComSafeArray::GetType  
 Dizideki depolanan verilerin türünü döndürür.  
  
```
VARTYPE GetType() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki türlerinden herhangi birinde olabilir dizisinde depolanan verilerin türünü döndürür:  
  
|VARTYPE|Açıklama|  
|-------------|-----------------|  
|VT_I1|char|  
|VT_I2|short|  
|VT_I4|int|  
|VT_I4|long|  
|VT_I8|longlong|  
|VT_UI1|byte|  
|VT_UI2|ushort|  
|VT_UI4|uint|  
|VT_UI4|ulong|  
|VT_UI8|ULONGLONG|  
|VT_R4|float|  
|VT_R8|çift|  
|VT_DECIMAL|ondalık işaretçi|  
|VT_VARIANT|değişken işaretçi|  
|VT_CY|Currency veri türü|  
  
##  <a name="getupperbound"></a>CComSafeArray::GetUpperBound  
 Dizinin tüm boyutu üst sınırı döndürür.  
  
```
LONG GetUpperBound(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `uDim`  
 Dizi boyutu üst sınırı almak istediğiniz. Atlanırsa, varsayılan değer 0'dır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üst sınır döndürür. Bu değer dahil, bu boyut için en büyük geçerli dizin.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir hata olması durumunda, geçersiz boyut bağımsız değişken, örneğin, bu yöntemi çağırır. `AtlThrow` hatayı açıklayan bir HRESULT.  
  
##  <a name="issizable"></a>CComSafeArray::IsSizable  
 Testleri bir `CComSafeArray` nesnesi yeniden boyutlandırılabilir.  
  
```
bool IsSizable() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** varsa `CComSafeArray` yeniden boyutlandırılabilir, **false** başaramazsa.  
  
##  <a name="m_psa"></a>CComSafeArray::m_psa  
 Adresini tutar **SAFEARRAY** erişilen yapısı.  
  
```
LPSAFEARRAY m_psa;
```  
  
##  <a name="multidimgetat"></a>CComSafeArray::MultiDimGetAt  
 Tek bir öğeye çok boyutlu bir diziye alır.  
  
```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```  
  
### <a name="parameters"></a>Parametreler  
 `alIndex`  
 Dizideki her boyut için dizin vektörü işaretçi. Soldaki (en önemli) boyutu `alIndex[0]`.  
  
 *t*  
 Döndürülen veriler bir başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="multidimsetat"></a>CComSafeArray::MultiDimSetAt  
 Çok boyutlu bir diziye bir öğe değerini ayarlar.  
  
```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```  
  
### <a name="parameters"></a>Parametreler  
 `alIndex`  
 Dizideki her boyut için dizin vektörü işaretçi. En sağdaki (en az önemli) boyutu `alIndex`[0].  
  
 *T*  
 Yeni öğe değerini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bir çok boyutlu sürümüdür [CComSafeArray::SetAt](#setat).  
  
##  <a name="operator_at"></a>CComSafeArray::operator\[\]  
 Bir öğenin diziden alır.  
  
```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```  
  
### <a name="parameters"></a>Parametreler  
 *Dizin, nIndex*  
 Dizideki gerekli öğe dizini sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uygun dizi öğesi döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Benzer bir işlevi gerçekleştiren [CComSafeArray::GetAt](#getat), ancak bu işleci yalnızca tek boyutlu diziler ile çalışır.  
  
##  <a name="operator_eq"></a>CComSafeArray::operator =  
 Atama işleci.  
  
```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `saSrc`  
 Bir başvuru bir `CComSafeArray` nesnesi.  
  
 `psaSrc`  
 Bir işaretçi bir **SAFEARRAY** nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizideki depolanan verilerin türünü döndürür.  
  
##  <a name="operator_lpsafearray"></a>CComSafeArray::operator LPSAFEARRAY  
 Bir değere bıraktığı bir **SAFEARRAY** işaretçi.  
  
```
operator LPSAFEARRAY() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir değere bıraktığı bir **SAFEARRAY** işaretçi.  
  
##  <a name="resize"></a>CComSafeArray::Resize  
 Yeniden boyutlandırır bir `CComSafeArray` nesnesi.  
  
```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `pBound`  
 Bir işaretçi bir **SAFEARRAYBOUND** öğe sayısı ve dizinin alt sınırını hakkında bilgi içeren yapısı.  
  
 `ulCount`  
 Nesneleri yeniden boyutlandırılan dizisindeki istenen sayısı.  
  
 `lLBound`  
 Alt sınır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca en sağdaki boyutu göre yeniden boyutlandırır. İade diziler boyutlandırılmayacağını **IsResizable** olarak **false**.  
  
##  <a name="setat"></a>CComSafeArray::SetAt  
 Tek boyutlu bir dizide bir öğenin değerini ayarlar.  
  
```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `lIndex`  
 Dizi öğesi ayarlamak için dizin sayısı.  
  
 *t*  
 Belirtilen öğe yeni değeri.  
  
 `bCopy`  
 Verilerin bir kopyasını oluşturulması gerekip gerekmediğini gösterir. Varsayılan değer **doğru**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `bCopy` Bayrağı dikkate alınır, türündeki öğeler `BSTR` veya **değişken** bir diziye eklenir. Varsayılan değer olan **TRUE** öğesi diziye eklendiğinde, yeni bir kopya verilerinin yapılmasını sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SAFEARRAY veri türü](http://msdn.microsoft.com/en-us/9ec8025b-4763-4526-ab45-390c5d8b3b1e)   
 [CComSafeArray::Create](#create)   
 [CComSafeArray::Destroy](#destroy)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
