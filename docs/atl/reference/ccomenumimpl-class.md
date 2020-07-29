---
title: CComEnumImpl sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- CComEnumImpl class
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
ms.openlocfilehash: 517a4e90ca21e22dcf161aefcff61a40437eabe0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226613"
---
# <a name="ccomenumimpl-class"></a>CComEnumImpl sınıfı

Bu sınıf, numaralandırılmakta olan öğelerin bir dizide depolandığı bir COM Numaralandırıcı arabirimine yönelik uygulamayı sağlar.

## <a name="syntax"></a>Söz dizimi

```
template <class Base,
    const IID* piid, class T, class Copy>
class ATL_NO_VTABLE CComEnumImpl : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
COM Numaralandırıcı arabirimi. Örnek için bkz. [IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) .

*piıd*<br/>
Numaralandırıcı arabiriminin arabirim KIMLIĞINE yönelik bir işaretçi.

*T*<br/>
Numaralandırıcı arabirimi tarafından kullanıma sunulan öğenin türü.

*Kopyala*<br/>
Homojen [kopya ilke sınıfı](../../atl/atl-copy-policy-classes.md).

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComEnumImpl:: CComEnumImpl](#ccomenumimpl)|Oluşturucu.|
|[CComEnumImpl:: ~ CComEnumImpl](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComEnumImpl:: Clone](#clone)|**Clone** Enumeration Interface yönteminin uygulanması.|
|[CComEnumImpl:: Init](#init)|Numaralandırıcı başlatır.|
|[CComEnumImpl:: Next](#next)|**Sonraki**uygulama.|
|[CComEnumImpl:: Reset](#reset)|**Sıfırlama**uygulamasının uygulanması.|
|[CComEnumImpl:: Skip](#skip)|**Atlanmayı**uygulama.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComEnumImpl:: m_begin](#m_begin)|Dizideki ilk öğe için bir işaretçi.|
|[CComEnumImpl:: m_dwFlags](#m_dwflags)|Kopyalama bayrakları geçti `Init` .|
|[CComEnumImpl:: m_end](#m_end)|Dizideki son öğenin hemen ötesinde konuma yönelik bir işaretçi.|
|[CComEnumImpl:: m_iter](#m_iter)|Dizideki geçerli öğeye yönelik bir işaretçi.|
|[CComEnumImpl:: m_spUnk](#m_spunk)|`IUnknown`Nesnenin, numaralandırılmakta olan koleksiyonu sağlayan işaretçisi.|

## <a name="remarks"></a>Açıklamalar

Yöntem uygulamalarına örnek olarak bkz. [IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) . `CComEnumImpl`numaralandırılmakta olan öğelerin bir dizide depolandığı bir COM Numaralandırıcı arabirimi için uygulama sağlar. Bu sınıf, `IEnumOnSTLImpl` bir C++ standart kitaplık kapsayıcısını temel alan bir Numaralandırıcı arabirimin uygulanmasını sağlayan sınıfına benzerdir.

> [!NOTE]
> Ve arasında daha fazla farklılık hakkındaki ayrıntılar için `CComEnumImpl` `IEnumOnSTLImpl` bkz. [CComEnumImpl:: Init](#init).

Genellikle, bu arabirim uygulamasından türeterek kendi Numaralandırıcı sınıfınızı *oluşturmanız gerekmez.* Bir dizi temelinde ATL tarafından sağlanan bir Numaralandırıcı kullanmak istiyorsanız, [CComEnum](../../atl/reference/ccomenum-class.md)'un bir örneğini oluşturmak daha yaygındır.

Ancak, özel bir Numaralandırıcı sağlamanız gerekiyorsa (örneğin, Numaralandırıcı arabirimine ek olarak arabirimler sunan bir tane), bu sınıftan türetebilirsiniz. Bu durumda, kendi uygulamanızı sağlamak için [CComEnumImpl:: Clone](#clone) metodunu geçersiz kılmanız gerekir.

Daha fazla bilgi için bkz. [atl koleksiyonları ve Numaralandırıcılar](../../atl/atl-collections-and-enumerators.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComEnumImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ccomenumimplccomenumimpl"></a><a name="ccomenumimpl"></a>CComEnumImpl:: CComEnumImpl

Oluşturucu.

```
CComEnumImpl();
```

## <a name="ccomenumimplccomenumimpl"></a><a name="dtor"></a>CComEnumImpl:: ~ CComEnumImpl

Yok edicisi.

```
~CComEnumImpl();
```

## <a name="ccomenumimplinit"></a><a name="init"></a>CComEnumImpl:: Init

Numaralandırıcı arabirimine bir işaretçiyi bir istemciye geri geçirmeden önce bu yöntemi çağırmanız gerekir.

```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```

### <a name="parameters"></a>Parametreler

*başladı*<br/>
Numaralandırılacak öğeleri içeren dizinin ilk öğesine yönelik bir işaretçi.

*erer*<br/>
Numaralandırılacak öğeleri içeren dizinin son öğesinin hemen ötesinde konuma yönelik bir işaretçi.

*pUnk dili*<br/>
'ndaki `IUnknown`Numaralandırıcının ömrü boyunca etkin tutulması gereken bir nesne işaretçisi. Böyle bir nesne yoksa NULL değeri geçirin.

*bayraklar*<br/>
Numaralandırıcının dizinin sahipliğini alıp etmeyeceğini veya bir kopyasını yapıp belirtmeyeceğini belirten bayraklar. Olası değerler aşağıda açıklanmıştır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca bir kez çağırın — numaralandırıcısı başlatın, kullanın ve sonra da oluşturun.

Başka bir nesnede tutulan bir dizide yer alan öğelere işaretçiler geçirirseniz (ve Numaralandırıcının verileri kopyalamasını istememeniz halinde), Numaralandırıcı gereken nesne ve dizinin bulunduğundan emin olmak için *punk* parametresini kullanabilirsiniz. Numaralandırıcı, etkin tutmak için nesne üzerinde bir COM başvurusu tutar. Numaralandırıcı yok edildiğinde COM başvurusu otomatik olarak serbest bırakılır.

*Flags* parametresi, Numaralandırıcının kendisine geçirilen dizi öğelerini nasıl ele almalıdır belirtmenize izin verir. *bayraklar* `CComEnumFlags` aşağıda gösterilen Numaralandırmadaki değerlerden birini alabilir:

```
enum CComEnumFlags
   {
   AtlFlagNoCopy = 0,
   AtlFlagTakeOwnership = 2, // BitOwn
   AtlFlagCopy = 3           // BitOwn | BitCopy
   };
```

`AtlFlagNoCopy`dizinin ömrü Numaralandırıcı tarafından denetlenmediği anlamına gelir. Bu durumda, dizi statik olur ya da *punk* tarafından tanımlanan nesne, artık gerekli olmadığında diziyi boşaltmaktan sorumludur.

`AtlFlagTakeOwnership`dizi yok etme işlemi Numaralandırıcı tarafından denetlenmektedir. Bu durumda, dizisinin kullanılarak dinamik olarak ayrılmış olması gerekir **`new`** . Numaralandırıcı, dizi yıkıcısında diziyi silecektir. Genellikle, *punk*için null değeri geçirirsiniz, ancak bazı nedenlerle Numaralandırıcının yok edilmesiyle ilgili bilgilendirilmeniz gerekiyorsa geçerli bir işaretçiye geçiş yapabilirsiniz.

`AtlFlagCopy`öğesine geçirilen dizi kopyalanarak yeni bir dizi oluşturulacak anlamına gelir `Init` . Yeni dizinin ömrü Numaralandırıcı tarafından denetlenmelidir. Numaralandırıcı, dizi yıkıcısında diziyi silecektir. Genellikle, *punk*için null değeri geçirirsiniz, ancak bazı nedenlerle Numaralandırıcının yok edilmesiyle ilgili bilgilendirilmeniz gerekiyorsa geçerli bir işaretçiye geçiş yapabilirsiniz.

> [!NOTE]
> Bu yöntemin prototipi, `T` `T` sınıf için bir şablon parametresi olarak tanımlandığı gibi dizi öğelerini türünde belirtir. Bu, [CComEnumImpl:: Next](#next)com arabirim yöntemi aracılığıyla ortaya çıkarılan aynı türdür. Bu, [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)'ın aksine, bu sınıfın farklı depolama ve sunulan veri türlerini desteklememesinden farklıdır. Dizideki öğelerin veri türü, COM arabirimi aracılığıyla ortaya çıkarılan veri türüyle aynı olmalıdır.

## <a name="ccomenumimplclone"></a><a name="clone"></a>CComEnumImpl:: Clone

Bu yöntem, türünde bir nesne oluşturarak **Clone** `CComEnum` , geçerli nesne tarafından kullanılan aynı dizi ve yineleyiciyi başlatarak ve yeni oluşturulan nesnesine arabirimini döndürürken Clone yönteminin uygulanmasını sağlar.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>Parametreler

*ppEnum*<br/>
dışı Geçerli numaralandırıcıdan kopyalanmış yeni oluşturulan nesne üzerindeki Numaralandırıcı arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Kopyalanan numaralandırıcıların özgün Numaralandırıcı tarafından kullanılan verilerin kendi kopyasını (veya sahipliğini al) hiçbir zaman yapmadığını unutmayın. Gerekirse, kopyalanmış Numaralandırıcılar, verilerin gerektiği sürece kullanılabilir olmasını sağlamak için özgün Numaralandırıcı canlı kalır (COM başvurusu kullanarak).

## <a name="ccomenumimplm_spunk"></a><a name="m_spunk"></a>CComEnumImpl:: m_spUnk

Bu akıllı işaretçi, [CComEnumImpl:: Init](#init)öğesine geçirilen nesne üzerinde bir başvuru tutar ve bu da Numaralandırıcının ömrü boyunca etkin kalmasını sağlar.

```
CComPtr<IUnknown> m_spUnk;
```

## <a name="ccomenumimplm_begin"></a><a name="m_begin"></a>CComEnumImpl:: m_begin

Numaralandırılacak öğeleri içeren dizinin son öğesinin hemen ötesinde konuma yönelik bir işaretçi.

```
T* m_begin;
```

## <a name="ccomenumimplm_end"></a><a name="m_end"></a>CComEnumImpl:: m_end

Numaralandırılacak öğeleri içeren dizinin ilk öğesine yönelik bir işaretçi.

```
T* m_end;
```

## <a name="ccomenumimplm_iter"></a><a name="m_iter"></a>CComEnumImpl:: m_iter

Numaralandırılacak öğeleri içeren dizinin geçerli öğesine yönelik bir işaretçi.

```
T* m_iter;
```

## <a name="ccomenumimplm_dwflags"></a><a name="m_dwflags"></a>CComEnumImpl:: m_dwFlags

[CComEnumImpl:: Init](#init)öğesine geçirilen bayraklar.

```
DWORD m_dwFlags;
```

## <a name="ccomenumimplnext"></a><a name="next"></a>CComEnumImpl:: Next

Bu yöntem, **Next** yönteminin uygulanmasını sağlar.

```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```

### <a name="parameters"></a>Parametreler

*celt*<br/>
'ndaki İstenen öğe sayısı.

*rgelt*<br/>
dışı Öğelerle doldurulacak dizi.

*Pceltfettiz*<br/>
dışı Aslında *rgelt*'de döndürülen öğelerin sayısı. Bu, *celt* öğelerinden daha azı listede kaldığı takdirde *celt* 'den daha az olabilir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ccomenumimplreset"></a><a name="reset"></a>CComEnumImpl:: Reset

Bu yöntem, **sıfırlama** yönteminin uygulanmasını sağlar.

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ccomenumimplskip"></a><a name="skip"></a>CComEnumImpl:: Skip

Bu yöntem, **Skip** yönteminin uygulanmasını sağlar.

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>Parametreler

*celt*<br/>
'ndaki Atlanacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*Celt* sıfırsa E_INVALIDARG döndürür, *celt* öğelerinden daha azı döndürülürse S_FALSE döndürür, aksi takdirde s_ok döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[IEnumOnSTLImpl sınıfı](../../atl/reference/ienumonstlimpl-class.md)<br/>
[CComEnum sınıfı](../../atl/reference/ccomenum-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
