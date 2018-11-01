---
title: CHeapPtrBase sınıfı
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase::AllocateBytes
- ATLCORE/ATL::CHeapPtrBase::Attach
- ATLCORE/ATL::CHeapPtrBase::Detach
- ATLCORE/ATL::CHeapPtrBase::Free
- ATLCORE/ATL::CHeapPtrBase::ReallocateBytes
- ATLCORE/ATL::CHeapPtrBase::m_pData
helpviewer_keywords:
- CHeapPtrBase class
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
ms.openlocfilehash: f183bb21d6a23b4e8ac4284894cfa2fcc7bb1dfd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538167"
---
# <a name="cheapptrbase-class"></a>CHeapPtrBase sınıfı

Bu sınıfın birkaç akıllı yığın işaretçisi sınıfları temelini oluşturur.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T, class Allocator = CCRTAllocator>
class CHeapPtrBase
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Yığın üzerinde depolanan nesne türü.

*Ayırıcı*<br/>
Bellek ayırma kullanmak için sınıf. Varsayılan olarak, ayırmak ve belleği boşaltmak için CRT yordamlar kullanılır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHeapPtrBase:: ~ CHeapPtrBase](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHeapPtrBase::AllocateBytes](#allocatebytes)|Bellek ayırmak için bu yöntemi çağırın.|
|[CHeapPtrBase::Attach](#attach)|Var olan bir işaretçi sahipliğini almak için bu yöntemi çağırın.|
|[CHeapPtrBase::Detach](#detach)|Bir işaretçi sahipliğini bırakmak için bu yöntemi çağırın.|
|[CHeapPtrBase::Free](#free)|İşaret ettiği nesnenin silmek için bu yöntemi çağıran bir `CHeapPtrBase`.|
|[CHeapPtrBase::ReallocateBytes](#reallocatebytes)|Bellek yeniden ayırmak üzere bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CHeapPtrBase::operator T *](#operator_t_star)|Atama işleci.|
|[CHeapPtrBase::operator &](#operator_amp)|& İşleci.|
|[CHeapPtrBase::operator ->](#operator_ptr)|İşaretçi-üye işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CHeapPtrBase::m_pData](#m_pdata)|İşaretçi veri üye değişkeni.|

## <a name="remarks"></a>Açıklamalar

Bu sınıfın birkaç akıllı yığın işaretçisi sınıfları temelini oluşturur. Türetilen sınıflar için [CHeapPtr](../../atl/reference/cheapptr-class.md) ve [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), kendi oluşturucular ve işleçleri ekleyin. Bu sınıfların uygulama örnekleri için bkz.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcore.h

##  <a name="allocatebytes"></a>  CHeapPtrBase::AllocateBytes

Bellek ayırmak için bu yöntemi çağırın.

```
bool AllocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
Ayrılacak bellek bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Bellek başarıyla ise true değeri döndürür ayrılmış, yanlış Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir [CHeapPtrBase::m_pData](#m_pdata) üye değişkeni şu anda var olan bir değere işaret eder; diğer bir deyişle, NULL değerine eşit değil.

##  <a name="attach"></a>  CHeapPtrBase::Attach

Var olan bir işaretçi sahipliğini almak için bu yöntemi çağırın.

```
void Attach(T* pData) throw();
```

### <a name="parameters"></a>Parametreler

*pData*<br/>
`CHeapPtrBase` Nesne, işaretçi sahipliğini alır.

### <a name="remarks"></a>Açıklamalar

Olduğunda bir `CHeapPtrBase` nesne, işaretçi sahipliğini alır, kapsam dışına çıktığında bunu otomatik olarak işaretçi ve ayrılan tüm verileri siler.

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir [CHeapPtrBase::m_pData](#m_pdata) üye değişkeni şu anda var olan bir değere işaret eder; diğer bir deyişle, NULL değerine eşit değil.

##  <a name="dtor"></a>  CHeapPtrBase:: ~ CHeapPtrBase

Yıkıcı.

```
~CHeapPtrBase() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

##  <a name="detach"></a>  CHeapPtrBase::Detach

Bir işaretçi sahipliğini bırakmak için bu yöntemi çağırın.

```
T* Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçiyi bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Bir işaretçi sahipliğini bırakır, ayarlar [CHeapPtrBase::m_pData](#m_pdata) üye değişkeni null ve işaretçi bir kopyasını döndürür.

##  <a name="free"></a>  CHeapPtrBase::Free

İşaret ettiği nesnenin silmek için bu yöntemi çağıran bir `CHeapPtrBase`.

```
void Free() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesne tarafından işaret edilen `CHeapPtrBase` serbest bırakılır ve [CHeapPtrBase::m_pData](#m_pdata) üye değişkeni, NULL olarak ayarlanır.

##  <a name="m_pdata"></a>  CHeapPtrBase::m_pData

İşaretçi veri üye değişkeni.

```
T* m_pData;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişkeni, işaretçi bilgileri tutar.

##  <a name="operator_amp"></a>  CHeapPtrBase::operator &amp;

& İşleci.

```
T** operator&() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Tarafından işaret edilen nesnenin adresini döndürür `CHeapPtrBase` nesne.

##  <a name="operator_ptr"></a>  CHeapPtrBase::operator-&gt;

İşaretçi-üye işleci.

```
T* operator->() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Değerini döndürür [CHeapPtrBase::m_pData](#m_pdata) üye değişkeni.

### <a name="remarks"></a>Açıklamalar

İşaret ettiği bir sınıftaki bir yöntemi çağırmak için bu işleci kullanın `CHeapPtrBase` nesne. Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir `CHeapPtrBase` işaret NULL.

##  <a name="operator_t_star"></a>  CHeapPtrBase::operator T *

Atama işleci.

```
operator T*() const throw();
```

### <a name="remarks"></a>Açıklamalar

Döndürür [CHeapPtrBase::m_pData](#m_pdata).

##  <a name="reallocatebytes"></a>  CHeapPtrBase::ReallocateBytes

Bellek yeniden ayırmak üzere bu yöntemi çağırın.

```
bool ReallocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
Yeni ayrılacak bayt cinsinden bellek miktarı.

### <a name="return-value"></a>Dönüş Değeri

Bellek başarıyla ise true değeri döndürür ayrılmış, yanlış Aksi takdirde.

## <a name="see-also"></a>Ayrıca Bkz.

[CHeapPtr Sınıfı](../../atl/reference/cheapptr-class.md)<br/>
[CComHeapPtr Sınıfı](../../atl/reference/ccomheapptr-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
