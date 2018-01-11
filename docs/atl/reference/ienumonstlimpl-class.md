---
title: "IEnumOnSTLImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl::Clone
- ATLCOM/ATL::IEnumOnSTLImpl::Init
- ATLCOM/ATL::IEnumOnSTLImpl::Next
- ATLCOM/ATL::IEnumOnSTLImpl::Reset
- ATLCOM/ATL::IEnumOnSTLImpl::Skip
- ATLCOM/ATL::IEnumOnSTLImpl::m_iter
- ATLCOM/ATL::IEnumOnSTLImpl::m_pcollection
- ATLCOM/ATL::IEnumOnSTLImpl::m_spUnk
dev_langs: C++
helpviewer_keywords: IEnumOnSTLImpl class
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 38d645f7841cb71af9812bd1d62a979752a0343d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ienumonstlimpl-class"></a>IEnumOnSTLImpl sınıfı
Bu sınıf bir C++ Standart Kitaplığı koleksiyona bağlı bir numaralandırıcı arabirimi tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>  
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```  
  
#### <a name="parameters"></a>Parametreler  
 `Base`  
 Bir COM Numaralandırıcı ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) arabirimi.  
  
 `piid`  
 Numaralandırıcı arabirimi arabirim kimliği için bir işaretçi.  
  
 `T`  
 Numaralandırıcı arabirimi tarafından gösterilen öğenin türü.  
  
 `Copy`  
 A [kopyalama ilke sınıfı](../../atl/atl-copy-policy-classes.md).  
  
 `CollType`  
 C++ Standart Kitaplığı kapsayıcı sınıfı.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IEnumOnSTLImpl::Clone](#clone)|Uygulaması [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx).|  
|[IEnumOnSTLImpl::Init](#init)|Numaralayıcı başlatır.|  
|[IEnumOnSTLImpl::Next](#next)|Uygulaması [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx).|  
|[IEnumOnSTLImpl::Reset](#reset)|Uygulaması [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx).|  
|[IEnumOnSTLImpl::Skip](#skip)|Uygulaması [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx).|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IEnumOnSTLImpl::m_iter](#m_iter)|Yineleyici koleksiyonundaki Numaralandırıcının geçerli konumu temsil eder.|  
|[IEnumOnSTLImpl::m_pcollection](#m_pcollection)|Numaralandırılacak öğelerini tutan C++ Standart Kitaplığı kapsayıcı için bir işaretçi.|  
|[IEnumOnSTLImpl::m_spUnk](#m_spunk)|**IUnknown** koleksiyonu sağladığını nesne işaretçisi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IEnumOnSTLImpl`Numaralandırılan öğeleri C++ Standart kitaplığı ile uyumlu kapsayıcısında depolandığı COM Numaralandırıcı arabirimi uygulamasını sağlar. Bu sınıf için paraleldir [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) bir uygulama için bir numaralandırıcı arabirim sağlayan sınıf tabanlı bir dizi.  
  
> [!NOTE]
>  Bkz: [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init) daha fazla arasındaki farklar hakkında ayrıntılı bilgi için `CComEnumImpl` ve `IEnumOnSTLImpl`.  
  
 Genellikle, şunları yapacaksınız *değil* kendi Numaralandırıcı sınıfı bu arabirimi uygulamasından türetme tarafından oluşturmanız gerekir. Bir C++ Standart Kitaplığı kapsayıcı dayalı bir ATL sağlanan Numaralandırıcı kullanmak istiyorsanız, bir örneğini oluşturmak için daha yaygın [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md), türetilenbirnumaralandırıcıdöndürürbirkoleksiyonsınıfıoluşturmakiçinveya[ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md).  
  
 Ancak, özel Numaralandırıcı (örneğin, bir numaralandırıcı arabirimi yanı sıra arabirimleri kullanıma sunan) sağlamak gerekiyorsa bu sınıfından türetilir. Bu durumda geçersiz kılma gerekecektir büyük olasılıkla [kopya](#clone) kendi uygulama sunmak amacıyla yöntemi.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Base`  
  
 `IEnumOnSTLImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="init"></a>IEnumOnSTLImpl::Init  
 Numaralayıcı başlatır.  
  
```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```  
  
### <a name="parameters"></a>Parametreler  
 `pUnkForRelease`  
 [in] **IUnknown** işaretçi nesnenin Numaralandırıcı ömrü boyunca Canlı tutulmalıdır. Geçirmek **NULL** böyle bir nesne varsa.  
  
 `collection`  
 Numaralandırılacak öğelerini tutan C++ Standart Kitaplığı kapsayıcı referansı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçirirseniz `Init` kullanabileceğiniz başka bir nesnenin bir koleksiyona başvuruyu tutulan `pUnkForRelease` nesne ve onun tutan, koleksiyon kullanılabilir olduğunu için gereksinim duyduğu Numaralandırıcı sürece emin olmak için parametresi.  
  
 Numaralandırıcı arabirimi tüm istemciler için bir işaretçi geçirmeden önce bu yöntemi çağırmanız gerekir.  
  
##  <a name="clone"></a>IEnumOnSTLImpl::Clone  
 Bu yöntem uygulamasını sağlar [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx) türünde bir nesne oluşturarak yöntemi `CComEnumOnSTL`, aynı toplama ve geçerli nesne tarafından kullanılan yineleyici başlatma ve üzerinde arabirimi döndürme Yeni oluşturulan nesne.  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>Parametreler  
 `ppEnum`  
 [out] Yeni oluşturulan nesnenin Numaralandırıcı arabirimde geçerli Numaralandırıcının kopyalandı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="m_spunk"></a>IEnumOnSTLImpl::m_spUnk  
 **IUnknown** koleksiyonu sağladığını nesne işaretçisi.  
  
```
CComPtr<IUnknown> m_spUnk;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu akıllı işaretçi geçirilen nesne üzerinde bir başvuru tutar [IEnumOnSTLImpl::Init](#init), onu Numaralandırıcı ömrü boyunca etkin kalmasını sağlama.  
  
##  <a name="m_pcollection"></a>IEnumOnSTLImpl::m_pcollection  
 Bu üye Numaralandırıcı arabirimi uyarlamasını yürüten verileri sağlayan koleksiyona işaret eder.  
  
```
CollType* m_pcollection;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye için bir çağrı tarafından başlatılana [IEnumOnSTLImpl::Init](#init).  
  
##  <a name="m_iter"></a>IEnumOnSTLImpl::m_iter  
 Bu üye koleksiyonun içindeki geçerli konumu işaretlemek ve sonraki öğelerine gezinmek için kullanılan yineleyici tutar.  
  
```
CollType::iterator m_iter;
```  
  
##  <a name="next"></a>IEnumOnSTLImpl::Next  
 Bu yöntem uygulamasını sağlar [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) yöntemi.  
  
```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```  
  
### <a name="parameters"></a>Parametreler  
 `celt`  
 [in] İstenen öğe sayısı.  
  
 `rgelt`  
 [out] Oturum öğeleri doldurulması dizisi.  
  
 `pceltFetched`  
 [out] Gerçekte döndürülen öğe sayısını `rgelt`. Bu, değerinden `celt` varsa, daha az `celt` öğeleri listesinde kalır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="reset"></a>IEnumOnSTLImpl::Reset  
 Bu yöntem uygulamasını sağlar [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx) yöntemi.  
  
```
STDMETHOD(Reset)(void);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="skip"></a>IEnumOnSTLImpl::Skip  
 Bu yöntem uygulamasını sağlar [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx) yöntemi.  
  
```
STDMETHOD(Skip)(ULONG celt);
```  
  
### <a name="parameters"></a>Parametreler  
 `celt`  
 [in] Atlamak için öğe sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
