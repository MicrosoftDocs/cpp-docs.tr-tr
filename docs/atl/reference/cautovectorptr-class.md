---
title: CAutoVectorPtr Sınıfı
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
ms.openlocfilehash: fc4bd4ba7a2f41a25679f1da718671f525519708
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748223"
---
# <a name="cautovectorptr-class"></a>CAutoVectorPtr Sınıfı

Bu sınıf, yeni vektör ve silme işleçlerini kullanarak akıllı işaretçi nesnesini temsil eder.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

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

|Adı|Açıklama|
|----------|-----------------|
|[CAutoVectorPtr::CAutoVectorPtr](#cautovectorptr)|Oluşturucu.|
|[CAutoVectorPtr::~CAutoVectorPtr](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAutoVectorPtr::Ayırma](#allocate)|Tarafından işaret edilen nesne dizisitarafından gerekli olan belleği `CAutoVectorPtr`ayırmak için bu yöntemi arayın.|
|[CAutoVectorPtr::Ekle](#attach)|Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.|
|[CAutoVectorPtr::Detach](#detach)|Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.|
|[CAutoVectorPtr::Ücretsiz](#free)|Bir `CAutoVectorPtr`. tarafından işaret edilen bir nesneyi silmek için bu yöntemi arayın|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAutoVectorPtr::operatör T *](#operator_t__star)|Döküm operatörü.|
|[CAutoVectorPtr::operatör =](#operator_eq)|Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAutoVectorPtr::m_p](#m_p)|İşaretçi veri üye değişkeni.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, kapsam dışına çıktığında kaynakları otomatik olarak serbest kalarak bellek sızıntılarına karşı koruma sağlayan akıllı bir işaretçi oluşturmak ve yönetmek için yöntemler sağlar. `CAutoVectorPtr`c++ `CAutoPtr` **yeni** ve **silme** işleçleri yerine&#91;&#93;ayırmak ve ücretsiz leştirmek için vektör [yeni&#91;&#93;](../../standard-library/new-operators.md#op_new_arr) ve vektör [silme&#91;&#93;](../../standard-library/new-operators.md#op_delete_arr) `CAutoVectorPtr` kullanan tek farka benzer. Toplama sınıfları gerekiyorsa [CAutoVectorPtrElementTraits'a](../../atl/reference/cautovectorptrelementtraits-class.md) `CAutoVectorPtr` bakın.

Akıllı işaretçi sınıfı kullanma örneği için [CAutoPtr'a](../../atl/reference/cautoptr-class.md) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="cautovectorptrallocate"></a><a name="allocate"></a>CAutoVectorPtr::Ayırma

Tarafından işaret edilen nesne dizisitarafından gerekli olan belleği `CAutoVectorPtr`ayırmak için bu yöntemi arayın.

```
bool Allocate(size_t nElements) throw();
```

### <a name="parameters"></a>Parametreler

*nElements*<br/>
Dizideki öğelerin sayısı

### <a name="return-value"></a>Dönüş Değeri

Bellek başarıyla ayrılırsa doğru döndürür, hata yanlış.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, [CAutoVectorPtr::m_p](#m_p) üye değişken şu anda varolan bir değeri işaret ederse bir iddia hatası oluşur; diğer bir şey, NULL'a eşit değildir.

## <a name="cautovectorptrattach"></a><a name="attach"></a>CAutoVectorPtr::Ekle

Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.

```cpp
void Attach(T* p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Nesne `CAutoVectorPtr` bu işaretçinin sahipliğini alır.

### <a name="remarks"></a>Açıklamalar

Bir `CAutoVectorPtr` nesne bir işaretçinin sahipliğini aldığında, işaretçiyi ve ayrılan verileri kapsam dışına çıktığında otomatik olarak siler. [CAutoVectorPtr::Detach](#detach) çağrılırsa, programcıya ayrılan kaynakları serbest bırakma sorumluluğu tekrar verilir.

Hata ayıklama oluştururda, [CAutoVectorPtr::m_p](#m_p) üye değişken şu anda varolan bir değeri işaret ederse bir iddia hatası oluşur; diğer bir şey, NULL'a eşit değildir.

## <a name="cautovectorptrcautovectorptr"></a><a name="cautovectorptr"></a>CAutoVectorPtr::CAutoVectorPtr

Oluşturucu.

```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Varolan bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Nesne `CAutoVectorPtr` varolan bir işaretçi kullanılarak oluşturulabilir ve bu durumda işaretçinin sahipliğini aktarabilir.

## <a name="cautovectorptrcautovectorptr"></a><a name="dtor"></a>CAutoVectorPtr::~CAutoVectorPtr

Yıkıcı.

```
~CAutoVectorPtr() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan kaynakları serbest sağlar. [Aramalar CAutoVectorPtr::Ücretsiz](#free).

## <a name="cautovectorptrdetach"></a><a name="detach"></a>CAutoVectorPtr::Detach

Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.

```
T* Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçinin bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Bir işaretçinin sahipliğini serbest bırakır, [CAutoVectorPtr::m_p](#m_p) üye değişkenini NULL olarak ayarlar ve işaretçinin bir kopyasını döndürür. Aradıktan `Detach`sonra, nesnenin daha önce sorumluluk almış olabileceği `CAutoVectorPtr` ayrılmış kaynakları serbest bırakmanız programcıya kalmış olur.

## <a name="cautovectorptrfree"></a><a name="free"></a>CAutoVectorPtr::Ücretsiz

Bir `CAutoVectorPtr`. tarafından işaret edilen bir nesneyi silmek için bu yöntemi arayın

```cpp
void Free() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesne tarafından işaret `CAutoVectorPtr` serbest bırakılır ve [CAutoVectorPtr::m_p](#m_p) üye değişken NULL olarak ayarlanır.

## <a name="cautovectorptrm_p"></a><a name="m_p"></a>CAutoVectorPtr::m_p

İşaretçi veri üye değişkeni.

```
T* m_p;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişken işaretçi bilgilerini tutar.

## <a name="cautovectorptroperator-"></a><a name="operator_eq"></a>CAutoVectorPtr::operatör =

Atama işleci.

```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

**\< CAutoVectorPtr T >** başvuru verir.

### <a name="remarks"></a>Açıklamalar

Atama işleci nesneyi `CAutoVectorPtr` herhangi bir geçerli işaretçiden ayırır ve yerine yeni işaretçi *p,* ilyi bağlar.

## <a name="cautovectorptroperator-t-"></a><a name="operator_t__star"></a>CAutoVectorPtr::operatör T *

Döküm operatörü.

```
operator T*() const throw();
```

### <a name="remarks"></a>Açıklamalar

Sınıf şablonunda tanımlanan nesne veri türüne bir işaretçi döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CAutoPtr Sınıfı](../../atl/reference/cautoptr-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
