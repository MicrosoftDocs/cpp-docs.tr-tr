---
title: "CComPtrBase sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase::Advise
- ATLCOMCLI/ATL::CComPtrBase::Attach
- ATLCOMCLI/ATL::CComPtrBase::CoCreateInstance
- ATLCOMCLI/ATL::CComPtrBase::CopyTo
- ATLCOMCLI/ATL::CComPtrBase::Detach
- ATLCOMCLI/ATL::CComPtrBase::IsEqualObject
- ATLCOMCLI/ATL::CComPtrBase::QueryInterface
- ATLCOMCLI/ATL::CComPtrBase::Release
- ATLCOMCLI/ATL::CComPtrBase::SetSite
- ATLCOMCLI/ATL::CComPtrBase::p
dev_langs:
- C++
helpviewer_keywords:
- CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f0d9b4d49a7568df905a595e2cf6494b2b98706d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomptrbase-class"></a>CComPtrBase sınıfı
Bu sınıf, COM tabanlı bellek yordamları kullanarak akıllı işaretçi sınıflar için bir temel sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
class CComPtrBase
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Akıllı işaretçiyi tarafından başvurulan nesne türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComPtrBase:: ~ CComPtrBase](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComPtrBase::Advise](#advise)|Arasında bir bağlantı oluşturmak için bu yöntemi çağırın `CComPtrBase`ait bağlantı noktası ve istemcinin havuz.|  
|[CComPtrBase::Attach](#attach)|Varolan bir işaretçi sahipliğini almak için bu yöntemi çağırın.|  
|[CComPtrBase::CoCreateInstance](#cocreateinstance)|Belirtilen sınıf kimliği veya Program Kimliği ile ilişkili sınıfın bir nesnesi oluşturmak için bu yöntemi çağırın|  
|[CComPtrBase::CopyTo](#copyto)|Kopyalamak için bu yöntemi çağırın `CComPtrBase` başka bir işaretçi değişkeninin işaretçi.|  
|[CComPtrBase::Detach](#detach)|Bir işaretçi sahipliğini serbest bırakmak için bu yöntemi çağırın.|  
|[CComPtrBase::IsEqualObject](#isequalobject)|Denetlemek için bu yöntemi çağırabilmeniz belirtilen **IUnknown** ilişkili aynı nesneye işaret `CComPtrBase` nesnesi.|  
|[CComPtrBase::QueryInterface](#queryinterface)|Belirtilen bir arabirim için bir işaretçi döndürmek için bu yöntemi çağırın.|  
|[CComPtrBase::Release](#release)|Arabirim serbest bırakmak için bu yöntemi çağırın.|  
|[CComPtrBase::SetSite](#setsite)|Sitesi ayarlamak için bu yöntemi çağırın `CComPtrBase` nesnesini **IUnknown** üst nesnenin.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComPtrBase::operator T *](#operator_t_star)|Atama işleci.|  
|[CComPtrBase::operator!](#operator_not)|NOT işleci.|  
|[CComPtrBase::operator &](#operator_amp)|& İşleci.|  
|[CComPtrBase::operator *](#operator_star)|* İşleci.|  
|[CComPtrBase::operator <](#ccomptrbase__operator lt)|Küçüktür-işleci daha.|  
|[CComPtrBase::operator ==](#operator_eq_eq)|Eşitlik işleci.|  
|[CComPtrBase::operator ->](#operator_ptr)|İşaretçi üyeleri işleci.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComPtrBase::p](#p)|İşaretçi veri üye değişkeni.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, COM bellek yönetimi yordamları gibi kullanan diğer akıllı işaretçiler temelini [CComQIPtr](../../atl/reference/ccomqiptr-class.md) ve [CComPtr](../../atl/reference/ccomptr-class.md). Türetilen sınıflar kendi oluşturucular ve işleçler ekleyin, ama tarafından sağlanan yöntemleri Bel `CComPtrBase`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcomcli.h  
  
##  <a name="advise"></a>CComPtrBase::Advise  
 Arasında bir bağlantı oluşturmak için bu yöntemi çağırın `CComPtrBase`ait bağlantı noktası ve istemcinin havuz.  
  
```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *pUnk*  
 İstemcinin bir işaretçi **IUnknown**.  
  
 `iid`  
 Bağlantı noktası GUID. Genellikle, bu bağlantı noktası tarafından yönetilen giden arabirimi aynıdır.  
  
 `pdw`  
 Bağlantı benzersiz olarak tanıtan tanımlama bilgisi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [AtlAdvise](connection-point-global-functions.md#atladvise) daha fazla bilgi için.  
  
##  <a name="attach"></a>CComPtrBase::Attach  
 Varolan bir işaretçi sahipliğini almak için bu yöntemi çağırın.  
  
```
void Attach(T* p2) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p2`  
 `CComPtrBase` Nesne sahipliği Bu işaretçinin götürür.  
  
### <a name="remarks"></a>Açıklamalar  
 **Attach** çağrıları [CComPtrBase::Release](#release) varolan üzerinde [CComPtrBase::p](#p) üye değişkeni ve atar `p2` için `CComPtrBase::p`. Zaman bir `CComPtrBase` nesnesini bir işaretçi sahipliğini alır, otomatik olarak çağıracaktır `Release` nesne üzerinde başvuru sayısı 0 olarak kalırsa işaretçinin ve tüm silecek işaretçisi üzerinde veri ayrılmış.  
  
##  <a name="dtor"></a>CComPtrBase:: ~ CComPtrBase  
 Yok Edicisi.  
  
```
~CComPtrBase() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Gösterdiği arabirimi serbest `CComPtrBase`.  
  
##  <a name="cocreateinstance"></a>CComPtrBase::CoCreateInstance  
 Belirtilen sınıf kimliği veya Program Kimliği ile ilişkili sınıfın bir nesnesi oluşturmak için bu yöntemi çağırın  
  
```
HRESULT CoCreateInstance(  
    LPCOLESTR szProgID,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();

HRESULT CoCreateInstance(  
    REFCLSID rclsid,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `szProgID`  
 CLSID kurtarmak için kullanılan bir ProgID işaretçi.  
  
 `pUnkOuter`  
 Varsa **NULL**, nesne bir toplama bir parçası olarak oluşturulduğunu değil gösterir. Olmayan varsa **NULL**, gösteren bir işaretçidir toplama nesnenin **IUnknown** arabirimi (denetleme **IUnknown**).  
  
 `dwClsContext`  
 Yeni oluşturulan nesnenin yönetir kod çalışacağı bağlamı.  
  
 `rclsid`  
 Veri ve nesneyi oluşturmak için kullanılan kod ilişkili CLSID.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya REGDB_E_CLASSNOTREG, CLASS_E_NOAGGREGATION, CO_E_CLASSSTRING veya E_NOINTERFACE hatası döndürür. Bkz: [CoCreateClassInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615) ve [CLSIDFromProgID](http://msdn.microsoft.com/library/windows/desktop/ms688386) bu hataları açıklaması.  
  
### <a name="remarks"></a>Açıklamalar  
 Yönteminin ilk form çağrılırsa, [CLSIDFromProgID](http://msdn.microsoft.com/library/windows/desktop/ms688386) CLSID kurtarmak için kullanılır. Her iki Formlar'ı çağırın [CoCreateClassInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
 Hata ayıklama derlemelerinde, bir onaylama hata oluşacaktır [CComPtrBase::p](#p) NULL değerine eşit değil.  
  
##  <a name="copyto"></a>CComPtrBase::CopyTo  
 Kopyalamak için bu yöntemi çağırın `CComPtrBase` başka bir işaretçi değişkeninin işaretçi.  
  
```
HRESULT CopyTo(T** ppT) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *ppT*  
 Alacak değişkeninin adresi `CComPtrBase` işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, başarısız olduğunda E_POINTER S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Kopya `CComPtrBase` işaretçi *ppT*. Başvuru sayım [CComPtrBase::p](#p) üye değişkeni artar.  
  
 HRESULT eşleşmişse döndürülecek hata *ppT* NULL değerine eşittir. Hata ayıklama derlemelerinde, bir onaylama hata oluşacaktır *ppT* NULL değerine eşittir.  
  
##  <a name="detach"></a>CComPtrBase::Detach  
 Bir işaretçi sahipliğini serbest bırakmak için bu yöntemi çağırın.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçinin kopyasını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işaretçi sahipliğini serbest bırakır, ayarlar [CComPtrBase::p](#p) veri üye değişkeni null ve işaretçiyi kopyasını döndürür.  
  
##  <a name="isequalobject"></a>CComPtrBase::IsEqualObject  
 Denetlemek için bu yöntemi çağırabilmeniz belirtilen **IUnknown** ilişkili aynı nesneye işaret `CComPtrBase` nesnesi.  
  
```
bool IsEqualObject(IUnknown* pOther) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pOther`  
 **IUnknown \***  karşılaştırmak için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesneleri aynı, false Aksi takdirde true değerini döndürür.  
  
##  <a name="operator_not"></a>CComPtrBase::operator!  
 NOT işleci.  
  
```
bool operator!() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsa true değerini döndürür `CComHeapPtr` işaretçisi NULL değerine eşittir false Aksi takdirde.  
  
##  <a name="operator_amp"></a>CComPtrBase::operator&amp;  
 & İşleci.  
  
```
T** operator&() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gösterdiği nesne adresini döndürür `CComPtrBase` nesnesi.  
  
##  <a name="operator_star"></a>CComPtrBase::operator *  
 * İşleci.  
  
```
T& operator*() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değerini döndürür [CComPtrBase::p](#p); diğer bir deyişle, tarafından başvurulan nesne için bir işaretçi `CComPtrBase` nesnesi.  
  
 Hata ayıklama derlemeleri, bir onaylama hata oluşacaktır [CComPtrBase::p](#p) NULL değerine eşit değil.  
  
##  <a name="operator_eq_eq"></a>CComPtrBase::operator ==  
 Eşitlik işleci.  
  
```
bool operator== (T* pT) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *pT*  
 Bir nesne için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsa true değerini döndürür `CComPtrBase` ve *pT* de aynı nesneye, aksi takdirde false gelin.  
  
##  <a name="operator_ptr"></a>CComPtrBase::operator-&gt;  

 İşaretçi-üye işleci.  
  
```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değerini döndürür [CComPtrBase::p](#p) veri üye değişkeni.  
  
### <a name="remarks"></a>Açıklamalar  
 Gösterdiği bir sınıftaki bir yöntemi çağırmak için bu işleci kullanın `CComPtrBase` nesnesi. Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır `CComPtrBase` veri üyesi NULL olarak işaret eder.  
  
##  <a name="operator_lt"></a>CComPtrBase::operator&lt;  
 Küçüktür-işleci daha.  
  
```
bool operator<(T* pT) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *pT*  
 Bir nesne için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçinin geçerli nesne tarafından yönetilen true değerini döndürür, onun karşılaştırıldığı işaretçi küçüktür.  
  
##  <a name="operator_t_star"></a>CComPtrBase::operator T *  
 Atama işleci.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sınıf şablonunda tanımlanan nesne veri türü için bir işaretçi döndürür.  
  
##  <a name="p"></a>CComPtrBase::p  
 İşaretçi veri üye değişkeni.  
  
```
T* p;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye değişkeni işaretçi bilgileri tutar.  
  
##  <a name="queryinterface"></a>CComPtrBase::QueryInterface  
 Belirtilen bir arabirim için bir işaretçi döndürmek için bu yöntemi çağırın.  
  
```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `Q`  
 Nesne türü, arabirim işaretçisi gereklidir.  
  
 `pp`  
 İstenen arabirim işaretçisi alan çıkış değişkeninin adresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya E_NOINTERFACE hatası döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır [IUnknown::QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 Hata ayıklama derlemelerinde, bir onaylama hata oluşacaktır *Gö* NULL değerine eşit değil.  
  
##  <a name="release"></a>CComPtrBase::Release  
 Arabirim serbest bırakmak için bu yöntemi çağırın.  
  
```
void Release() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Arabirim yayımlandığı ve [CComPtrBase::p](#p) NULL olarak ayarlandı.  
  
##  <a name="setsite"></a>CComPtrBase::SetSite  
 Sitesi ayarlamak için bu yöntemi çağırın `CComPtrBase` nesnesini **IUnknown** üst nesnenin.  
  
```
HRESULT SetSite(IUnknown* punkParent) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `punkParent`  
 Bir işaretçi **IUnknown** üst arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır [AtlSetChildSite](composite-control-global-functions.md#atlsetchildsite).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
