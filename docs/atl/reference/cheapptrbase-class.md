---
title: CHeapPtrBase Sınıfı
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
ms.openlocfilehash: e247b4f488411ffdcde5d1d9016436c9c36fe793
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747686"
---
# <a name="cheapptrbase-class"></a>CHeapPtrBase Sınıfı

Bu sınıf, birkaç akıllı yığın işaretçi sınıfları için temel oluşturur.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T, class Allocator = CCRTAllocator>
class CHeapPtrBase
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Yığında depolanacak nesne türü.

*Ayırıcı*<br/>
Kullanılacak bellek ayırma sınıfı. Varsayılan CRT yordamları ayırmak ve belleği boşaltmak için kullanılır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CHeapPtrBase::~CHeapPtrBase](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CHeapPtrBase::AllocateBytes](#allocatebytes)|Bellek ayırmak için bu yöntemi arayın.|
|[CHeapPtrBase::Ekle](#attach)|Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.|
|[CHeapPtrBase::Detach](#detach)|Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.|
|[CHeapPtrBase::Ücretsiz](#free)|Bir `CHeapPtrBase`. tarafından işaret edilen bir nesneyi silmek için bu yöntemi arayın|
|[CHeapPtrBase::EmlakçıBytes](#reallocatebytes)|Belleği yeniden tahsis etmek için bu yöntemi arayın.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CHeapPtrBase::operatör T*](#operator_t_star)|Döküm operatörü.|
|[CHeapPtrBase::operatör &](#operator_amp)|& operatörü.|
|[CHeapPtrBase::operatör ->](#operator_ptr)|İşaretçiden üyeye işleç.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CHeapPtrBase::m_pData](#m_pdata)|İşaretçi veri üye değişkeni.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, birkaç akıllı yığın işaretçi sınıfları için temel oluşturur. Türemiş sınıflar, örneğin, [CHeapPtr](../../atl/reference/cheapptr-class.md) ve [CComHeapPtr,](../../atl/reference/ccomheapptr-class.md)kendi yapıcıları ve işleçleri ekleyin. Uygulama örnekleri için bu sınıflara bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore.h

## <a name="cheapptrbaseallocatebytes"></a><a name="allocatebytes"></a>CHeapPtrBase::AllocateBytes

Bellek ayırmak için bu yöntemi arayın.

```
bool AllocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBayt*<br/>
Ayrılacak bellek baytlarının sayısı.

### <a name="return-value"></a>Dönüş Değeri

Bellek başarıyla ayrılırsa doğru döndürür, aksi takdirde yanlış.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, [CHeapPtrBase::m_pData](#m_pdata) üye değişkeni şu anda varolan bir değeri işaret ederse bir iddia hatası oluşur; diğer bir şey, NULL'a eşit değildir.

## <a name="cheapptrbaseattach"></a><a name="attach"></a>CHeapPtrBase::Ekle

Varolan bir işaretçinin sahipliğini almak için bu yöntemi çağırın.

```cpp
void Attach(T* pData) throw();
```

### <a name="parameters"></a>Parametreler

*Pdata*<br/>
Nesne `CHeapPtrBase` bu işaretçinin sahipliğini alır.

### <a name="remarks"></a>Açıklamalar

Bir `CHeapPtrBase` nesne bir işaretçinin sahipliğini aldığında, işaretçiyi ve ayrılan verileri kapsam dışına çıktığında otomatik olarak siler.

Hata ayıklama oluştururda, [CHeapPtrBase::m_pData](#m_pdata) üye değişkeni şu anda varolan bir değeri işaret ederse bir iddia hatası oluşur; diğer bir şey, NULL'a eşit değildir.

## <a name="cheapptrbasecheapptrbase"></a><a name="dtor"></a>CHeapPtrBase::~CHeapPtrBase

Yıkıcı.

```
~CHeapPtrBase() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest sağlar.

## <a name="cheapptrbasedetach"></a><a name="detach"></a>CHeapPtrBase::Detach

Bir işaretçinin sahipliğini serbest bırakmak için bu yöntemi çağırın.

```
T* Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçinin bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Bir işaretçinin sahipliğini serbest bırakır, [CHeapPtrBase::m_pData](#m_pdata) üye değişkenini NULL olarak ayarlar ve işaretçinin bir kopyasını döndürür.

## <a name="cheapptrbasefree"></a><a name="free"></a>CHeapPtrBase::Ücretsiz

Bir `CHeapPtrBase`. tarafından işaret edilen bir nesneyi silmek için bu yöntemi arayın

```cpp
void Free() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesne tarafından işaret `CHeapPtrBase` serbest bırakılır ve [CHeapPtrBase::m_pData](#m_pdata) üye değişken NULL olarak ayarlanır.

## <a name="cheapptrbasem_pdata"></a><a name="m_pdata"></a>CHeapPtrBase::m_pData

İşaretçi veri üye değişkeni.

```
T* m_pData;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişken işaretçi bilgilerini tutar.

## <a name="cheapptrbaseoperator-amp"></a><a name="operator_amp"></a>CHeapPtrBase::operatör&amp;

& operatörü.

```
T** operator&() throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CHeapPtrBase` Nesne tarafından işaret edilen nesnenin adresini döndürür.

## <a name="cheapptrbaseoperator--gt"></a><a name="operator_ptr"></a>CHeapPtrBase::operatör -&gt;

İşaretçiden üyeye işleç.

```
T* operator->() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

[CHeapPtrBase::m_pData](#m_pdata) üye değişkeninin değerini verir.

### <a name="remarks"></a>Açıklamalar

`CHeapPtrBase` Nesne tarafından işaret edilen bir sınıftabir yöntem çağırmak için bu işleci kullanın. Hata ayıklama oluşturur, null `CHeapPtrBase` puan bir iddia hatası oluşur.

## <a name="cheapptrbaseoperator-t"></a><a name="operator_t_star"></a>CHeapPtrBase::operatör T*

Döküm operatörü.

```
operator T*() const throw();
```

### <a name="remarks"></a>Açıklamalar

[CHeapPtrBase::m_pData](#m_pdata).

## <a name="cheapptrbasereallocatebytes"></a><a name="reallocatebytes"></a>CHeapPtrBase::EmlakçıBytes

Belleği yeniden tahsis etmek için bu yöntemi arayın.

```
bool ReallocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBayt*<br/>
Baytlarda ayrılacak yeni bellek miktarı.

### <a name="return-value"></a>Dönüş Değeri

Bellek başarıyla ayrılırsa doğru döndürür, aksi takdirde yanlış.

## <a name="see-also"></a>Ayrıca bkz.

[CHeapPtr Sınıfı](../../atl/reference/cheapptr-class.md)<br/>
[CComHeapPtr Sınıfı](../../atl/reference/ccomheapptr-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
