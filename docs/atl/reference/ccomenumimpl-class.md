---
title: CComEnumImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComEnumImpl
- ATLCOM/ATL::CComEnumImpl
- ATLCOM/ATL::CComEnumImpl::CComEnumImpl
- ATLCOM/ATL::CComEnumImpl::Clone
- ATLCOM/ATL::CComEnumImpl::Init
- ATLCOM/ATL::CComEnumImpl::Next
- ATLCOM/ATL::CComEnumImpl::Reset
- ATLCOM/ATL::CComEnumImpl::Skip
- ATLCOM/ATL::CComEnumImpl::m_begin
- ATLCOM/ATL::CComEnumImpl::m_dwFlags
- ATLCOM/ATL::CComEnumImpl::m_end
- ATLCOM/ATL::CComEnumImpl::m_iter
- ATLCOM/ATL::CComEnumImpl::m_spUnk
dev_langs:
- C++
helpviewer_keywords:
- CComEnumImpl class
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14c7b1e72db3337b786a0e524ae3d8da964f6bbc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ccomenumimpl-class"></a>CComEnumImpl sınıfı
Bu sınıf numaralandırılan öğeleri bir dizide depolandığı COM Numaralandırıcı arabirimi uygulamasını sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Base,
    const IID* piid, class T, class Copy>  
class ATL_NO_VTABLE CComEnumImpl : public Base
```  
  
#### <a name="parameters"></a>Parametreler  
 `Base`  
 Bir COM Numaralandırıcı ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) arabirimi.  
  
 `piid`  
 Numaralandırıcı arabirimi arabirim kimliği için bir işaretçi.  
  
 `T`  
 Numaralandırıcı arabirimi tarafından gösterilen öğenin türü.  
  
 `Copy`  
 Bir homojen [kopyalama ilke sınıfı](../../atl/atl-copy-policy-classes.md).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComEnumImpl::CComEnumImpl](#ccomenumimpl)|Oluşturucu.|  
|[CComEnumImpl:: ~ CComEnumImpl](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComEnumImpl::Clone](#clone)|Uygulaması [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx).|  
|[CComEnumImpl::Init](#init)|Numaralayıcı başlatır.|  
|[CComEnumImpl::Next](#next)|Uygulaması [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx).|  
|[CComEnumImpl::Reset](#reset)|Uygulaması [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx).|  
|[CComEnumImpl::Skip](#skip)|Uygulaması [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx).|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComEnumImpl::m_begin](#m_begin)|Dizinin ilk öğesi için bir işaretçi.|  
|[CComEnumImpl::m_dwFlags](#m_dwflags)|Aracılığıyla geçirilen bayraklar kopyalama `Init`.|  
|[CComEnumImpl::m_end](#m_end)|Dizi son öğenin yalnızca ötesinde konuma bir işaretçi.|  
|[CComEnumImpl::m_iter](#m_iter)|Dizideki geçerli öğe için bir işaretçi.|  
|[CComEnumImpl::m_spUnk](#m_spunk)|**IUnknown** numaralandırılan koleksiyonu sağladığını nesne işaretçisi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComEnumImpl` Numaralandırılan öğeleri bir dizide depolandığı COM Numaralandırıcı arabirimi uygulamasını sağlar. Bu sınıf için paraleldir `IEnumOnSTLImpl` Numaralandırıcı arabirim uygulaması sağlayan sınıfı, temel bir C++ Standart Kitaplığı kapsayıcıda.  
  
> [!NOTE]
>  Daha fazla arasındaki farklar hakkında ayrıntılı bilgi için `CComEnumImpl` ve `IEnumOnSTLImpl`, bkz: [CComEnumImpl::Init](#init).  
  
 Genellikle, şunları yapacaksınız *değil* kendi Numaralandırıcı sınıfı bu arabirimi uygulamasından türetme tarafından oluşturmanız gerekir. Bir dizisine göre bir ATL sağlanan Numaralandırıcı kullanmak istiyorsanız, bir örneğini oluşturmak için daha yaygın [CComEnum](../../atl/reference/ccomenum-class.md).  
  
 Ancak, özel Numaralandırıcı (örneğin, bir numaralandırıcı arabirimi yanı sıra arabirimleri kullanıma sunan) sağlamak gerekiyorsa bu sınıfından türetilir. Bu durumda, geçersiz kılma gerekecektir büyük olasılıkla [CComEnumImpl::Clone](#clone) kendi uygulama sunmak amacıyla yöntemi.  
  
 Daha fazla bilgi için bkz: [ATL koleksiyonları ve numaralandırmalar](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Base`  
  
 `CComEnumImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="ccomenumimpl"></a>  CComEnumImpl::CComEnumImpl  
 Oluşturucu.  
  
```
CComEnumImpl();
```  
  
##  <a name="dtor"></a>  CComEnumImpl:: ~ CComEnumImpl  
 Yok Edicisi.  
  
```
~CComEnumImpl();
```  
  
##  <a name="init"></a>  CComEnumImpl::Init  
 Numaralandırıcı arabirimi tüm istemciler için bir işaretçi geçirmeden önce bu yöntemi çağırmanız gerekir.  
  
```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```  
  
### <a name="parameters"></a>Parametreler  
 *Başlangıç*  
 Numaralandırılacak öğeleri içeren dizisinin ilk öğesi için bir işaretçi.  
  
 `end`  
 Numaralandırılacak öğeleri içeren dizinin son öğenin yalnızca ötesinde konuma bir işaretçi.  
  
 *pUnk*  
 [in] **IUnknown** işaretçi nesnenin Numaralandırıcı ömrü boyunca Canlı tutulmalıdır. Geçirmek **NULL** böyle bir nesne varsa.  
  
 `flags`  
 Numaralandırıcı dizinin sahipliğini ya da bir kopyasını oluşturun olup olmadığını belirleyen bayrak. Olası değerler aşağıda açıklanmıştır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi yalnızca bir kez çağırın — Numaralandırıcı başlatmak, bunu kullanın ve sonra hemen throw.  
  
 Başka bir nesnede yer alacak bir dizi öğeleri işaretçileri geçirin (ve verileri kopyalamak için Numaralandırıcı sorma varsa), kullanabileceğiniz *pUnk* nesne ve bu dizi Numaralandırıcı olarak uzun bir süredir kullanılabilir olduğundan emin olmak için parametresi bunları gerekir. Numaralayıcı yalnızca etkin kalmasını sağlamak için bir nesne üzerinde bir COM referansı tutar. Numaralayıcı bozulduğunda COM başvurusu otomatik olarak yayımlanır.  
  
 `flags` Parametresi Numaralandırıcı kendisine geçirilen dizi öğeleri nasıl işler belirtmenize olanak verir. `flags` değerlerinden birini alabilir **CComEnumFlags** numaralandırma aşağıda gösterilmektedir:  
  
```  
enum CComEnumFlags  
   {  
   AtlFlagNoCopy = 0,  
   AtlFlagTakeOwnership = 2, // BitOwn  
   AtlFlagCopy = 3           // BitOwn | BitCopy  
   };  
```  
  
 **AtlFlagNoCopy** dizinin yaşam numaralandırıcı tarafından denetlenmeyen anlamına gelir. Bu durumda, ya da dizi statik veya tarafından tanımlanan nesne olacak *pUnk* artık gerekli olmadığında dizi boşaltma için sorumlu olacaktır.  
  
 **AtlFlagTakeOwnership** yok etme dizisi sıralayıcı tarafından denetlenmesini anlamına gelir. Bu durumda, dizi dinamik olarak kullanarak tahsis edilmiş gerekir **yeni**. Numaralayıcı kendi yıkıcı dizisinde silinmesine neden olur. Genellikle, geçip geçmeyeceğini **NULL** için *pUnk*, ancak hala Numaralandırıcı yok etme herhangi bir nedenden dolayı bildirilmesini gerekiyorsa, geçerli bir işaretçi geçirebilirsiniz.  
  
 **AtlFlagCopy** yeni bir dizi geçirilen dizi kopyalayarak oluşturulması anlamına gelir `Init`. Yeni dizinin yaşam numaralandırıcı tarafından denetlenmesi sağlamaktır. Numaralayıcı kendi yıkıcı dizisinde silinmesine neden olur. Genellikle, geçip geçmeyeceğini **NULL** için *pUnk*, ancak hala Numaralandırıcı yok etme herhangi bir nedenden dolayı bildirilmesini gerekiyorsa, geçerli bir işaretçi geçirebilirsiniz.  
  
> [!NOTE]
>  Bu yöntem prototip türünden olduğu dizi öğeleri belirtir **T**, burada **T** sınıfına şablon parametresi olarak tanımlandı. COM arabirimi yoluyla metodunun aynı türü budur [CComEnumImpl::Next](#next). Bu uygulanır, benzemez [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md), bu sınıfın farklı depolama desteklemez ve sunulan veri türleri. Dizideki öğeler veri türünü COM arabirimi yoluyla kullanıma sunulan veri türü ile aynı olmalıdır.  
  
##  <a name="clone"></a>  CComEnumImpl::Clone  
 Bu yöntem uygulamasını sağlar [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx) türünde bir nesne oluşturarak yöntemi `CComEnum`, aynı dizi ve geçerli nesne tarafından kullanılan yineleyici başlatma ve üzerinde arabirimi döndürme Yeni oluşturulan nesnenin.  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>Parametreler  
 `ppEnum`  
 [out] Yeni oluşturulan nesnenin Numaralandırıcı arabirimde geçerli Numaralandırıcının kopyalandı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Kopyalanan numaralandırıcılar hiçbir zaman kendi yapmanızı not özgün numaralandırıcı tarafından kullanılan verilerin kopyasını (veya sahipliği). Gerekirse, kopyalanan numaralandırıcılar özgün Numaralandırıcı Canlı (COM başvurusu kullanarak) ihtiyaç duydukları sürece verileri için kullanılabilir olduğundan emin olmak için tutar.  
  
##  <a name="m_spunk"></a>  CComEnumImpl::m_spUnk  
 Bu akıllı işaretçi geçirilen nesne üzerinde bir başvuru tutar [CComEnumImpl::Init](#init), onu Numaralandırıcı ömrü boyunca etkin kalmasını sağlama.  
  
```
CComPtr<IUnknown> m_spUnk;
```  
  
##  <a name="m_begin"></a>  CComEnumImpl::m_begin  
 Numaralandırılacak öğeleri içeren dizinin son öğenin yalnızca ötesinde konuma bir işaretçi.  
  
```
T* m_begin;
```  
  
##  <a name="m_end"></a>  CComEnumImpl::m_end  
 Numaralandırılacak öğeleri içeren dizisinin ilk öğesi için bir işaretçi.  
  
```
T* m_end;
```  
  
##  <a name="m_iter"></a>  CComEnumImpl::m_iter  
 Numaralandırılacak öğeleri içeren dizinin geçerli öğe için bir işaretçi.  
  
```
T* m_iter;
```  
  
##  <a name="m_dwflags"></a>  CComEnumImpl::m_dwFlags  
 Geçirilen bayraklar [CComEnumImpl::Init](#init).  
  
```
DWORD m_dwFlags;
```  
  
##  <a name="next"></a>  CComEnumImpl::Next  
 Bu yöntem uygulamasını sağlar [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) yöntemi.  
  
```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```  
  
### <a name="parameters"></a>Parametreler  
 `celt`  
 [in] İstenen öğe sayısı.  
  
 `rgelt`  
 [out] Öğeleri ile doldurulması dizisi.  
  
 `pceltFetched`  
 [out] Gerçekte döndürülen öğe sayısını `rgelt`. Bu, değerinden `celt` varsa, daha az `celt` öğeleri listede kalan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="reset"></a>  CComEnumImpl::Reset  
 Bu yöntem uygulamasını sağlar [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx) yöntemi.  
  
```
STDMETHOD(Reset)(void);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="skip"></a>  CComEnumImpl::Skip  
 Bu yöntem uygulamasını sağlar [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx) yöntemi.  
  
```
STDMETHOD(Skip)(ULONG celt);
```  
  
### <a name="parameters"></a>Parametreler  
 `celt`  
 [in] Atlamak için öğe sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 E_INVALIDARG döndürür `celt` sıfırsa, S_FALSE değerinden döndürür `celt` öğeler döndürülür, S_OK döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IEnumOnSTLImpl sınıfı](../../atl/reference/ienumonstlimpl-class.md)   
 [CComEnum sınıfı](../../atl/reference/ccomenum-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
