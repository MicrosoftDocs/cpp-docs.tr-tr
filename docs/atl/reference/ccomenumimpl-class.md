---
title: CComEnumImpl Sınıfı
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
ms.openlocfilehash: 965e0a8bf6c890882754b60e2785832933d1c52c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327857"
---
# <a name="ccomenumimpl-class"></a>CComEnumImpl Sınıfı

Bu sınıf, numaralandırılan öğelerin bir dizide depolandığı bir COM numaralandırma arabirimi için uygulama sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class Base,
    const IID* piid, class T, class Copy>
class ATL_NO_VTABLE CComEnumImpl : public Base
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
Com enumerator arabirimi. Bir örnek için [IEnumString'e](/windows/win32/api/objidl/nn-objidl-ienumstring) bakın.

*piid*<br/>
Yerumerator arabiriminin arabirim kimliğine işaretçi.

*T*<br/>
Enumerator arabirimi tarafından maruz kalan öğenin türü.

*Kopyala*<br/>
Homojen [bir kopya ilkesi sınıfı.](../../atl/atl-copy-policy-classes.md)

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CComEnumImpl::CComEnumImpl](#ccomenumimpl)|Oluşturucu.|
|[CComEnumImpl::~CComEnumImpl](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComEnumImpl::Klon](#clone)|**Klon** numaralandırma arabirimi yönteminin uygulanması.|
|[CComEnumImpl::Init](#init)|Enumerator'u başharfe iter.|
|[CComEnumImpl::Sonraki](#next)|**Sonraki'nin**uygulanması .|
|[CComEnumImpl::Sıfırlama](#reset)|**Sıfırla**uygulaması.|
|[CComEnumImpl::Atla](#skip)|**Skip**uygulaması.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CComEnumImpl::m_begin](#m_begin)|Dizideki ilk öğeiçin bir işaretçi.|
|[CComEnumImpl::m_dwFlags](#m_dwflags)|Kopya bayrakları `Init`geçti.|
|[CComEnumImpl::m_end](#m_end)|Dizideki son öğenin hemen ötesinde ki konuma işaretçi.|
|[CComEnumImpl::m_iter](#m_iter)|Dizideki geçerli öğenin işaretçisi.|
|[CComEnumImpl::m_spUnk](#m_spunk)|Koleksiyonu `IUnknown` sağlayan nesnenin işaretçisi numaralandırılır.|

## <a name="remarks"></a>Açıklamalar

Yöntem uygulamaları örneği için [IEnumString'e](/windows/win32/api/objidl/nn-objidl-ienumstring) bakın. `CComEnumImpl`numaralandırılan öğelerin bir dizide depolandığı com numaralandırıcı arabirimi için uygulama sağlar. Bu sınıf, C++ `IEnumOnSTLImpl` Standart Kitaplık kapsayıcısına dayalı bir numaralandırma arabirimi uygulamasını sağlayan sınıfa benzer.

> [!NOTE]
> ve arasındaki `CComEnumImpl` daha fazla `IEnumOnSTLImpl`fark hakkında daha fazla bilgi için, [CComEnumImpl bakınız::Init](#init).

Genellikle, bu arabirim uygulamasından türeyen kendi numaralandırıcı sınıf Oluşturmanız *gerekmez.* Bir diziye dayalı olarak ATL tarafından sağlanan bir sayısallaştırıcı kullanmak istiyorsanız, [CComEnum'un](../../atl/reference/ccomenum-class.md)bir örneğini oluşturmak daha yaygındır.

Ancak, özel bir sayısallaştırıcı (örneğin, enumerator arabirimine ek olarak arabirimleri ortaya çıkaran) sağlamanız gerekiyorsa, bu sınıftan türemiş olabilirsiniz. Bu durumda, [ccomEnumImpl](#clone) geçersiz kılmak gerekir muhtemeldir::Kendi uygulama sağlamak için Klon yöntemi.

Daha fazla bilgi için [ATL Koleksiyonları ve Sayısallaştırıcılar'a](../../atl/atl-collections-and-enumerators.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Base`

`CComEnumImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomenumimplccomenumimpl"></a><a name="ccomenumimpl"></a>CComEnumImpl::CComEnumImpl

Oluşturucu.

```
CComEnumImpl();
```

## <a name="ccomenumimplccomenumimpl"></a><a name="dtor"></a>CComEnumImpl::~CComEnumImpl

Yıkıcı.

```
~CComEnumImpl();
```

## <a name="ccomenumimplinit"></a><a name="init"></a>CComEnumImpl::Init

Herhangi bir istemciye geri sayısalçağrı arabirimine bir işaretçi geçmeden önce bu yöntemi aramak gerekir.

```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```

### <a name="parameters"></a>Parametreler

*Başlamak*<br/>
Numaralandırılacak öğeleri içeren dizinin ilk öğesine işaretçi.

*Son -unda*<br/>
Numaralandırılacak öğeleri içeren dizinin son öğesinin hemen ötesinde ki konuma işaretçi.

*Punk*<br/>
[içinde] Tümumerator `IUnknown` ömrü boyunca canlı tutulması gereken bir nesnenin işaretçisi. Böyle bir nesne yoksa NULL'u geçirin.

*bayraklar*<br/>
Yerumerator'un dizinin sahipliğini alıp almayacağını veya dizinin bir kopyasını yapıp yapmaması gerektiğini belirten bayraklar. Olası değerler aşağıda açıklanmıştır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca bir kez arayın - enumerator'u baş harfe çevirin, kullanın, sonra atın.

İşaretçileri başka bir nesnede tutulan bir dizideki öğelere geçirirseniz (ve tamumatörden verileri kopyalamasını istemezseniz), noterator'un ve tuttuğu dizinin, enumerator'un ihtiyacı olduğu sürece kullanılabilir olduğundan emin olmak için *pUnk* parametresini kullanabilirsiniz. Enumerator sadece canlı tutmak için nesne üzerinde bir COM referans tutar. Enumerator yok edildiğinde COM başvurusu otomatik olarak serbest bırakılır.

*Bayraklar* parametresi, yerumerator'un ona geçirilen dizi öğelerini nasıl ele alması gerektiğini belirtmenize olanak tanır. *bayraklar* aşağıda gösterilen numaralandırma `CComEnumFlags` değerlerinden birini alabilir:

```
enum CComEnumFlags
   {
   AtlFlagNoCopy = 0,
   AtlFlagTakeOwnership = 2, // BitOwn
   AtlFlagCopy = 3           // BitOwn | BitCopy
   };
```

`AtlFlagNoCopy`dizinin ömrünün tümeratör tarafından kontrol edilemeyeceğini ifade eder. Bu durumda, dizi statik olacak veya *pUnk* tarafından tanımlanan nesne artık gerekli olmadığında dizi serbest sorumlu olacaktır.

`AtlFlagTakeOwnership`dizinin yok edilmesinin tümumeratör tarafından kontrol edilmesi anlamına gelir. Bu durumda, dizi dinamik olarak **yeni**kullanılarak ayrılmış olmalıdır. Enumerator, yıkıcıdaki diziyi siler. Genellikle, *pUnk*için NULL geçer, ancak yine de geçerli bir işaretçi bazı nedenlerden dolayı enumerator imha haberdar edilmesi gerekiyorsa geçirebilirsiniz.

`AtlFlagCopy`'ye `Init`geçirilen dizi kopyalayarak yeni bir dizi oluşturulacak anlamına gelir. Yeni dizinin ömrü, tümumeratör tarafından kontrol edilecek. Enumerator, yıkıcıdaki diziyi siler. Genellikle, *pUnk*için NULL geçer, ancak yine de geçerli bir işaretçi bazı nedenlerden dolayı enumerator imha haberdar edilmesi gerekiyorsa geçirebilirsiniz.

> [!NOTE]
> Bu yöntemin prototipi, dizi öğelerini sınıfa şablon parametresi olarak tanımlanan tür `T`, `T` tür olarak belirtir. Bu COM arabirim yöntemi [CComEnumImpl](#next)ile maruz aynı türüdür::Sonraki . Bunun anlamı, [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)aksine, bu sınıf farklı depolama ve maruz veri türleri desteklemez olmasıdır. Dizideki öğelerin veri türü, COM arabirimi ile açığa çıkan veri türüyle aynı olmalıdır.

## <a name="ccomenumimplclone"></a><a name="clone"></a>CComEnumImpl::Klon

Bu yöntem, bir **Clone** tür `CComEnum`nesne oluşturarak Klon yönteminin uygulanmasını sağlar, aynı dizi ve geçerli nesne tarafından kullanılan yineleyici ile başlatılması ve yeni oluşturulan nesne üzerinde arabirimi döndürerek.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>Parametreler

*ppEnum*<br/>
[çıkış] Yeni oluşturulan bir nesnenin enumeratör arabirimi, geçerli sayısallaştırıcıdan klonlandı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Klonlanmış tümumeratörlerin orijinal enumerator tarafından kullanılan verilerin kendi kopyalarını (veya sahipliklerini) asla oluşturmadığını unutmayın. Gerekirse, klonlanmış tümumeratörler orijinal sayısallaştırıcıyı (COM referansı kullanarak) canlı tutar ve verilerin ihtiyaç duydukları sürece kullanılabilir olmasını sağlar.

## <a name="ccomenumimplm_spunk"></a><a name="m_spunk"></a>CComEnumImpl::m_spUnk

Bu akıllı işaretçi [CComEnumImpl](#init)geçirilen nesne üzerinde bir referans tutar::Init , bu kişinin ömrü boyunca canlı kalmasını sağlamak.

```
CComPtr<IUnknown> m_spUnk;
```

## <a name="ccomenumimplm_begin"></a><a name="m_begin"></a>CComEnumImpl::m_begin

Numaralandırılacak öğeleri içeren dizinin son öğesinin hemen ötesinde ki konuma işaretçi.

```
T* m_begin;
```

## <a name="ccomenumimplm_end"></a><a name="m_end"></a>CComEnumImpl::m_end

Numaralandırılacak öğeleri içeren dizinin ilk öğesine işaretçi.

```
T* m_end;
```

## <a name="ccomenumimplm_iter"></a><a name="m_iter"></a>CComEnumImpl::m_iter

Numaralandırılacak öğeleri içeren dizinin geçerli öğesine işaretçi.

```
T* m_iter;
```

## <a name="ccomenumimplm_dwflags"></a><a name="m_dwflags"></a>CComEnumImpl::m_dwFlags

Bayraklar [CComEnumImpl geçti::Init](#init).

```
DWORD m_dwFlags;
```

## <a name="ccomenumimplnext"></a><a name="next"></a>CComEnumImpl::Sonraki

Bu yöntem **Sonraki** yöntemin uygulanmasını sağlar.

```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```

### <a name="parameters"></a>Parametreler

*Celt*<br/>
[içinde] İstenen öğe sayısı.

*Rgelt*<br/>
[çıkış] Öğelerle doldurulacak dizi.

*pceltFetched*<br/>
[çıkış] *Rgelt'te*döndürülen öğelerin sayısı. Listede *keltten* daha az eleman kalmışsa, bu *keltten* daha az olabilir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ccomenumimplreset"></a><a name="reset"></a>CComEnumImpl::Sıfırlama

Bu **yöntem, Sıfırlama** yönteminin uygulanmasını sağlar.

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="ccomenumimplskip"></a><a name="skip"></a>CComEnumImpl::Atla

Bu **yöntem, Atlama** yönteminin uygulanmasını sağlar.

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>Parametreler

*Celt*<br/>
[içinde] Atlasılayacak öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

*Kelt* sıfır ise E_INVALIDARG döndürür, *keltten* daha az eleman döndürülürse S_FALSE döndürür, aksi S_OK döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[IEnumOnSTLImpl Sınıfı](../../atl/reference/ienumonstlimpl-class.md)<br/>
[CComEnum Sınıfı](../../atl/reference/ccomenum-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
