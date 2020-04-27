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
ms.openlocfilehash: 7f15e16b075b9a5327723a7f081100313f14ea77
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167727"
---
# <a name="cautoptr-class"></a>CAutoPtr Sınıfı

Bu sınıf, bir akıllı işaretçi nesnesini temsil eder.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
class CAutoPtr
```

### <a name="parameters"></a>Parametreler

*T*<br/>
İşaretçi türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAutoPtr:: CAutoPtr](#cautoptr)|Oluşturucu.|
|[CAutoPtr:: ~ CAutoPtr](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAutoPtr:: Attach](#attach)|Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.|
|[CAutoPtr::D etach](#detach)|Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.|
|[CAutoPtr:: ücretsiz](#free)|Tarafından işaret edilen bir nesneyi silmek için bu yöntemi çağırın `CAutoPtr`.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAutoPtr:: operator T *](#operator_t_star)|Atama işleci.|
|[CAutoPtr:: operator =](#operator_eq)|Atama işleci.|
|[CAutoPtr:: operator->](#operator_ptr)|Üye işaretçisi işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAutoPtr:: m_p](#m_p)|İşaretçi verisi üye değişkeni.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, kapsam dışı kaldığında kaynakları otomatik olarak boşaltarak bellek sızıntılarına karşı korumaya yardımcı olacak akıllı bir işaretçi oluşturmak ve yönetmek için yöntemler sağlar.

Daha ayrıntılı `CAutoPtr`olarak, işaretçinin kopyalama Oluşturucusu ve atama işleci, işaretçinin sahipliğini aktarma, kaynak işaretçiyi hedef işaretçiye kopyalama ve kaynak işaretçisini null olarak ayarlama. Bu nedenle, her biri aynı işaretçiyi `CAutoPtr` depolayan iki nesnenin olması olanaksız ve bu, aynı işaretçiyi iki kez silmenin olasılığını azaltır.

`CAutoPtr`Ayrıca işaretçiler koleksiyonunun oluşturulmasını basitleştirir. Bir koleksiyon sınıfı türetmek ve yıkıcıyı geçersiz kılmak yerine bir `CAutoPtr` nesne koleksiyonu oluşturmak daha basittir. Koleksiyon silindiğinde, `CAutoPtr` nesneler kapsam dışına geçer ve kendilerini otomatik olarak siler.

[CHeapPtr](../../atl/reference/cheapptr-class.md) ve varyantlar `CAutoPtr`, C++ **New** ve **Delete** işleçleri yerine farklı yığın işlevleri kullanarak bellek ayırıp serbest bırakmak dışında, ile aynı şekilde çalışır. [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) `CAutoPtr`, bellek ayırmak ve serbest bırakmak için **Vector New []** ve **Vector delete []** gibi tek farklılık ile benzerdir.

Ayrıca, diziler veya akıllı işaretçiler listesi gerektiğinde bkz. [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) ve [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#74](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]

## <a name="cautoptrattach"></a><a name="attach"></a>CAutoPtr:: Attach

Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.

```cpp
void Attach(T* p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
`CAutoPtr` Nesne Bu işaretçinin sahipliğini alır.

### <a name="remarks"></a>Açıklamalar

Bir `CAutoPtr` nesne bir işaretçinin sahipliğini aldığında, bu işlem, kapsam dışına geçtiğinde işaretçiyi ve ayrılan verileri otomatik olarak siler. [CAutoPtr::D etach](#detach) çağrılırsa, programcının ayrılan kaynakları boşaltma sorumluluğunu yeniden vermiş olur.

Hata ayıklama yapılarında, [CAutoPtr:: m_p](#m_p) veri üyesi şu anda mevcut bir değere işaret ediyorsa bir onaylama hatası meydana gelir; diğer bir deyişle, NULL değerine eşit değildir.

### <a name="example"></a>Örnek

[CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md)' daki örneğe bakın.

## <a name="cautoptrcautoptr"></a><a name="cautoptr"></a>CAutoPtr:: CAutoPtr

Oluşturucu.

```cpp
CAutoPtr() throw();
explicit CAutoPtr(T* p) throw();

template<typename TSrc>
CAutoPtr(CAutoPtr<TSrc>& p) throw();

template<>
CAutoPtr(CAutoPtr<T>& p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Var olan bir işaretçi.

*TSrc*<br/>
Başka bir `CAutoPtr`tarafından yönetilmekte olan tür, geçerli nesneyi başlatmak için kullanılır.

### <a name="remarks"></a>Açıklamalar

`CAutoPtr` Nesnesi var olan bir işaretçi kullanılarak oluşturulabilir ve bu durumda işaretçinin sahipliğini aktarır.

### <a name="example"></a>Örnek

[CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md)' daki örneğe bakın.

## <a name="cautoptrcautoptr"></a><a name="dtor"></a>CAutoPtr:: ~ CAutoPtr

Yok edicisi.

```cpp
~CAutoPtr() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan kaynakları serbest bırakır. [CAutoPtr:: Free](#free)çağırır.

## <a name="cautoptrdetach"></a><a name="detach"></a>CAutoPtr::D etach

Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.

```cpp
T* Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçinin bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Bir işaretçinin sahipliğini serbest bırakır, [CAutoPtr:: m_p](#m_p) veri ÜYESI değişkenini null olarak ayarlar ve işaretçinin bir kopyasını döndürür. Öğesini çağırdıktan `Detach`sonra, `CAutoPtr` nesnenin daha önce yanıtı kabul eden ayrılmış kaynakların serbest bırakılmasının için programcıya kalmıştır.

### <a name="example"></a>Örnek

[CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md)' daki örneğe bakın.

## <a name="cautoptrfree"></a><a name="free"></a>CAutoPtr:: ücretsiz

Tarafından işaret edilen bir nesneyi silmek için bu yöntemi çağırın `CAutoPtr`.

```cpp
void Free() throw();
```

### <a name="remarks"></a>Açıklamalar

Tarafından işaret edilen nesne serbest `CAutoPtr` bırakılır ve [cautoptr:: m_p](#m_p) veri üyesi değişkeni null olarak ayarlanır.

## <a name="cautoptrm_p"></a><a name="m_p"></a>CAutoPtr:: m_p

İşaretçi verisi üye değişkeni.

```cpp
T* m_p;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişkeni işaretçi bilgisini tutar.

## <a name="cautoptroperator-"></a><a name="operator_eq"></a>CAutoPtr:: operator =

Atama işleci.

```cpp
template<>
CAutoPtr<T>& operator= (CAutoPtr<T>& p);

template<typename TSrc>
CAutoPtr<T>& operator= (CAutoPtr<TSrc>& p);
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Bir işaretçi.

*TSrc*<br/>
Bir sınıf türü.

### <a name="return-value"></a>Dönüş Değeri

Bir **CAutoPtr\< T >** başvurusunu döndürür.

### <a name="remarks"></a>Açıklamalar

Atama `CAutoPtr` *işleci, nesneyi*herhangi bir geçerli işaretçiden ayırır ve yeni işaretçiyi o yere ekler.

### <a name="example"></a>Örnek

[CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md)' daki örneğe bakın.

## <a name="cautoptroperator--gt"></a><a name="operator_ptr"></a>CAutoPtr:: operator-&gt;

Üye işaretçisi işleci.

```cpp
T* operator->() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[CAutoPtr:: m_p](#m_p) veri üyesi değişkeninin değerini döndürür.

### <a name="remarks"></a>Açıklamalar

`CAutoPtr` Nesne tarafından işaret edilen bir sınıftaki yöntemi çağırmak için bu işleci kullanın. Hata ayıklama yapılarında, NULL değeri `CAutoPtr` işaret ediyorsa bir onaylama hatası meydana gelir.

### <a name="example"></a>Örnek

[CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md)' daki örneğe bakın.

## <a name="cautoptroperator-t"></a><a name="operator_t_star"></a>CAutoPtr:: operator T *

Atama işleci.

```cpp
operator T* () const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Sınıf şablonunda tanımlanan nesne veri türüne bir işaretçi döndürür.

### <a name="example"></a>Örnek

[CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md)' daki örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CHeapPtr Sınıfı](../../atl/reference/cheapptr-class.md)<br/>
[CAutoVectorPtr Sınıfı](../../atl/reference/cautovectorptr-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
