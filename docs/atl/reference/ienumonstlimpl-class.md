---
description: 'Şu konuda daha fazla bilgi edinin: IEnumOnSTLImpl sınıfı'
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
ms.openlocfilehash: 33bc34288ebd03f987532ebb078fed62ce2204c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139496"
---
# <a name="ienumonstlimpl-class"></a>IEnumOnSTLImpl sınıfı

Bu sınıf, bir C++ standart kitaplığı koleksiyonunu temel alan bir Numaralandırıcı arabirimi tanımlar.

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

*T*<br/>
Numaralandırıcı arabirimi tarafından kullanıma sunulan öğenin türü.

*Kopyala*<br/>
Bir [kopyalama ilkesi sınıfı](../../atl/atl-copy-policy-classes.md).

*CollType*<br/>
C++ standart kitaplığı kapsayıcı sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IEnumOnSTLImpl:: Clone](#clone)|**Kopyanın** uygulanması.|
|[IEnumOnSTLImpl:: Init](#init)|Numaralandırıcı başlatır.|
|[IEnumOnSTLImpl:: Next](#next)|**Sonraki** uygulama.|
|[IEnumOnSTLImpl:: Reset](#reset)|**Sıfırlama** uygulamasının uygulanması.|
|[IEnumOnSTLImpl:: Skip](#skip)|**Atlanmayı** uygulama.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[IEnumOnSTLImpl:: m_iter](#m_iter)|Numaralandırıcı içerisindeki geçerli konumu temsil eden Yineleyici.|
|[IEnumOnSTLImpl:: m_pcollection](#m_pcollection)|Görüntülenecek öğeleri tutan C++ standart kitaplık kapsayıcısına yönelik bir işaretçi.|
|[IEnumOnSTLImpl:: m_spUnk](#m_spunk)|`IUnknown`Koleksiyonu sağlayan nesnenin işaretçisi.|

## <a name="remarks"></a>Açıklamalar

`IEnumOnSTLImpl` numaralandırılmakta olan öğelerin C++ standart kitaplığı ile uyumlu bir kapsayıcıda depolandığı bir COM Numaralandırıcı arabirimi için uygulama sağlar. Bu sınıf [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) sınıfına benzer ve bir diziyi temel alan bir Numaralandırıcı arabirimine yönelik bir uygulama sağlar.

> [!NOTE]
> Ve arasındaki diğer farklılıklar hakkında daha fazla bilgi için bkz. [CComEnumImpl:: Init](../../atl/reference/ccomenumimpl-class.md#init) `CComEnumImpl` `IEnumOnSTLImpl` .

Genellikle, bu arabirim uygulamasından türeterek kendi Numaralandırıcı sınıfınızı *oluşturmanız gerekmez.* C++ standart kitaplık kapsayıcısını temel alan ATL tarafından sağlanan bir Numaralandırıcı kullanmak istiyorsanız, [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)'nin bir örneğini oluşturmak veya [ıollectiononstlımpl](../../atl/reference/icollectiononstlimpl-class.md)öğesinden türeterek bir Numaralandırıcı döndüren bir koleksiyon sınıfı oluşturmak daha yaygındır.

Ancak, özel bir Numaralandırıcı sağlamanız gerekiyorsa (örneğin, Numaralandırıcı arabirimine ek olarak arabirimler sunan bir tane), bu sınıftan türetebilirsiniz. Bu durumda, kendi uygulamanızı sağlamak için [Clone](#clone) metodunu geçersiz kılmanız gerekir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`IEnumOnSTLImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ienumonstlimplinit"></a><a name="init"></a> IEnumOnSTLImpl:: Init

Numaralandırıcı başlatır.

```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```

### <a name="parameters"></a>Parametreler

*pUnkForRelease*<br/>
'ndaki `IUnknown` Numaralandırıcının ömrü boyunca etkin tutulması gereken bir nesne işaretçisi. Böyle bir nesne yoksa NULL değeri geçirin.

*koleksiyon*<br/>
Numaralandırılacak öğeleri tutan C++ standart kitaplık kapsayıcısına başvuru.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

`Init`Başka bir nesnede tutulan bir koleksiyona başvuru geçirirseniz, nesnenin ve sahip olduğu koleksiyonun, Numaralandırıcı için gereken süre için kullanılabilir olduğundan emin olmak Için *pUnkForRelease* parametresini kullanabilirsiniz.

Numaralandırıcı arabirimine bir işaretçiyi bir istemciye geri geçirmeden önce bu yöntemi çağırmanız gerekir.

## <a name="ienumonstlimplclone"></a><a name="clone"></a> IEnumOnSTLImpl:: Clone

Bu yöntem, türünde bir nesne oluşturarak  `CComEnumOnSTL` , onu geçerli nesne tarafından kullanılan aynı koleksiyon ve yineleyici ile başlatarak ve yeni oluşturulan nesne üzerinde arabirimini döndürerek kopyalama yönteminin uygulanmasını sağlar.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>Parametreler

*ppEnum*<br/>
dışı Geçerli numaralandırıcıdan kopyalanmış yeni oluşturulan nesne üzerindeki Numaralandırıcı arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ienumonstlimplm_spunk"></a><a name="m_spunk"></a> IEnumOnSTLImpl:: m_spUnk

`IUnknown`Koleksiyonu sağlayan nesnenin işaretçisi.

```
CComPtr<IUnknown> m_spUnk;
```

### <a name="remarks"></a>Açıklamalar

Bu akıllı işaretçi, [IEnumOnSTLImpl:: Init](#init)öğesine geçirilen nesne üzerinde bir başvuru tutar ve bu, Numaralandırıcının ömrü boyunca canlı kalmasını sağlar.

## <a name="ienumonstlimplm_pcollection"></a><a name="m_pcollection"></a> IEnumOnSTLImpl:: m_pcollection

Bu üye, Numaralandırıcı arabiriminin uygulamasını yönlendiren verileri sağlayan koleksiyona işaret eder.

```
CollType* m_pcollection;
```

### <a name="remarks"></a>Açıklamalar

Bu üye bir [IEnumOnSTLImpl:: Init](#init)çağrısıyla başlatılır.

## <a name="ienumonstlimplm_iter"></a><a name="m_iter"></a> IEnumOnSTLImpl:: m_iter

Bu üye, koleksiyon içindeki geçerli konumu işaretlemek için kullanılan yineleyiciyi barındırır ve sonraki öğelere gider.

```
CollType::iterator m_iter;
```

## <a name="ienumonstlimplnext"></a><a name="next"></a> IEnumOnSTLImpl:: Next

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
dışı Aslında *rgelt*'de döndürülen öğelerin sayısı. Bu, celt öğelerinden *daha azı* listede kalırsa *bu değerden daha* az olabilir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ienumonstlimplreset"></a><a name="reset"></a> IEnumOnSTLImpl:: Reset

Bu yöntem, **sıfırlama** yönteminin uygulanmasını sağlar.

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ienumonstlimplskip"></a><a name="skip"></a> IEnumOnSTLImpl:: Skip

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
