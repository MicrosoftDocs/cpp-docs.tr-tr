---
title: Ccomenumımpl sınıfı | Microsoft Docs
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
ms.openlocfilehash: 2cf80d51cdf45b6298255a252124ace9568953b1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082541"
---
# <a name="ccomenumimpl-class"></a>Ccomenumımpl sınıfı

Bu sınıf, numaralandırılan öğeleri bir dizi içinde depolandığı bir COM Numaralandırıcı arabirimi uygulamasını sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class Base,
    const IID* piid, class T, class Copy>
class ATL_NO_VTABLE CComEnumImpl : public Base
```

#### <a name="parameters"></a>Parametreler

*temel*<br/>
COM Numaralandırıcı arabirimi. Bkz: [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) örneği.

*piid*<br/>
Numaralandırıcı arabirimi arabirim kimliği için bir işaretçi.

*T*<br/>
Numaralandırıcı arabirim tarafından sunulan öğe türü.

*kopyalama*<br/>
Bir homojen [kopyalama İlkesi sınıfı](../../atl/atl-copy-policy-classes.md).

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComEnumImpl::CComEnumImpl](#ccomenumimpl)|Oluşturucu.|
|[Ccomenumımpl:: ~ Ccomenumımpl](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComEnumImpl::Clone](#clone)|Uygulamasını **kopya** numaralandırma arabirim yöntemi.|
|[CComEnumImpl::Init](#init)|Numaralandırıcı başlatır.|
|[CComEnumImpl::Next](#next)|Uygulamasını **sonraki**.|
|[CComEnumImpl::Reset](#reset)|Uygulamasını **sıfırlama**.|
|[CComEnumImpl::Skip](#skip)|Uygulamasını **atla**.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComEnumImpl::m_begin](#m_begin)|Dizideki ilk öğe işaretçisi.|
|[CComEnumImpl::m_dwFlags](#m_dwflags)|Kopyalama aracılığıyla geçirilen bayraklar `Init`.|
|[CComEnumImpl::m_end](#m_end)|Konumun dizi içindeki son öğenin hemen ötesinde bir işaretçi.|
|[CComEnumImpl::m_iter](#m_iter)|Dizideki geçerli öğeye bir işaretçi.|
|[CComEnumImpl::m_spUnk](#m_spunk)|`IUnknown` İşaretçi numaralandırılan koleksiyonu sağlayan nesne.|

## <a name="remarks"></a>Açıklamalar

Bkz: [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) yöntem uygulamaları ilişkin bir örnek. `CComEnumImpl` Numaralandırılan öğeleri bir dizi içinde depolandığı bir COM Numaralandırıcı arabirim uygulamasını sağlar. Bu sınıf için benzer `IEnumOnSTLImpl` Numaralandırıcı arabiriminin bir uygulamasını sağlar sınıfını, bir C++ Standart Kitaplığı kapsayıcı tabanlı.

> [!NOTE]
>  Daha fazla arasındaki farklar hakkında ayrıntılı bilgi için `CComEnumImpl` ve `IEnumOnSTLImpl`, bkz: [CComEnumImpl::Init](#init).

Genellikle, görüntüler *değil* kendi Numaralandırıcı sınıfı bu arabirimi uygulamasından türetilerek oluşturmanız gerekir. ATL tarafından sağlanan bir dizisine göre bir numaralandırıcı kullanmak istiyorsanız, bir örneğini oluşturmak için daha yaygın [CComEnum](../../atl/reference/ccomenum-class.md).

Ancak, özel bir numaralandırıcı (örneğin, bir numaralandırıcı arabirimi yanı sıra arabirimleri kullanıma açıp) sağlamak gerekiyorsa, bu sınıftan türetebilirsiniz. Bu durumda geçersiz kılma gerekecektir olma olasılığı yüksektir [CComEnumImpl::Clone](#clone) kendi uygulamasını sağlamak için yöntemi.

Daha fazla bilgi için [ATL koleksiyonları ve numaralandırıcıları](../../atl/atl-collections-and-enumerators.md).

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

##  <a name="dtor"></a>  Ccomenumımpl:: ~ Ccomenumımpl

Yıkıcı.

```
~CComEnumImpl();
```

##  <a name="init"></a>  CComEnumImpl::Init

Numaralandırıcı arabirimine tüm istemciler için bir işaretçi geçirmeden önce bu yöntemi çağırmanız gerekir.

```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```

### <a name="parameters"></a>Parametreler

*başlayın*<br/>
Numaralandırılacak öğeleri içeren dizinin ilk öğesinin işaretçisi.

*Son*<br/>
Konuma son sıralanması öğeleri içeren bir dizi öğesi için bir işaretçi.

*pUnk*<br/>
[in] `IUnknown` İşaretçiyi nesnenin Numaralandırıcı yaşam süresi boyunca canlı olarak tutulmalıdır. Böyle bir nesne varsa, NULL geçirin.

*bayrakları*<br/>
Numaralandırıcı bir kopyasını oluşturmak veya dizinin sahipliğini olup olmadığını belirten işaretleri. Olası değerler, aşağıda açıklanmıştır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca bir kez çağırmanız — Numaralandırıcı başlatmak, bunu kullanın ve ardından çöpe.

Başka bir nesnede yer alacak bir dizi öğelerinde işaretçileri geçirebilirsiniz (ve veri kopyalamak için bir numaralandırıcı sorma varsa), kullanabileceğiniz *pUnk* nesne ve onun tutan dizinin olduğu sürece Numaralandırıcı için kullanılabilir olmasını sağlamak için parametre bunları gerekir. Numaralandırıcı, yalnızca etkin kalması için nesne üzerinde bir COM başvurusu tutar. COM başvurusu, numaralandırıcı kaldırıldığında otomatik olarak yayımlanır.

*Bayrakları* parametresi Numaralandırıcı geçirilen dizi öğelerinin nasıl düşünmelisiniz belirtmenize olanak verir. *bayrakları* değerlerden birini alabilir `CComEnumFlags` sabit listesi aşağıda gösterilmektedir:

```
enum CComEnumFlags
   {
   AtlFlagNoCopy = 0,
   AtlFlagTakeOwnership = 2, // BitOwn
   AtlFlagCopy = 3           // BitOwn | BitCopy
   };
```

`AtlFlagNoCopy` dizinin ömrü numaralandırıcı tarafından denetlenmeyen anlamına gelir. Bu durumda, ya da dizi statik veya tarafından tanımlanan nesne olacak *pUnk* artık gerekli olmadığında, dizi boşaltma için sorumlu olursunuz.

`AtlFlagTakeOwnership` yok etme dizisi numaralandırıcı tarafından denetlenecek olduğu anlamına gelir. Bu durumda, dizi dinamik olarak kullanarak ayrılmış olmalıdır **yeni**. Numaralandırıcı, yok edici dizide siler. NULL genellikle geçecekse *pUnk*, ancak Numaralandırıcı yok etme herhangi bir nedenden dolayı bildirim almak gerekirse yine de geçerli bir işaretçi geçirebilirsiniz.

`AtlFlagCopy` Yeni bir dizi için geçirilen dizisi kopyalayarak oluşturulması anlamına gelir `Init`. Yeni dizinin ömrü numaralandırıcı tarafından kontrol etmektir. Numaralandırıcı, yok edici dizide siler. NULL genellikle geçecekse *pUnk*, ancak Numaralandırıcı yok etme herhangi bir nedenden dolayı bildirim almak gerekirse yine de geçerli bir işaretçi geçirebilirsiniz.

> [!NOTE]
>  Bu yöntem prototipi türü olacak şekilde dizi öğeleri belirtir `T`burada `T` sınıfı için şablon parametresi olarak tanımlanmıştır. COM arabirimi yoluyla metodunun aynı türü budur [CComEnumImpl::Next](#next). Bu olduğu çıkarımında, benzer nitelikte değildir [Ienumonstlımpl](../../atl/reference/ienumonstlimpl-class.md), bu sınıf kullanıma sunulan veri türleri ve farklı depolama desteklemez. Dizideki öğelerin veri türü, COM arabirimi yoluyla kullanıma sunulan veri türü ile aynı olmalıdır.

##  <a name="clone"></a>  CComEnumImpl::Clone

Bu yöntem uygulamasını sağlar **kopya** türünde bir nesne oluşturarak yöntemi `CComEnum`, aynı dizi ve geçerli nesne tarafından kullanılan yineleyici başlatma ve yeni oluşturulan üzerinde arabirimi döndüren nesne.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>Parametreler

*ppEnum*<br/>
[out] Yeni oluşturulan bir nesneye Numaralandırıcı arabirimde geçerli Numaralandırıcının kopyalandı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Kopyalanan numaralandırıcılar hiç kendi yaptığınız Not özgün numaralandırıcı tarafından kullanılan veri kopyalama (veya sahipliği). Gerekirse, kopyalanan numaralandırıcılar özgün Numaralandırıcı Canlı (bir COM başvurusu kullanarak) ihtiyaç duydukları sürece verileri için kullanılabilir olduğundan emin olmak için tutar.

##  <a name="m_spunk"></a>  CComEnumImpl::m_spUnk

Bu akıllı işaretçi geçirilen nesne üzerinde bir başvuru tutan [CComEnumImpl::Init](#init), bu Numaralandırıcının yaşam süresi boyunca Canlı çalışmayı sürdürdüğünden emin olma.

```
CComPtr<IUnknown> m_spUnk;
```

##  <a name="m_begin"></a>  CComEnumImpl::m_begin

Konuma son sıralanması öğeleri içeren bir dizi öğesi için bir işaretçi.

```
T* m_begin;
```

##  <a name="m_end"></a>  CComEnumImpl::m_end

Numaralandırılacak öğeleri içeren dizinin ilk öğesinin işaretçisi.

```
T* m_end;
```

##  <a name="m_iter"></a>  CComEnumImpl::m_iter

Geçerli sıralanması öğeleri içeren bir dizi öğesinin işaretçisi.

```
T* m_iter;
```

##  <a name="m_dwflags"></a>  CComEnumImpl::m_dwFlags

Geçirilen bayraklar [CComEnumImpl::Init](#init).

```
DWORD m_dwFlags;
```

##  <a name="next"></a>  CComEnumImpl::Next

Bu yöntem uygulamasını sağlar **sonraki** yöntemi.

```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```

### <a name="parameters"></a>Parametreler

*celt*<br/>
[in] İstenen öğe sayısı.

*rgelt*<br/>
[out] Öğelerle doldurulması dizisi.

*pceltFetched*<br/>
[out] Gerçekte döndürülen öğe sayısını *rgelt*. Bu kısa *celt* az olursa *celt* öğeleri listede kaldı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="reset"></a>  CComEnumImpl::Reset

Bu yöntem uygulamasını sağlar **sıfırlama** yöntemi.

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="skip"></a>  CComEnumImpl::Skip

Bu yöntem uygulamasını sağlar **atla** yöntemi.

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>Parametreler

*celt*<br/>
[in] Geçilecek öğelerin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

E_INVALIDARG döndürür *celt* sıfırsa, küçüktür, S_FALSE döndürür *celt* öğeleri döndürülür, aksi S_OK döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[IEnumOnSTLImpl Sınıfı](../../atl/reference/ienumonstlimpl-class.md)<br/>
[CComEnum Sınıfı](../../atl/reference/ccomenum-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
