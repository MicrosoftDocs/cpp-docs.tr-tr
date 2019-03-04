---
title: CAutoPtr sınıfı
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
ms.openlocfilehash: 7f4f446aa97f2bf3843b830bd7fb4c4a5d74ffdb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259795"
---
# <a name="cautoptr-class"></a>CAutoPtr sınıfı

Bu sınıf, bir akıllı işaretçi nesnesinin temsil eder.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

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

|Ad|Açıklama|
|----------|-----------------|
|[CAutoPtr::CAutoPtr](#cautoptr)|Oluşturucu.|
|[CAutoPtr:: ~ CAutoPtr](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAutoPtr::Attach](#attach)|Var olan bir işaretçi sahipliğini almak için bu yöntemi çağırın.|
|[CAutoPtr::Detach](#detach)|Bir işaretçi sahipliğini bırakmak için bu yöntemi çağırın.|
|[CAutoPtr::Free](#free)|İşaret ettiği nesnenin silmek için bu yöntemi çağıran bir `CAutoPtr`.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAutoPtr::operator T *](#operator_t_star)|Atama işleci.|
|[CAutoPtr::operator =](#operator_eq)|Atama işleci.|
|[CAutoPtr::operator ->](#operator_ptr)|İşaretçi-üye işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAutoPtr::m_p](#m_p)|İşaretçi veri üye değişkeni.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, oluşturmak ve kapsam dışına düştüğünde otomatik olarak kaynakları boşaltma tarafından bellek sızıntılarını karşı korunmasına yardımcı olacak akıllı bir işaretçi yönetmek için yöntemler sağlar.

Ayrıca `CAutoPtr`kopya oluşturucu ve atama işleci aktarımı sahipliği işaretçisinin hedef işaretçisi kaynak işaretçi kopyalama ve kaynak işaretçiyi NULL olarak ayarlamak. Bu nedenle iki tane mümkün değildir `CAutoPtr` her aynı işaretçi depolama nesneleri ve bu aynı işaretçi iki kez silme olasılığını azaltır.

`CAutoPtr` Ayrıca koleksiyonları işaretçilerinin oluşturulmasını basitleştirir. Koleksiyon sınıfı türetme ve geçersiz kılma yıkıcısında yerine koleksiyonunu yapmak daha kolaydır `CAutoPtr` nesneleri. Koleksiyon silindiğinde, `CAutoPtr` nesne kapsam dışına çıkmaz ve otomatik olarak kendilerini Sil.

[CHeapPtr](../../atl/reference/cheapptr-class.md) ve çeşitleri iş aynı şekilde `CAutoPtr`, ayırma ve serbest C++ yerine farklı bir yığın işlevleri kullanarak bellek **yeni** ve **Sil** işleçleri. [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) benzer `CAutoPtr`, bunu kullanan tek fark **vektör new []** ve **vektör delete []** ayırmak ve belleği boşaltmak için.

Ayrıca bkz: [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) ve [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) zaman diziler veya akıllı işaretçiler listesi gereklidir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#74](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]

##  <a name="attach"></a>  CAutoPtr::Attach

Var olan bir işaretçi sahipliğini almak için bu yöntemi çağırın.

```
void Attach(T* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
`CAutoPtr` Nesne, işaretçi sahipliğini alır.

### <a name="remarks"></a>Açıklamalar

Olduğunda bir `CAutoPtr` nesne, işaretçi sahipliğini alır, kapsam dışına çıktığında bunu otomatik olarak işaretçi ve ayrılan tüm verileri siler. Varsa [CAutoPtr::Detach](#detach) olan çağrılır, programcı yeniden herhangi boşaltma sorumluluğunu verilen kaynakları tahsis edilir.

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir [CAutoPtr::m_p](#m_p) veri üyesi için bir varolan değeri şu anda işaret eder; diğer bir deyişle, NULL değerine eşit değil.

### <a name="example"></a>Örnek

Örnekte bakın [CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md).

##  <a name="cautoptr"></a>  CAutoPtr::CAutoPtr

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

*p*<br/>
Var olan bir işaretçi.

*TSrc*<br/>
Bir başkası tarafından yönetilen türü `CAutoPtr`geçerli nesneyi başlatmak için kullanılır.

### <a name="remarks"></a>Açıklamalar

`CAutoPtr` Nesne var olan bir işaretçi kullanarak oluşturulabilir, bu durumda işaretçi sahipliğini aktarır.

### <a name="example"></a>Örnek

Örnekte bakın [CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md).

##  <a name="dtor"></a>  CAutoPtr:: ~ CAutoPtr

Yıkıcı.

```
~CAutoPtr() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır. Çağrıları [CAutoPtr::Free](#free).

##  <a name="detach"></a>  CAutoPtr::Detach

Bir işaretçi sahipliğini bırakmak için bu yöntemi çağırın.

```
T* Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçiyi bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Bir işaretçi sahipliğini bırakır, ayarlar [CAutoPtr::m_p](#m_p) veri üyesi değişkeninin NULL ve işaretçi bir kopyasını döndürür. Arama sonra `Detach`, bunu herhangi boşaltmak için programcı kadar kaynakları ayrıldığı `CAutoPtr` nesnesi daha önce kabul reponsibility.

### <a name="example"></a>Örnek

Örnekte bakın [CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md).

##  <a name="free"></a>  CAutoPtr::Free

İşaret ettiği nesnenin silmek için bu yöntemi çağıran bir `CAutoPtr`.

```
void Free() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesne tarafından işaret edilen `CAutoPtr` serbest bırakılır ve [CAutoPtr::m_p](#m_p) veri üyesi değişkeni, NULL olarak ayarlanır.

##  <a name="m_p"></a>  CAutoPtr::m_p

İşaretçi veri üye değişkeni.

```
T* m_p;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişkeni, işaretçi bilgileri tutar.

##  <a name="operator_eq"></a>  CAutoPtr::operator =

Atama işleci.

```
template<>
CAutoPtr<T>& operator= (CAutoPtr<T>& p);

template<typename TSrc>
CAutoPtr<T>& operator= (CAutoPtr<TSrc>& p);
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Bir işaretçi.

*TSrc*<br/>
Sınıf türü.

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru döndürür bir **CAutoPtr\< T >**.

### <a name="remarks"></a>Açıklamalar

Atama işleci ayırır `CAutoPtr` herhangi bir geçerli işaretçi nesneden ve yeni bir işaretçi ekler *p*, onun yerine.

### <a name="example"></a>Örnek

Örnekte bakın [CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md).

##  <a name="operator_ptr"></a>  CAutoPtr::operator-&gt;

İşaretçi-üye işleci.

```
T* operator->() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Değerini döndürür [CAutoPtr::m_p](#m_p) veri üye değişkeni.

### <a name="remarks"></a>Açıklamalar

İşaret ettiği bir sınıftaki bir yöntemi çağırmak için bu işleci kullanın `CAutoPtr` nesne. Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir `CAutoPtr` işaret NULL.

### <a name="example"></a>Örnek

Örnekte bakın [CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md).

##  <a name="operator_t_star"></a>  CAutoPtr::operator T *

Atama işleci.

```
operator T* () const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Sınıf şablonunda tanımlanan nesne veri türü bir işaretçi döndürür.

### <a name="example"></a>Örnek

Örnekte bakın [CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[CHeapPtr Sınıfı](../../atl/reference/cheapptr-class.md)<br/>
[CAutoVectorPtr Sınıfı](../../atl/reference/cautovectorptr-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
