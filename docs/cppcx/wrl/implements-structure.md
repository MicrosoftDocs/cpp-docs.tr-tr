---
title: Implements Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements
- implements/Microsoft::WRL::Implements::CanCastTo
- implements/Microsoft::WRL::Implements::CastToUnknown
- implements/Microsoft::WRL::Implements::FillArrayWithIid
- implements/Microsoft::WRL::Implements::IidCount
helpviewer_keywords:
- Microsoft::WRL::Implements structure
- Microsoft::WRL::Implements::CanCastTo method
- Microsoft::WRL::Implements::CastToUnknown method
- Microsoft::WRL::Implements::FillArrayWithIid method
- Microsoft::WRL::Implements::IidCount method
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
ms.openlocfilehash: 223f37d7cabbd0b8cd238582773c05d7b9eaabf6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371402"
---
# <a name="implements-structure"></a>Implements Yapısı

Uygular `QueryInterface` ve `GetIid` belirtilen arabirimler için.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    typename I0,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil,
    typename I3 = Details::Nil,
    typename I4 = Details::Nil,
    typename I5 = Details::Nil,
    typename I6 = Details::Nil,
    typename I7 = Details::Nil,
    typename I8 = Details::Nil,
    typename I9 = Details::Nil
>
struct __declspec(novtable) Implements :
    Details::ImplementsHelper<
        RuntimeClassFlags<WinRt>,
        typename Details::InterfaceListHelper<
            I0, I1, I2, I3, I4, I5, I6, I7, I8, I9
        >::TypeT
    >,
    Details::ImplementsBase;

template <
    int flags,
    typename I0,
    typename I1,
    typename I2,
    typename I3,
    typename I4,
    typename I5,
    typename I6,
    typename I7,
    typename I8
>
struct __declspec(novtable) Implements<
        RuntimeClassFlags<flags>,
        I0, I1, I2, I3, I4, I5, I6, I7, I8> :
    Details::ImplementsHelper<
        RuntimeClassFlags<flags>,
        typename Details::InterfaceListHelper<
            I0, I1, I2, I3, I4, I5, I6, I7, I8
        >::TypeT
    >,
    Details::ImplementsBase;
```

### <a name="parameters"></a>Parametreler

*I0*<br/>
Sıfırıncı arayüz kimliği. (Zorunlu)

*I1*<br/>
İlk arayüz kimliği. (İsteğe bağlı)

*I2*<br/>
İkinci arayüz kimliği. (İsteğe bağlı)

*I3*<br/>
Üçüncü arayüz kimliği. (İsteğe bağlı)

*I4*<br/>
Dördüncü arayüz kimliği. (İsteğe bağlı)

*I5*<br/>
Beşinci arayüz kimliği. (İsteğe bağlı)

*I6*<br/>
Altıncı arayüz kimliği. (İsteğe bağlı)

*I7*<br/>
Yedinci arayüz kimliği. (İsteğe bağlı)

*I8*<br/>
Sekizinci arayüz kimliği. (İsteğe bağlı)

*I9*<br/>
Dokuzuncu arayüz kimliği. (İsteğe bağlı)

*bayraklar*<br/>
Sınıf için yapılandırma bayrakları. [RuntimeClassFlags](runtimeclassflags-structure.md) yapısında belirtilen bir veya daha fazla [RuntimeClassType](runtimeclasstype-enumeration.md) sayılandırma.

## <a name="remarks"></a>Açıklamalar

Belirtilen arabirimler listesinden türetilmiştir ve yardımcı `QueryInterface` şablonları `GetIid`uygular ve.

I9 arabirim parametresi her *I0* `IInspectable`ya türetilmelidir *I9* `IUnknown`, veya [ChainInterfaces](chaininterfaces-structure.md) şablonu. *Bayraklar* parametresi, destek için `IUnknown` `IInspectable`oluşturulup oluşturulmadığını belirler.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

| Adı        | Açıklama                               |
| ----------- | ----------------------------------------- |
| `ClassFlags`| Bir eşanlamlı `RuntimeClassFlags<WinRt>`. |

### <a name="protected-methods"></a>Korumalı Yöntemler

| Adı                                              | Açıklama                                                                                                   |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| [Uygular::CanCastTo](#cancastto)               | Belirtilen arabirime bir işaretçi alır.                                                                    |
| [Uygular::CastToUnknown](#casttounknown)       | Temel `IUnknown` arabirim için bir işaretçi alır.                                                        |
| [Uygular::FillArrayWithIid](#fillarraywithiid) | Geçerli sıfırth şablon parametresi tarafından belirtilen arabirim kimliğini belirtilen dizi öğesine ekler. |

### <a name="protected-constants"></a>Korumalı Sabitler

| Adı                              | Açıklama                                    |
| --------------------------------- | ---------------------------------------------- |
| [Uygular::IidCount](#iidcount) | Uygulanan arabirim tayının sayısını tutar. |

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`I0`

`ChainInterfaces`

`I0`

`ImplementsBase`

`ImplementsHelper`

`Implements`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** implements.h

**Ad alanı:** Microsoft::WRL

## <a name="implementscancastto"></a><a name="cancastto"></a>Uygular::CanCastTo

Belirtilen arabirime bir işaretçi alır.

```cpp
__forceinline HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parametreler

*Riid*<br/>
Arabirim kimliğine başvuru.

*Ppv*<br/>
Başarılı olursa, *riid*tarafından belirtilen arabirimin bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, E_NOINTERFACE gibi hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu, QueryInterface işlemini gerçekleştiren bir iç yardımcı işlevidir.

## <a name="implementscasttounknown"></a><a name="casttounknown"></a>Uygular::CastToUnknown

Temel `IUnknown` arabirim için bir işaretçi alır.

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Dönüş Değeri

Bu işlem her zaman `IUnknown` başarılı ve işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Dahili yardımcı işlevi.

## <a name="implementsfillarraywithiid"></a><a name="fillarraywithiid"></a>Uygular::FillArrayWithIid

Geçerli sıfırth şablon parametresi tarafından belirtilen arabirim kimliğini belirtilen dizi öğesine ekler.

```cpp
__forceinline static void FillArrayWithIid(
   unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Parametreler

*Dizin*<br/>
Bu işlem için başlangıç dizi öğesini gösteren sıfır tabanlı dizin. Bu işlem tamamlandığında, *dizin* 1 ile artımlanır.

*iids*<br/>
Tip IID bir dizi.

### <a name="remarks"></a>Açıklamalar

Dahili yardımcı işlevi.

## <a name="implementsiidcount"></a><a name="iidcount"></a>Uygular::IidCount

Uygulanan arabirim tayının sayısını tutar.

```cpp
static const unsigned long IidCount;
```
