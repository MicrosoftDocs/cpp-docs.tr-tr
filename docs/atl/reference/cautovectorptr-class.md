---
title: CAutoVectorPtr sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::Allocate
- ATLBASE/ATL::CAutoVectorPtr::Attach
- ATLBASE/ATL::CAutoVectorPtr::Detach
- ATLBASE/ATL::CAutoVectorPtr::Free
- ATLBASE/ATL::CAutoVectorPtr::m_p
helpviewer_keywords:
- CAutoVectorPtr class
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
ms.openlocfilehash: 65d37396b02d2c11c758915b201eef09cf1935b5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226652"
---
# <a name="cautovectorptr-class"></a>CAutoVectorPtr sınıfı

Bu sınıf, vector New ve DELETE işleçlerini kullanarak bir akıllı işaretçi nesnesini temsil eder.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Söz dizimi

```
template<typename T>
class CAutoVectorPtr
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
İşaretçi türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAutoVectorPtr:: CAutoVectorPtr](#cautovectorptr)|Oluşturucu.|
|[CAutoVectorPtr:: ~ CAutoVectorPtr](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAutoVectorPtr:: allocate](#allocate)|Tarafından işaret edilen nesneler dizisinin gerektirdiği belleği ayırmak için bu yöntemi çağırın `CAutoVectorPtr` .|
|[CAutoVectorPtr:: Attach](#attach)|Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.|
|[CAutoVectorPtr::D etach](#detach)|Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.|
|[CAutoVectorPtr:: ücretsiz](#free)|Tarafından işaret edilen bir nesneyi silmek için bu yöntemi çağırın `CAutoVectorPtr` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAutoVectorPtr:: operator T *](#operator_t__star)|Atama işleci.|
|[CAutoVectorPtr:: operator =](#operator_eq)|Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAutoVectorPtr:: m_p](#m_p)|İşaretçi verisi üye değişkeni.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, kapsam dışı kaldığında kaynakları otomatik olarak boşaltarak bellek sızıntılarına karşı korumaya yardımcı olacak akıllı bir işaretçi oluşturmak ve yönetmek için yöntemler sağlar. `CAutoVectorPtr``CAutoPtr`, `CAutoVectorPtr` C++ ve işleçleri yerine bellek ayırmak ve serbest bırakmak için [vektör yeni&#91;&#93;](../../standard-library/new-operators.md#op_new_arr) ve [vektör silme&#91;&#93;](../../standard-library/new-operators.md#op_delete_arr) kullanan tek fark öğesine benzerdir **`new`** **`delete`** . Koleksiyon sınıfları gerekliyse, bkz. [Cautovectorptrelementnitelikler](../../atl/reference/cautovectorptrelementtraits-class.md) `CAutoVectorPtr` .

Akıllı işaretçi sınıfı kullanmayla ilgili bir örnek için bkz. [CAutoPtr](../../atl/reference/cautoptr-class.md) .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="cautovectorptrallocate"></a><a name="allocate"></a>CAutoVectorPtr:: allocate

Tarafından işaret edilen nesneler dizisinin gerektirdiği belleği ayırmak için bu yöntemi çağırın `CAutoVectorPtr` .

```
bool Allocate(size_t nElements) throw();
```

### <a name="parameters"></a>Parametreler

*nElements*<br/>
Dizideki öğelerin sayısı

### <a name="return-value"></a>Dönüş Değeri

Bellek başarıyla ayrılmışsa true, hatada false döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, [CAutoVectorPtr:: m_p](#m_p) üye değişkeni şu anda mevcut bir değere işaret ediyorsa bir onaylama hatası meydana gelir; diğer bir deyişle, NULL değerine eşit değildir.

## <a name="cautovectorptrattach"></a><a name="attach"></a>CAutoVectorPtr:: Attach

Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.

```cpp
void Attach(T* p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
`CAutoVectorPtr`Nesne Bu işaretçinin sahipliğini alır.

### <a name="remarks"></a>Açıklamalar

Bir `CAutoVectorPtr` nesne bir işaretçinin sahipliğini aldığında, bu işlem, kapsam dışına geçtiğinde işaretçiyi ve ayrılan verileri otomatik olarak siler. [CAutoVectorPtr::D etach](#detach) çağrıldığında, programcının, ayrılan kaynakları boşaltma sorumluluğunu yeniden kabul etmesi sağlanır.

Hata ayıklama yapılarında, [CAutoVectorPtr:: m_p](#m_p) üye değişkeni şu anda mevcut bir değere işaret ediyorsa bir onaylama hatası meydana gelir; diğer bir deyişle, NULL değerine eşit değildir.

## <a name="cautovectorptrcautovectorptr"></a><a name="cautovectorptr"></a>CAutoVectorPtr:: CAutoVectorPtr

Oluşturucu.

```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Var olan bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`CAutoVectorPtr`Nesnesi var olan bir işaretçi kullanılarak oluşturulabilir ve bu durumda işaretçinin sahipliğini aktarır.

## <a name="cautovectorptrcautovectorptr"></a><a name="dtor"></a>CAutoVectorPtr:: ~ CAutoVectorPtr

Yok edicisi.

```
~CAutoVectorPtr() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan kaynakları serbest bırakır. [CAutoVectorPtr:: Free](#free)çağırır.

## <a name="cautovectorptrdetach"></a><a name="detach"></a>CAutoVectorPtr::D etach

Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.

```
T* Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçinin bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Bir işaretçinin sahipliğini serbest bırakır, [CAutoVectorPtr:: m_p](#m_p) üye değişkenini null olarak ayarlar ve işaretçinin bir kopyasını döndürür. Çağrıldıktan sonra `Detach` , `CAutoVectorPtr` nesnenin daha önce sorumluluğa sahip olabileceği ayrılmış kaynakların serbest olması için programcıya sahipsiniz.

## <a name="cautovectorptrfree"></a><a name="free"></a>CAutoVectorPtr:: ücretsiz

Tarafından işaret edilen bir nesneyi silmek için bu yöntemi çağırın `CAutoVectorPtr` .

```cpp
void Free() throw();
```

### <a name="remarks"></a>Açıklamalar

Tarafından işaret edilen nesne `CAutoVectorPtr` serbest bırakılır ve [CAutoVectorPtr:: m_p](#m_p) üye değişkeni null olarak ayarlanır.

## <a name="cautovectorptrm_p"></a><a name="m_p"></a>CAutoVectorPtr:: m_p

İşaretçi verisi üye değişkeni.

```
T* m_p;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişkeni işaretçi bilgisini tutar.

## <a name="cautovectorptroperator-"></a><a name="operator_eq"></a>CAutoVectorPtr:: operator =

Atama işleci.

```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bir **CAutoVectorPtr \< T > **öğesine bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Atama işleci, `CAutoVectorPtr` nesneyi herhangi bir geçerli işaretçiden ayırır ve yeni işaretçiyi o yere ekler. *p*

## <a name="cautovectorptroperator-t-"></a><a name="operator_t__star"></a>CAutoVectorPtr:: operator T *

Atama işleci.

```
operator T*() const throw();
```

### <a name="remarks"></a>Açıklamalar

Sınıf şablonunda tanımlanan nesne veri türüne bir işaretçi döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CAutoPtr sınıfı](../../atl/reference/cautoptr-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
