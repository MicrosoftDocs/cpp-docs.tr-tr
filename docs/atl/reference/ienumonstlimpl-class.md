---
title: IEnumOnSTLImpl sınıfı
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
ms.openlocfilehash: 7cf777f3ff0d298f224157735a06bf57a2c10cf5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495869"
---
# <a name="ienumonstlimpl-class"></a>IEnumOnSTLImpl sınıfı

Bu sınıf, C++ standart kitaplık koleksiyonu temelinde bir Numaralandırıcı arabirimi tanımlar.

## <a name="syntax"></a>Sözdizimi

```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
COM numaralandırıcısı. Örnek için bkz. [IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) .

*piıd*<br/>
Numaralandırıcı arabiriminin arabirim KIMLIĞINE yönelik bir işaretçi.

*ŞI*<br/>
Numaralandırıcı arabirimi tarafından kullanıma sunulan öğenin türü.

*Kopyala*<br/>
Bir [kopyalama ilkesi sınıfı](../../atl/atl-copy-policy-classes.md).

*CollType*<br/>
C++ Standart kitaplık kapsayıcı sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IEnumOnSTLImpl:: Clone](#clone)|**Kopyanın**uygulanması.|
|[IEnumOnSTLImpl:: Init](#init)|Numaralandırıcı başlatır.|
|[IEnumOnSTLImpl:: Next](#next)|**Sonraki**uygulama.|
|[IEnumOnSTLImpl:: Reset](#reset)|**Sıfırlama**uygulamasının uygulanması.|
|[IEnumOnSTLImpl:: Skip](#skip)|Atlanmayı uygulama.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[IEnumOnSTLImpl:: m_iter](#m_iter)|Numaralandırıcı içerisindeki geçerli konumu temsil eden Yineleyici.|
|[IEnumOnSTLImpl:: m_pcollection](#m_pcollection)|Numaralandırılacak öğeleri tutan C++ standart kitaplık kapsayıcısına yönelik bir işaretçi.|
|[IEnumOnSTLImpl:: m_spUnk](#m_spunk)|Koleksiyonu sağlayan nesnenin işaretçisi. `IUnknown`|

## <a name="remarks"></a>Açıklamalar

`IEnumOnSTLImpl`numaralandırılmakta olan öğelerin standart kitaplık ile uyumlu bir C++ kapsayıcıda DEPOLANDıĞı bir com Numaralandırıcı arabirimi için uygulama sağlar. Bu sınıf [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) sınıfına benzer ve bir diziyi temel alan bir Numaralandırıcı arabirimine yönelik bir uygulama sağlar.

> [!NOTE]
>  `CComEnumImpl` Ve arasındaki`IEnumOnSTLImpl`diğer farklılıklar hakkında daha fazla bilgi için bkz. [CComEnumImpl:: Init](../../atl/reference/ccomenumimpl-class.md#init) .

Genellikle, bu arabirim uygulamasından türeterek kendi Numaralandırıcı sınıfınızı oluşturmanız gerekmez. C++ Standart kitaplık kapsayıcısını temel alan ATL tarafından sağlanan bir Numaralandırıcı kullanmak Istiyorsanız, [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)'nin bir örneğini oluşturmak veya ıollectiononstlımpl öğesinden türeterek bir Numaralandırıcı döndüren bir koleksiyon sınıfı oluşturmak daha yaygındır. [ ](../../atl/reference/icollectiononstlimpl-class.md).

Ancak, özel bir Numaralandırıcı sağlamanız gerekiyorsa (örneğin, Numaralandırıcı arabirimine ek olarak arabirimler sunan bir tane), bu sınıftan türetebilirsiniz. Bu durumda, kendi uygulamanızı sağlamak için [Clone](#clone) metodunu geçersiz kılmanız gerekir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`IEnumOnSTLImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="init"></a>IEnumOnSTLImpl:: Init

Numaralandırıcı başlatır.

```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```

### <a name="parameters"></a>Parametreler

*pUnkForRelease*<br/>
'ndaki Numaralandırıcının ömrü boyunca etkin tutulması gereken bir nesne işaretçisi.`IUnknown` Böyle bir nesne yoksa NULL değeri geçirin.

*koleksiyon*<br/>
Numaralandırılacak öğeleri tutan C++ standart kitaplık kapsayıcısına başvuru.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Başka bir nesnede `Init` tutulan bir koleksiyona başvuru geçirirseniz, nesnenin ve sahip olduğu koleksiyonun, Numaralandırıcı için gereken süre için kullanılabilir olduğundan emin olmak için *pUnkForRelease* parametresini kullanabilirsiniz.

Numaralandırıcı arabirimine bir işaretçiyi bir istemciye geri geçirmeden önce bu yöntemi çağırmanız gerekir.

##  <a name="clone"></a>IEnumOnSTLImpl:: Clone

Bu yöntem, türünde `CComEnumOnSTL`bir nesne oluşturarak, onu geçerli nesne tarafından kullanılan aynı koleksiyon ve yineleyici ile başlatarak ve yeni oluşturulan nesne üzerinde arabirimini döndürerek **kopyalama** yönteminin uygulanmasını sağlar.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>Parametreler

*ppEnum*<br/>
dışı Geçerli numaralandırıcıdan kopyalanmış yeni oluşturulan nesne üzerindeki Numaralandırıcı arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="m_spunk"></a>IEnumOnSTLImpl:: m_spUnk

Koleksiyonu sağlayan nesnenin işaretçisi. `IUnknown`

```
CComPtr<IUnknown> m_spUnk;
```

### <a name="remarks"></a>Açıklamalar

Bu akıllı işaretçi, [IEnumOnSTLImpl:: Init](#init)öğesine geçirilen nesne üzerinde bir başvuru tutar ve bu, Numaralandırıcının ömrü boyunca canlı kalmasını sağlar.

##  <a name="m_pcollection"></a>IEnumOnSTLImpl:: m_pcollection

Bu üye, Numaralandırıcı arabiriminin uygulamasını yönlendiren verileri sağlayan koleksiyona işaret eder.

```
CollType* m_pcollection;
```

### <a name="remarks"></a>Açıklamalar

Bu üye bir [IEnumOnSTLImpl:: Init](#init)çağrısıyla başlatılır.

##  <a name="m_iter"></a>IEnumOnSTLImpl:: m_iter

Bu üye, koleksiyon içindeki geçerli konumu işaretlemek için kullanılan yineleyiciyi barındırır ve sonraki öğelere gider.

```
CollType::iterator m_iter;
```

##  <a name="next"></a>IEnumOnSTLImpl:: Next

Bu yöntem, **Next** yönteminin uygulanmasını sağlar.

```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```

### <a name="parameters"></a>Parametreler

*celt*<br/>
'ndaki İstenen öğe sayısı.

*rgelt*<br/>
dışı Öğeleriyle doldurulacak dizi.

*Pceltfettiz*<br/>
dışı Aslında *rgelt*'de döndürülen öğelerin sayısı. Bu, celt öğelerinden daha azı listede kalırsa bu değerden daha az olabilir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="reset"></a>IEnumOnSTLImpl:: Reset

Bu yöntem, **sıfırlama** yönteminin uygulanmasını sağlar.

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="skip"></a>IEnumOnSTLImpl:: Skip

Bu yöntem, **Skip** yönteminin uygulanmasını sağlar.

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>Parametreler

*celt*<br/>
'ndaki Atlanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
