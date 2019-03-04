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
ms.openlocfilehash: f614318125f3c6bce4003fee5fb4a945c7c88129
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259561"
---
# <a name="cautovectorptr-class"></a>CAutoVectorPtr sınıfı

Bu sınıf, vektör kullanarak yeni bir akıllı işaretçi nesnesinin temsil eder ve delete işleçleri.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

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
|[CAutoVectorPtr::CAutoVectorPtr](#cautovectorptr)|Oluşturucu.|
|[CAutoVectorPtr:: ~ CAutoVectorPtr](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAutoVectorPtr::Allocate](#allocate)|İşaret ettiği nesneler dizisi için gerekli bellek ayırmak için bu yöntemi çağırın `CAutoVectorPtr`.|
|[CAutoVectorPtr::Attach](#attach)|Var olan bir işaretçi sahipliğini almak için bu yöntemi çağırın.|
|[CAutoVectorPtr::Detach](#detach)|Bir işaretçi sahipliğini bırakmak için bu yöntemi çağırın.|
|[CAutoVectorPtr::Free](#free)|İşaret ettiği nesnenin silmek için bu yöntemi çağıran bir `CAutoVectorPtr`.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAutoVectorPtr::operator T *](#operator_t__star)|Atama işleci.|
|[CAutoVectorPtr::operator =](#operator_eq)|Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAutoVectorPtr::m_p](#m_p)|İşaretçi veri üye değişkeni.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, oluşturmak ve kapsam dışına düştüğünde otomatik olarak kaynakları boşaltma tarafından bellek sızıntılarını karşı korunmasına yardımcı olacak akıllı bir işaretçi yönetmek için yöntemler sağlar. `CAutoVectorPtr` benzer `CAutoPtr`, tek fark, olan `CAutoVectorPtr` kullanan [yeni vektör&#91; &#93; ](../../standard-library/new-operators.md#op_new_arr) ve [vektör silme&#91; &#93; ](../../standard-library/new-operators.md#op_delete_arr) ayırmak ve belleği boşaltmak için C++ yerine **yeni** ve **Sil** işleçleri. Bkz: [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) , koleksiyon sınıfları `CAutoVectorPtr` gereklidir.

Bkz: [CAutoPtr](../../atl/reference/cautoptr-class.md) akıllı işaretçi sınıfının kullanma örneği için.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="allocate"></a>  CAutoVectorPtr::Allocate

İşaret ettiği nesneler dizisi için gerekli bellek ayırmak için bu yöntemi çağırın `CAutoVectorPtr`.

```
bool Allocate(size_t nElements) throw();
```

### <a name="parameters"></a>Parametreler

*nElements*<br/>
Dizideki öğelerin sayısı

### <a name="return-value"></a>Dönüş Değeri

Ayrılan bellek başarıyla ise true değeri döndürür, başarısız olduğunda false.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir [CAutoVectorPtr::m_p](#m_p) üye değişkeni şu anda var olan bir değere işaret eder; diğer bir deyişle, NULL değerine eşit değil.

##  <a name="attach"></a>  CAutoVectorPtr::Attach

Var olan bir işaretçi sahipliğini almak için bu yöntemi çağırın.

```
void Attach(T* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
`CAutoVectorPtr` Nesne, işaretçi sahipliğini alır.

### <a name="remarks"></a>Açıklamalar

Olduğunda bir `CAutoVectorPtr` nesne, işaretçi sahipliğini alır, kapsam dışına çıktığında bunu otomatik olarak işaretçi ve ayrılan tüm verileri siler. Varsa [CAutoVectorPtr::Detach](#detach) olan çağrılır, programcı yeniden herhangi boşaltma sorumluluğunu verilen kaynakları tahsis edilir.

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir [CAutoVectorPtr::m_p](#m_p) üye değişkeni şu anda var olan bir değere işaret eder; diğer bir deyişle, NULL değerine eşit değil.

##  <a name="cautovectorptr"></a>  CAutoVectorPtr::CAutoVectorPtr

Oluşturucu.

```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Var olan bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`CAutoVectorPtr` Nesne var olan bir işaretçi kullanarak oluşturulabilir, bu durumda işaretçi sahipliğini aktarır.

##  <a name="dtor"></a>  CAutoVectorPtr:: ~ CAutoVectorPtr

Yıkıcı.

```
~CAutoVectorPtr() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır. Çağrıları [CAutoVectorPtr::Free](#free).

##  <a name="detach"></a>  CAutoVectorPtr::Detach

Bir işaretçi sahipliğini bırakmak için bu yöntemi çağırın.

```
T* Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçiyi bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Bir işaretçi sahipliğini bırakır, ayarlar [CAutoVectorPtr::m_p](#m_p) üye değişkeni null ve işaretçi bir kopyasını döndürür. Arama sonra `Detach`, bunu herhangi boşaltmak için programcı kadar kaynakları ayrıldığı `CAutoVectorPtr` nesnesi daha önce kabul sorumluluk.

##  <a name="free"></a>  CAutoVectorPtr::Free

İşaret ettiği nesnenin silmek için bu yöntemi çağıran bir `CAutoVectorPtr`.

```
void Free() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesne tarafından işaret edilen `CAutoVectorPtr` serbest bırakılır ve [CAutoVectorPtr::m_p](#m_p) üye değişkeni, NULL olarak ayarlanır.

##  <a name="m_p"></a>  CAutoVectorPtr::m_p

İşaretçi veri üye değişkeni.

```
T* m_p;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişkeni, işaretçi bilgileri tutar.

##  <a name="operator_eq"></a>  CAutoVectorPtr::operator =

Atama işleci.

```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru döndürür bir **CAutoVectorPtr\< T >**.

### <a name="remarks"></a>Açıklamalar

Atama işleci ayırır `CAutoVectorPtr` herhangi bir geçerli işaretçi nesneden ve yeni bir işaretçi ekler *p*, onun yerine.

##  <a name="operator_t__star"></a>  CAutoVectorPtr::operator T *

Atama işleci.

```
operator T*() const throw();
```

### <a name="remarks"></a>Açıklamalar

Sınıf şablonunda tanımlanan nesne veri türü bir işaretçi döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CAutoPtr Sınıfı](../../atl/reference/cautoptr-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
