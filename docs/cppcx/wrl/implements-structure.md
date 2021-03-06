---
description: 'Daha fazla bilgi edinin: Implements yapısı'
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
ms.openlocfilehash: b438e012b23e34b08956c969ffe604878d3065fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249834"
---
# <a name="implements-structure"></a>Implements Yapısı

`QueryInterface` `GetIid` Belirtilen arabirimler için ve uygular.

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
Diğer arabirim KIMLIĞI. Girilmesi

*I1*<br/>
İlk arabirim KIMLIĞI. (İsteğe bağlı)

*I2*<br/>
İkinci arabirim KIMLIĞI. (İsteğe bağlı)

*I3*<br/>
Üçüncü arabirim KIMLIĞI. (İsteğe bağlı)

*I4*<br/>
Dördüncü arabirim KIMLIĞI. (İsteğe bağlı)

*I5*<br/>
Beşinci arabirim KIMLIĞI. (İsteğe bağlı)

*I6*<br/>
Altıncı arabirim KIMLIĞI. (İsteğe bağlı)

*I7*<br/>
Yedinci arabirim KIMLIĞI. (İsteğe bağlı)

*I8*<br/>
Sekizinci arabirim KIMLIĞI. (İsteğe bağlı)

*I9*<br/>
Dokuzuncu arabirim KIMLIĞI. (İsteğe bağlı)

*bayraklar*<br/>
Sınıf için yapılandırma bayrakları. [RuntimeClassFlags](runtimeclassflags-structure.md) yapısında belirtilen bir veya daha fazla [RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırması.

## <a name="remarks"></a>Açıklamalar

Belirtilen arabirimlerin listesinden türetilir ve ve için yardımcı şablonları uygular `QueryInterface` `GetIid` .

Her *I0* ile *I9* arabirimi parametresi `IUnknown` , `IInspectable` ya da [ChainInterfaces](chaininterfaces-structure.md) şablonundan türetilmelidir. *Flags* parametresi, veya için desteğin oluşturulup oluşturulmayacağını belirler `IUnknown` `IInspectable` .

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

| Ad        | Açıklama                               |
| ----------- | ----------------------------------------- |
| `ClassFlags`| İçin bir eş anlamlı `RuntimeClassFlags<WinRt>` . |

### <a name="protected-methods"></a>Korumalı Yöntemler

| Ad                                              | Açıklama                                                                                                   |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| [Şunları uygular:: Canroto](#cancastto)               | Belirtilen arabirime bir işaretçi alır.                                                                    |
| [Implements:: Rotounknown](#casttounknown)       | Temel alınan arabirime yönelik bir işaretçi alır `IUnknown` .                                                        |
| [Implements:: Fillarraywithııd](#fillarraywithiid) | Belirtilen dizi öğesine geçerli bir diğer şablon parametresi tarafından belirtilen arabirim KIMLIĞINI ekler. |

### <a name="protected-constants"></a>Korunan sabitler

| Ad                              | Açıklama                                    |
| --------------------------------- | ---------------------------------------------- |
| [Implements:: ııdcount](#iidcount) | Uygulanan arabirim kimliklerinin sayısını tutar. |

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`I0`

`ChainInterfaces`

`I0`

`ImplementsBase`

`ImplementsHelper`

`Implements`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL

## <a name="implementscancastto"></a><a name="cancastto"></a> Şunları uygular:: Canroto

Belirtilen arabirime bir işaretçi alır.

```cpp
__forceinline HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parametreler

*riıd*<br/>
Arabirim KIMLIĞINE başvuru.

*PPV*<br/>
Başarılı olursa, *riıd* tarafından belirtilen arabirime yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, E_NOINTERFACE gibi bir hata belirten HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu, bir QueryInterface işlemi gerçekleştiren iç yardımcı işlevdir.

## <a name="implementscasttounknown"></a><a name="casttounknown"></a> Implements:: Rotounknown

Temel alınan arabirime yönelik bir işaretçi alır `IUnknown` .

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Dönüş Değeri

Bu işlem her zaman başarılı olur ve `IUnknown` işaretçiyi döndürür.

### <a name="remarks"></a>Açıklamalar

İç yardımcı işlevi.

## <a name="implementsfillarraywithiid"></a><a name="fillarraywithiid"></a> Implements:: Fillarraywithııd

Belirtilen dizi öğesine geçerli bir diğer şablon parametresi tarafından belirtilen arabirim KIMLIĞINI ekler.

```cpp
__forceinline static void FillArrayWithIid(
   unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Parametreler

*indeks*<br/>
Bu işlem için başlangıç dizisi öğesini gösteren sıfır tabanlı bir dizin. Bu işlem tamamlandığında, *Dizin* 1 artırılır.

*IID*<br/>
IID türünde bir dizi.

### <a name="remarks"></a>Açıklamalar

İç yardımcı işlevi.

## <a name="implementsiidcount"></a><a name="iidcount"></a> Implements:: ııdcount

Uygulanan arabirim kimliklerinin sayısını tutar.

```cpp
static const unsigned long IidCount;
```
