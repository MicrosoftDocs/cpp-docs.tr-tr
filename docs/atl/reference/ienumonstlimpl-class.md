---
title: Ienumonstlımpl sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- IEnumOnSTLImpl class
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
ms.openlocfilehash: 8ff29522351b542d0b674bc173040d4468d00f1c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57277455"
---
# <a name="ienumonstlimpl-class"></a>Ienumonstlımpl sınıfı

Bu sınıf, bir C++ Standart Kitaplığı koleksiyonuna bağlı bir numaralandırıcı arabirimi tanımlar.

## <a name="syntax"></a>Sözdizimi

```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```

#### <a name="parameters"></a>Parametreler

*temel*<br/>
Bir COM Numaralandırıcı. Bkz: [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) örneği.

*piid*<br/>
Numaralandırıcı arabirimi arabirim kimliği için bir işaretçi.

*T*<br/>
Numaralandırıcı arabirim tarafından sunulan öğe türü.

*Kopyala*<br/>
A [kopyalama İlkesi sınıfı](../../atl/atl-copy-policy-classes.md).

*CollType*<br/>
Bir C++ Standart Kitaplığı kapsayıcı sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IEnumOnSTLImpl::Clone](#clone)|Uygulamasını **kopya**.|
|[IEnumOnSTLImpl::Init](#init)|Numaralandırıcı başlatır.|
|[IEnumOnSTLImpl::Next](#next)|Uygulamasını **sonraki**.|
|[IEnumOnSTLImpl::Reset](#reset)|Uygulamasını **sıfırlama**.|
|[IEnumOnSTLImpl::Skip](#skip)|Uygulamasını **atla**.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[IEnumOnSTLImpl::m_iter](#m_iter)|Numaralandırıcı koleksiyondaki geçerli konumunu gösteren yineleyici.|
|[IEnumOnSTLImpl::m_pcollection](#m_pcollection)|Numaralandırılacak öğelerini bulunduran standart C++ Kitaplığı kapsayıcı için bir işaretçi.|
|[IEnumOnSTLImpl::m_spUnk](#m_spunk)|`IUnknown` İşaretçi koleksiyonu sağlayan nesne.|

## <a name="remarks"></a>Açıklamalar

`IEnumOnSTLImpl` Numaralandırılan öğeleri bir C++ Standart kitaplığı ile uyumlu kapsayıcıda depolandığı bir COM Numaralandırıcı arabirim uygulamasını sağlar. Bu sınıf için benzer [Ccomenumımpl](../../atl/reference/ccomenumimpl-class.md) Numaralandırıcı arabiriminin bir uygulamasını sağlar sınıfını tabanlı bir dizi üzerinde.

> [!NOTE]
>  Bkz: [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init) daha arasındaki farklar hakkında ayrıntılı bilgi için `CComEnumImpl` ve `IEnumOnSTLImpl`.

Genellikle, görüntüler *değil* kendi Numaralandırıcı sınıfı bu arabirimi uygulamasından türetilerek oluşturmanız gerekir. Bir C++ Standart Kitaplığı kapsayıcı dayalı bir ATL sağlanan Numaralandırıcı kullanmak istiyorsanız, bir örneğini oluşturmak için daha yaygın [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md), veya türetilenbirnumaralandırıcıdöndürür.birkoleksiyonsınıfıoluşturmakiçin[Icollectiononstlımpl](../../atl/reference/icollectiononstlimpl-class.md).

Ancak, özel bir numaralandırıcı (örneğin, bir numaralandırıcı arabirimi yanı sıra arabirimleri kullanıma açıp) sağlamak gerekiyorsa, bu sınıftan türetebilirsiniz. Bu durumda geçersiz kılma gerekecektir olma olasılığı yüksektir [kopya](#clone) kendi uygulamasını sağlamak için yöntemi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`IEnumOnSTLImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="init"></a>  IEnumOnSTLImpl::Init

Numaralandırıcı başlatır.

```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```

### <a name="parameters"></a>Parametreler

*pUnkForRelease*<br/>
[in] `IUnknown` İşaretçiyi nesnenin Numaralandırıcı yaşam süresi boyunca canlı olarak tutulmalıdır. Böyle bir nesne varsa, NULL geçirin.

*Koleksiyon*<br/>
Numaralandırılacak öğelerini tutan C++ Standart Kitaplığı kapsayıcıya bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Geçirirseniz `Init` kullanabileceğiniz başka bir nesnede bir koleksiyona başvuruyu tutulan *pUnkForRelease* nesne ve koleksiyon başvuruysa, kullanılabilecek Numaralandırıcı ihtiyaç duyduğu sürece emin olmak için parametre.

Numaralandırıcı arabirimine tüm istemciler için bir işaretçi geçirmeden önce bu yöntemi çağırmanız gerekir.

##  <a name="clone"></a>  IEnumOnSTLImpl::Clone

Bu yöntem uygulamasını sağlar **kopya** türünde bir nesne oluşturarak yöntemi `CComEnumOnSTL`, aynı koleksiyon ve geçerli nesne tarafından kullanılan yineleyici başlatma ve üzerinde arabirimi döndüren yeni oluşturulan nesne.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>Parametreler

*ppEnum*<br/>
[out] Yeni oluşturulan bir nesneye Numaralandırıcı arabirimde geçerli Numaralandırıcının kopyalandı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="m_spunk"></a>  IEnumOnSTLImpl::m_spUnk

`IUnknown` İşaretçi koleksiyonu sağlayan nesne.

```
CComPtr<IUnknown> m_spUnk;
```

### <a name="remarks"></a>Açıklamalar

Bu akıllı işaretçi geçirilen nesne üzerinde bir başvuru tutan [IEnumOnSTLImpl::Init](#init), bu Numaralandırıcının yaşam süresi boyunca Canlı çalışmayı sürdürdüğünden emin olma.

##  <a name="m_pcollection"></a>  IEnumOnSTLImpl::m_pcollection

Bu üye Numaralandırıcı arabiriminin uygulamasını yönlendiren veriler sağlayan koleksiyona işaret eder.

```
CollType* m_pcollection;
```

### <a name="remarks"></a>Açıklamalar

Bu üye yapılan bir çağrıyla başlatılır [IEnumOnSTLImpl::Init](#init).

##  <a name="m_iter"></a>  IEnumOnSTLImpl::m_iter

Bu üye, koleksiyon içindeki geçerli konumu işaretlemek ve sonraki öğelerde gezinmek için kullanılan yineleyici tutar.

```
CollType::iterator m_iter;
```

##  <a name="next"></a>  IEnumOnSTLImpl::Next

Bu yöntem uygulamasını sağlar **sonraki** yöntemi.

```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```

### <a name="parameters"></a>Parametreler

*celt*<br/>
[in] İstenen öğe sayısı.

*rgelt*<br/>
[out] Öğeleri ile doldurulacak dizisi.

*pceltFetched*<br/>
[out] Gerçekte döndürülen öğe sayısını *rgelt*. Bu kısa *celt* az olursa *celt* öğeleri listesinde kalır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="reset"></a>  IEnumOnSTLImpl::Reset

Bu yöntem uygulamasını sağlar **sıfırlama** yöntemi.

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="skip"></a>  IEnumOnSTLImpl::Skip

Bu yöntem uygulamasını sağlar **atla** yöntemi.

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>Parametreler

*celt*<br/>
[in] Geçilecek öğelerin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
