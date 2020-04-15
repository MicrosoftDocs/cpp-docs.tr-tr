---
title: IEnumOnSTLImpl Sınıfı
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
ms.openlocfilehash: 2fbe6ccfbea2836c42a054da7ea9ebeac4e1555d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329707"
---
# <a name="ienumonstlimpl-class"></a>IEnumOnSTLImpl Sınıfı

Bu sınıf, C++ Standart Kitaplık koleksiyonuna dayalı bir yerumerator arabirimi tanımlar.

## <a name="syntax"></a>Sözdizimi

```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
Bir COM kayıt örnecisi. Bir örnek için [IEnumString'e](/windows/win32/api/objidl/nn-objidl-ienumstring) bakın.

*piid*<br/>
Yerumerator arabiriminin arabirim kimliğine işaretçi.

*T*<br/>
Enumerator arabirimi tarafından maruz kalan öğenin türü.

*Kopyala*<br/>
Bir [kopya ilkesi sınıfı.](../../atl/atl-copy-policy-classes.md)

*CollType*<br/>
C++ Standart Kitaplık kapsayıcı sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IEnumOnSTLImpl::Klon](#clone)|**Klon**uygulanması .|
|[IEnumOnSTLImpl::Init](#init)|Enumerator'u başharfe iter.|
|[IEnumOnSTLImpl::Sonraki](#next)|**Sonraki'nin**uygulanması .|
|[IEnumOnSTLImpl::Sıfırlama](#reset)|**Sıfırla**uygulaması.|
|[IEnumOnSTLImpl::Atla](#skip)|**Skip**uygulaması.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[IEnumOnSTLImpl::m_iter](#m_iter)|Herumerator'un koleksiyondaki geçerli konumunu temsil eden yineleyici.|
|[IEnumOnSTLImpl::m_pcollection](#m_pcollection)|Öğeleri numaralandırılacak tutan C++ Standart Kitaplık kapsayıcısına işaretçi.|
|[IEnumOnSTLImpl::m_spUnk](#m_spunk)|Koleksiyonu `IUnknown` sağlayan nesnenin işaretçisi.|

## <a name="remarks"></a>Açıklamalar

`IEnumOnSTLImpl`numaralandırılan öğelerin C++ Standart Kitaplık uyumlu bir kapsayıcıda depolandığı com numaralandırıcı arabirimi için uygulama sağlar. Bu sınıf, bir diziye dayalı bir numaralandırma arabirimi için bir uygulama sağlayan [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) sınıfına benzer.

> [!NOTE]
> [Bkz. CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init) arasındaki `CComEnumImpl` diğer farklar hakkında ayrıntılı bilgi için `IEnumOnSTLImpl`.

Genellikle, bu arabirim uygulamasından türeyen kendi numaralandırıcı sınıf Oluşturmanız *gerekmez.* Bir C++ Standart Kitaplık kapsayıcısına dayalı bir ATL tarafından sağlanan bir enumerator kullanmak istiyorsanız, [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)bir örnek oluşturmak için daha yaygındır , ya da [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)türeterek bir sayısallaştırıcı döndürür bir toplama sınıfı oluşturmak için .

Ancak, özel bir sayısallaştırıcı (örneğin, enumerator arabirimine ek olarak arabirimleri ortaya çıkaran) sağlamanız gerekiyorsa, bu sınıftan türemiş olabilirsiniz. Bu durumda, kendi uygulamanızı sağlamak için [Klon](#clone) yöntemini geçersiz kılmanız gerekebilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`IEnumOnSTLImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ienumonstlimplinit"></a><a name="init"></a>IEnumOnSTLImpl::Init

Enumerator'u başharfe iter.

```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```

### <a name="parameters"></a>Parametreler

*pUnkForRelease*<br/>
[içinde] Tümumerator `IUnknown` ömrü boyunca canlı tutulması gereken bir nesnenin işaretçisi. Böyle bir nesne yoksa NULL'u geçirin.

*Koleksiyon*<br/>
Öğeleri numaralandırılacak tutan C++ Standart Kitaplık kapsayıcısına yapılan başvuru.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Başka bir `Init` nesnede tutulan bir koleksiyona başvuru yutarak, nesnenin ve tuttuğu koleksiyonun, sayısallaştırıcının ihtiyacı olduğu sürece kullanılabilir olmasını sağlamak için *pUnkForRelease* parametresini kullanabilirsiniz.

Herhangi bir istemciye geri sayısalçağrı arabirimine bir işaretçi geçmeden önce bu yöntemi aramak gerekir.

## <a name="ienumonstlimplclone"></a><a name="clone"></a>IEnumOnSTLImpl::Klon

Bu yöntem, bir **Clone** tür `CComEnumOnSTL`nesne oluşturarak, aynı koleksiyon ve geçerli nesne tarafından kullanılan yineleyici ile başlatılan ve yeni oluşturulan nesne üzerinde arabirimi döndürerek Klon yönteminin uygulanmasını sağlar.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>Parametreler

*ppEnum*<br/>
[çıkış] Yeni oluşturulan bir nesnenin enumeratör arabirimi, geçerli sayısallaştırıcıdan klonlandı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ienumonstlimplm_spunk"></a><a name="m_spunk"></a>IEnumOnSTLImpl::m_spUnk

Koleksiyonu `IUnknown` sağlayan nesnenin işaretçisi.

```
CComPtr<IUnknown> m_spUnk;
```

### <a name="remarks"></a>Açıklamalar

Bu akıllı [işaretçi, IEnumOnSTLImpl'e](#init)geçen nesne üzerinde bir referans tutar::Init , enumerator ömrü boyunca canlı kalmasını sağlar.

## <a name="ienumonstlimplm_pcollection"></a><a name="m_pcollection"></a>IEnumOnSTLImpl::m_pcollection

Bu üye, numaralandırıcı arabiriminin uygulanmasını sağlayan verileri sağlayan koleksiyona işaret ediyor.

```
CollType* m_pcollection;
```

### <a name="remarks"></a>Açıklamalar

Bu üye [IEnumOnSTLImpl](#init)bir çağrı ile başharfle::Init .

## <a name="ienumonstlimplm_iter"></a><a name="m_iter"></a>IEnumOnSTLImpl::m_iter

Bu üye, koleksiyondaki geçerli konumu işaretlemek ve sonraki öğelere gitmek için kullanılan yineleyiciyi tutar.

```
CollType::iterator m_iter;
```

## <a name="ienumonstlimplnext"></a><a name="next"></a>IEnumOnSTLImpl::Sonraki

Bu yöntem **Sonraki** yöntemin uygulanmasını sağlar.

```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```

### <a name="parameters"></a>Parametreler

*Celt*<br/>
[içinde] İstenen öğe sayısı.

*Rgelt*<br/>
[çıkış] Öğelerle doldurulacak dizi.

*pceltFetched*<br/>
[çıkış] *Rgelt'te*döndürülen öğelerin sayısı. Listede *keltten* daha az eleman kalırsa bu *keltten* daha az olabilir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ienumonstlimplreset"></a><a name="reset"></a>IEnumOnSTLImpl::Sıfırlama

Bu **yöntem, Sıfırlama** yönteminin uygulanmasını sağlar.

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ienumonstlimplskip"></a><a name="skip"></a>IEnumOnSTLImpl::Atla

Bu **yöntem, Atlama** yönteminin uygulanmasını sağlar.

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>Parametreler

*Celt*<br/>
[içinde] Atlasılayacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
