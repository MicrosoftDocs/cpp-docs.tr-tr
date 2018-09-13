---
title: Uygulayan yapısı | Microsoft Docs
ms.custom: ''
ms.date: 09/11/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements
- implements/Microsoft::WRL::Implements::CanCastTo
- implements/Microsoft::WRL::Implements::CastToUnknown
- implements/Microsoft::WRL::Implements::FillArrayWithIid
- implements/Microsoft::WRL::Implements::IidCount
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Implements structure
- Microsoft::WRL::Implements::CanCastTo method
- Microsoft::WRL::Implements::CastToUnknown method
- Microsoft::WRL::Implements::FillArrayWithIid method
- Microsoft::WRL::Implements::IidCount method
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18616b1010dfe6a23861c512b1113c30fe5251ce
ms.sourcegitcommit: b4432d30f255f0cb58dce69cbc8cbcb9d44bc68b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45535359"
---
# <a name="implements-structure"></a>Implements Yapısı

Implements `QueryInterface` ve `GetIid` belirtilen arabirimleri için.

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
struct __declspec(novtable) Implements : Details::ImplementsHelper<RuntimeClassFlags<WinRt>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT>, Details::ImplementsBase;
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
struct __declspec(novtable) Implements<RuntimeClassFlags<flags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : Details::ImplementsHelper<RuntimeClassFlags<flags>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT>, Details::ImplementsBase;
```

### <a name="parameters"></a>Parametreler

*I0*  
Sıfırıncı arabirim kimliği. (Zorunlu)

*I1*  
İlk arabirim kimliği. (İsteğe bağlı)

*I2*  
İkinci arabirim kimliği. (İsteğe bağlı)

*I3*  
Üçüncü arabirim kimliği. (İsteğe bağlı)

*I4*  
Dördüncü arabirim kimliği. (İsteğe bağlı)

*I5*  
Beşinci arabirim kimliği. (İsteğe bağlı)

*I6*  
Altıncı arabirim kimliği. (İsteğe bağlı)

*I7*  
Yedinci arabirim kimliği. (İsteğe bağlı)

*I8*  
Sekizinci arabirim kimliği. (İsteğe bağlı)

*I9*  
Dokuzuncu arabirim kimliği. (İsteğe bağlı)

*bayrakları*  
Sınıfı için yapılandırma bayraklar. Bir veya daha fazla [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) belirtilmiş numaralandırmalar bir [RuntimeClassFlags](../windows/runtimeclassflags-structure.md) yapısı.

## <a name="remarks"></a>Açıklamalar

Belirtilen arabirimleri listesinden türetilen ve için şablonları yardımcı uygulayan `QueryInterface` ve `GetIid`.

Her *I0* aracılığıyla *I9* arabirimi parametresi öğesinden türetilmelidir `IUnknown`, `IInspectable`, veya [Chainınterfaces](../windows/chaininterfaces-structure.md) şablonu. *Bayrakları* parametre desteği için oluşturulup oluşturulmayacağını belirler `IUnknown` veya `IInspectable`.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

| Ad        | Açıklama                               |
| ----------- | ----------------------------------------- |
| `ClassFlags`| İçin bir eşanlamlı `RuntimeClassFlags<WinRt>`. |

### <a name="protected-methods"></a>Korumalı Yöntemler

| Ad                                              | Açıklama                                                                                                   |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| [Implements::cancastto](#cancastto)               | Belirtilen arabirim için bir işaretçi alır.                                                                    |
| [Implements::casttounknown](#casttounknown)       | Temel alınan bir işaretçi alır `IUnknown` arabirimi.                                                        |
| [Implements::fillarraywithıid](#fillarraywithiid) | Belirtilen bir dizi öğesine geçerli sıfırıncı şablon parametresi tarafından belirtilen arabirim kimliği ekler. |

### <a name="protected-constants"></a>Korumalı sabitleri

| Ad                              | Açıklama                                    |
| --------------------------------- | ---------------------------------------------- |
| [Implements::ıidcount](#iidcount) | Uygulanan arabirimi kimlikleri sayısını tutar. |

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`I0`

`ChainInterfaces`

`I0`

`ImplementsBase`

`ImplementsHelper`

`Implements`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="cancastto"></a>Implements::cancastto

Belirtilen arabirim için bir işaretçi alır.

```cpp
__forceinline HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parametreler

*riid*  
Başvuru için bir arabirim kimliği.

*ppv*  
Başarılı bir arabirim işaretçisi tarafından belirttiyseniz *riid*.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, e_noınterface gibi hatayı gösteren HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu QueryInterface işlemi gerçekleştiren bir iç yardımcı işlevdir.

## <a name="casttounknown"></a>Implements::casttounknown

Temel alınan bir işaretçi alır `IUnknown` arabirimi.

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Dönüş Değeri

Bu işlem, her zaman başarılı olur ve döndürür `IUnknown` işaretçi.

### <a name="remarks"></a>Açıklamalar

İç yardımcı işlevi.

## <a name="fillarraywithiid"></a>Implements::fillarraywithıid

Belirtilen bir dizi öğesine geçerli sıfırıncı şablon parametresi tarafından belirtilen arabirim kimliği ekler.

```cpp
__forceinline static void FillArrayWithIid(
   unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Parametreler

*Dizin*  
Bu işlem için başlangıç dizi öğesini gösteren sıfır tabanlı dizini. Bu işlem tamamlandığında *dizin* 1 azaltılır.

*IID'leri*  
IID türünde bir dizi.

### <a name="remarks"></a>Açıklamalar

İç yardımcı işlevi.

## <a name="iidcount"></a>Implements::ıidcount

Uygulanan arabirimi kimlikleri sayısını tutar.

```cpp
static const unsigned long IidCount;
```
