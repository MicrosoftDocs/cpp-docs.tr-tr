---
title: CAutoPtr Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAutoPtr
- ATLBASE/ATL::CAutoPtr
- ATLBASE/ATL::CAutoPtr::CAutoPtr
- ATLBASE/ATL::CAutoPtr::Attach
- ATLBASE/ATL::CAutoPtr::Detach
- ATLBASE/ATL::CAutoPtr::Free
- ATLBASE/ATL::CAutoPtr::m_p
helpviewer_keywords:
- CAutoPtr class
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
ms.openlocfilehash: 2fa6eb26c2e2cd569d74c02d8303768b1aeb4f1c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748266"
---
# <a name="cautoptr-class"></a>CAutoPtr Sınıfı

Bu sınıf akıllı işaretçi nesnesini temsil eder.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class CAutoPtr
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
İşaretçi türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAutoPtr::CAutoPtr](#cautoptr)|Oluşturucu.|
|[CAutoPtr::~CAutoPtr](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAutoPtr::Ekle](#attach)|Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.|
|[CAutoPtr::Detach](#detach)|Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.|
|[CAutoPtr::Ücretsiz](#free)|Bir `CAutoPtr`. tarafından işaret edilen bir nesneyi silmek için bu yöntemi arayın|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAutoPtr::operatör T*](#operator_t_star)|Döküm operatörü.|
|[CAutoPtr::operatör =](#operator_eq)|Atama işleci.|
|[CAutoPtr::operatör ->](#operator_ptr)|İşaretçiden üyeye işleç.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAutoPtr::m_p](#m_p)|İşaretçi veri üye değişkeni.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, kapsam dışına çıktığında kaynakları otomatik olarak serbest kalarak bellek sızıntılarına karşı koruma sağlayan akıllı bir işaretçi oluşturmak ve yönetmek için yöntemler sağlar.

Ayrıca, `CAutoPtr`'kopya oluşturucu ve atama işleci işaretçinin sahipliğini aktararak, kaynak işaretçisini hedef işaretçiye kopyalar ve kaynak işaretçiyi NULL'a ayarlar. Bu nedenle, her `CAutoPtr` biri aynı işaretçiyi depolayan iki nesneye sahip olmak mümkün değildir ve bu da aynı işaretçiyi iki kez silme olasılığını azaltır.

`CAutoPtr`ayrıca işaretçilerin koleksiyonlarının oluşturulmasını da kolaylaştırır. Bir toplama sınıfı türetmek ve yıkıcıyı geçersiz kılmak yerine, nesnelerden `CAutoPtr` oluşan bir koleksiyon yapmak daha kolaydır. Koleksiyon silindiğinde, `CAutoPtr` nesneler kapsam dışına çıkar ve kendilerini otomatik olarak siler.

[CHeapPtr](../../atl/reference/cheapptr-class.md) ve `CAutoPtr`varyantları, C++ **yeni** ve **silme** işleçleri yerine farklı yığın işlevleri kullanarak farklı bellek ayırmaları ve özgür olmaları dışında aynı şekilde çalışır. [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) benzer `CAutoPtr`, tek fark, ayırmak ve ücretsiz bellek **için vektör yeni[]** ve vektör **silme[]** kullanıyor olması.

[Ayrıca](../../atl/reference/cautoptrarray-class.md) bkz. [CAutoPtrList](../../atl/reference/cautoptrlist-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#74](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]

## <a name="cautoptrattach"></a><a name="attach"></a>CAutoPtr::Ekle

Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.

```cpp
void Attach(T* p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Nesne `CAutoPtr` bu işaretçinin sahipliğini alır.

### <a name="remarks"></a>Açıklamalar

Bir `CAutoPtr` nesne bir işaretçinin sahipliğini aldığında, işaretçiyi ve ayrılan verileri kapsam dışına çıktığında otomatik olarak siler. [CAutoPtr::Detach](#detach) çağrılırsa, programcıya ayrılan kaynakları serbest bırakma sorumluluğu tekrar verilir.

Hata ayıklama oluştururda, [CAutoPtr::m_p](#m_p) veri üyesi şu anda varolan bir değeri işaret ederse bir iddia hatası oluşur; diğer bir şey, NULL'a eşit değildir.

### <a name="example"></a>Örnek

[CAutoPtr Genel Bakış'taki](../../atl/reference/cautoptr-class.md)örneğe bakın.

## <a name="cautoptrcautoptr"></a><a name="cautoptr"></a>CAutoPtr::CAutoPtr

Oluşturucu.

```
CAutoPtr() throw();
explicit CAutoPtr(T* p) throw();

template<typename TSrc>
CAutoPtr(CAutoPtr<TSrc>& p) throw();

template<>
CAutoPtr(CAutoPtr<T>& p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Varolan bir işaretçi.

*TSrc*<br/>
Geçerli nesneyi başlatmak için kullanılan başka bir `CAutoPtr`tür.

### <a name="remarks"></a>Açıklamalar

Nesne `CAutoPtr` varolan bir işaretçi kullanılarak oluşturulabilir ve bu durumda işaretçinin sahipliğini aktarabilir.

### <a name="example"></a>Örnek

[CAutoPtr Genel Bakış'taki](../../atl/reference/cautoptr-class.md)örneğe bakın.

## <a name="cautoptrcautoptr"></a><a name="dtor"></a>CAutoPtr::~CAutoPtr

Yıkıcı.

```
~CAutoPtr() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan kaynakları serbest sağlar. [Aramalar CAutoPtr::Ücretsiz](#free).

## <a name="cautoptrdetach"></a><a name="detach"></a>CAutoPtr::Detach

Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.

```
T* Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçinin bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Bir işaretçinin sahipliğini serbest bırakır, [CAutoPtr::m_p](#m_p) veri üye değişkenini NULL olarak ayarlar ve işaretçinin bir kopyasını döndürür. Aramadan `Detach`sonra, `CAutoPtr` nesnenin daha önce reponsibility kabul etmiş olabileceği ayrılan kaynakları serbest bırakmaprogramcıya kalmış.

### <a name="example"></a>Örnek

[CAutoPtr Genel Bakış'taki](../../atl/reference/cautoptr-class.md)örneğe bakın.

## <a name="cautoptrfree"></a><a name="free"></a>CAutoPtr::Ücretsiz

Bir `CAutoPtr`. tarafından işaret edilen bir nesneyi silmek için bu yöntemi arayın

```cpp
void Free() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesne tarafından işaret `CAutoPtr` serbest bırakılır ve [CAutoPtr::m_p](#m_p) veri üyesi değişken NULL olarak ayarlanır.

## <a name="cautoptrm_p"></a><a name="m_p"></a>CAutoPtr::m_p

İşaretçi veri üye değişkeni.

```
T* m_p;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişken işaretçi bilgilerini tutar.

## <a name="cautoptroperator-"></a><a name="operator_eq"></a>CAutoPtr::operatör =

Atama işleci.

```
template<>
CAutoPtr<T>& operator= (CAutoPtr<T>& p);

template<typename TSrc>
CAutoPtr<T>& operator= (CAutoPtr<TSrc>& p);
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Bir işaretçi.

*TSrc*<br/>
Bir sınıf türü.

### <a name="return-value"></a>Dönüş Değeri

**CAutoPtr\< T >** başvuru verir.

### <a name="remarks"></a>Açıklamalar

Atama işleci nesneyi `CAutoPtr` herhangi bir geçerli işaretçiden ayırır ve yerine yeni işaretçi *p,* ilyi bağlar.

### <a name="example"></a>Örnek

[CAutoPtr Genel Bakış'taki](../../atl/reference/cautoptr-class.md)örneğe bakın.

## <a name="cautoptroperator--gt"></a><a name="operator_ptr"></a>CAutoPtr::operatör -&gt;

İşaretçiden üyeye işleç.

```
T* operator->() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[CAutoPtr::m_p](#m_p) veri üyesi değişkeninin değerini verir.

### <a name="remarks"></a>Açıklamalar

`CAutoPtr` Nesne tarafından işaret edilen bir sınıftabir yöntem çağırmak için bu işleci kullanın. Hata ayıklama oluşturur, null `CAutoPtr` puan bir iddia hatası oluşur.

### <a name="example"></a>Örnek

[CAutoPtr Genel Bakış'taki](../../atl/reference/cautoptr-class.md)örneğe bakın.

## <a name="cautoptroperator-t"></a><a name="operator_t_star"></a>CAutoPtr::operatör T*

Döküm operatörü.

```
operator T* () const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Sınıf şablonunda tanımlanan nesne veri türüne bir işaretçi döndürür.

### <a name="example"></a>Örnek

[CAutoPtr Genel Bakış'taki](../../atl/reference/cautoptr-class.md)örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CHeapPtr Sınıfı](../../atl/reference/cheapptr-class.md)<br/>
[CAutoVectorPtr Sınıfı](../../atl/reference/cautovectorptr-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
