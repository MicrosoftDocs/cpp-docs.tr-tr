---
description: 'Daha fazla bilgi edinin: CHeapPtrBase sınıfı'
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
ms.openlocfilehash: 6186f68066f4c159c16c458f9f00725478aa98a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141641"
---
# <a name="cheapptrbase-class"></a>CHeapPtrBase sınıfı

Bu sınıf, birkaç akıllı yığın işaretçisi sınıfının temelini oluşturur.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T, class Allocator = CCRTAllocator>
class CHeapPtrBase
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Yığında depolanacak nesne türü.

*Öğe*<br/>
Kullanılacak bellek ayırma sınıfı. Varsayılan olarak CRT yordamları, bellek ayırmak ve serbest bırakmak için kullanılır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHeapPtrBase:: ~ CHeapPtrBase](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHeapPtrBase:: AllocateBytes](#allocatebytes)|Bellek ayırmak için bu yöntemi çağırın.|
|[CHeapPtrBase:: Attach](#attach)|Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.|
|[CHeapPtrBase::D etach](#detach)|Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.|
|[CHeapPtrBase:: Free](#free)|Tarafından işaret edilen bir nesneyi silmek için bu yöntemi çağırın `CHeapPtrBase` .|
|[CHeapPtrBase:: ReallocateBytes](#reallocatebytes)|Belleği yeniden ayırmak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CHeapPtrBase:: operator T *](#operator_t_star)|Atama işleci.|
|[CHeapPtrBase:: operator &](#operator_amp)|& işleci.|
|[CHeapPtrBase:: operator->](#operator_ptr)|Üye işaretçisi işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CHeapPtrBase:: m_pData](#m_pdata)|İşaretçi verisi üye değişkeni.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, birkaç akıllı yığın işaretçisi sınıfının temelini oluşturur. Türetilmiş sınıflar, örneğin, [CHeapPtr](../../atl/reference/cheapptr-class.md) ve [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), kendi oluşturucularını ve işleçlerini ekler. Uygulama örnekleri için bu sınıflara bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore. h

## <a name="cheapptrbaseallocatebytes"></a><a name="allocatebytes"></a> CHeapPtrBase:: AllocateBytes

Bellek ayırmak için bu yöntemi çağırın.

```
bool AllocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
Ayrılacak bellek bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Bellek başarıyla ayrılmışsa true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, [CHeapPtrBase:: m_pData](#m_pdata) üye değişkeni şu anda var olan bir değere işaret ediyorsa bir onaylama hatası meydana gelir; diğer bir deyişle, NULL değerine eşit değildir.

## <a name="cheapptrbaseattach"></a><a name="attach"></a> CHeapPtrBase:: Attach

Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.

```cpp
void Attach(T* pData) throw();
```

### <a name="parameters"></a>Parametreler

*pData*<br/>
`CHeapPtrBase`Nesne Bu işaretçinin sahipliğini alır.

### <a name="remarks"></a>Açıklamalar

Bir `CHeapPtrBase` nesne bir işaretçinin sahipliğini aldığında, bu işlem, kapsam dışına geçtiğinde işaretçiyi ve ayrılan verileri otomatik olarak siler.

Hata ayıklama yapılarında, [CHeapPtrBase:: m_pData](#m_pdata) üye değişkeni şu anda var olan bir değere işaret ediyorsa bir onaylama hatası meydana gelir; diğer bir deyişle, NULL değerine eşit değildir.

## <a name="cheapptrbasecheapptrbase"></a><a name="dtor"></a> CHeapPtrBase:: ~ CHeapPtrBase

Yok edicisi.

```
~CHeapPtrBase() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

## <a name="cheapptrbasedetach"></a><a name="detach"></a> CHeapPtrBase::D etach

Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.

```
T* Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçinin bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Bir işaretçinin sahipliğini serbest bırakır, [CHeapPtrBase:: m_pData](#m_pdata) üye değişkenini null olarak ayarlar ve işaretçinin bir kopyasını döndürür.

## <a name="cheapptrbasefree"></a><a name="free"></a> CHeapPtrBase:: Free

Tarafından işaret edilen bir nesneyi silmek için bu yöntemi çağırın `CHeapPtrBase` .

```cpp
void Free() throw();
```

### <a name="remarks"></a>Açıklamalar

Tarafından işaret edilen nesne `CHeapPtrBase` serbest bırakılır ve [CHeapPtrBase:: m_pData](#m_pdata) üye değişkeni null olarak ayarlanır.

## <a name="cheapptrbasem_pdata"></a><a name="m_pdata"></a> CHeapPtrBase:: m_pData

İşaretçi verisi üye değişkeni.

```
T* m_pData;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişkeni işaretçi bilgisini tutar.

## <a name="cheapptrbaseoperator-amp"></a><a name="operator_amp"></a> CHeapPtrBase:: işleci &amp;

& işleci.

```
T** operator&() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne tarafından işaret edilen nesnenin adresini döndürür `CHeapPtrBase` .

## <a name="cheapptrbaseoperator--gt"></a><a name="operator_ptr"></a> CHeapPtrBase:: operator-&gt;

Üye işaretçisi işleci.

```
T* operator->() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[CHeapPtrBase:: m_pData](#m_pdata) üye değişkeninin değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Nesne tarafından işaret edilen bir sınıftaki yöntemi çağırmak için bu işleci kullanın `CHeapPtrBase` . Hata ayıklama yapılarında, NULL değeri işaret ediyorsa bir onaylama hatası meydana gelir `CHeapPtrBase` .

## <a name="cheapptrbaseoperator-t"></a><a name="operator_t_star"></a> CHeapPtrBase:: operator T *

Atama işleci.

```
operator T*() const throw();
```

### <a name="remarks"></a>Açıklamalar

[CHeapPtrBase:: m_pData](#m_pdata)döndürür.

## <a name="cheapptrbasereallocatebytes"></a><a name="reallocatebytes"></a> CHeapPtrBase:: ReallocateBytes

Belleği yeniden ayırmak için bu yöntemi çağırın.

```
bool ReallocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
Ayrılacak yeni bellek miktarı (bayt cinsinden).

### <a name="return-value"></a>Dönüş Değeri

Bellek başarıyla ayrılmışsa true, aksi takdirde false döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CHeapPtr sınıfı](../../atl/reference/cheapptr-class.md)<br/>
[CComHeapPtr sınıfı](../../atl/reference/ccomheapptr-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
