---
title: ArgTraits yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits
dev_langs:
- C++
helpviewer_keywords:
- ArgTraits structure
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 047754338566d476fa8e832d58dd2d4cd0776a63
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418404"
---
# <a name="argtraits-structure"></a>ArgTraits Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename TMemberFunction>
struct ArgTraits;
template<typename TDelegateInterface>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;
template<
   typename TDelegateInterface,
   typename TArg1
>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;
template<
   typename TDelegateInterface,
   typename TArg1,
   typename TArg2
>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;
template<
   typename TDelegateInterface,
   typename TArg1,
   typename TArg2,
   typename TArg3
>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;
template<
   typename TDelegateInterface,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4
>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4)>;
template<
   typename TDelegateInterface,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5
>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5)>;
template<
   typename TDelegateInterface,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6
>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;
template<
   typename TDelegateInterface,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7
>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;
template<
   typename TDelegateInterface,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8
>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;
template<
   typename TDelegateInterface,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8,
   typename TArg9
>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;
```

### <a name="parameters"></a>Parametreler

*TMemberFunction*<br/>
TypeName parametresi herhangi eşleşemez bir ArgTraits yapısı için `Invoke` metodu imzası.

*TDelegateInterface*<br/>
Bir temsilci arabirimi.

*TArg1*<br/>
İlk bağımsız değişkeninin türü `Invoke` yöntemi.

*TArg2*<br/>
İkinci bağımsız değişkeni türünü `Invoke` yöntemi.

*TArg3*<br/>
Üçüncü bağımsız değişkeninin türü `Invoke` yöntemi.

*TArg4*<br/>
Dördüncü bağımsız değişkeninin türü `Invoke` yöntemi.

*TArg5*<br/>
Beşinci bağımsız değişkeninin türü `Invoke` yöntemi.

*TArg6*<br/>
Altıncı bağımsız değişkeninin türü `Invoke` yöntemi.

*TArg7*<br/>
Yedinci bağımsız değişkeninin türü `Invoke` yöntemi.

*TArg8*<br/>
Sekizinci bağımsız değişkeninin türü `Invoke` yöntemi.

*TArg9*<br/>
Dokuzuncu bağımsız değişkeninin türü `Invoke` yöntemi.

## <a name="remarks"></a>Açıklamalar

**ArgTraits** yapıyı, arabirimi ve belirtilen bir dizi parametre içeren bir anonim üye işlevi belirtilen temsilci bildirir.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`Arg1Type`|TArg1 için typedef.|
|`Arg2Type`|TArg2 için typedef.|
|`Arg3Type`|TArg3 için typedef.|
|`Arg4Type`|TArg4 için typedef.|
|`Arg5Type`|TArg5 için typedef.|
|`Arg6Type`|TArg6 için typedef.|
|`Arg7Type`|TArg7 için typedef.|
|`Arg8Type`|TArg8 için typedef.|
|`Arg9Type`|TArg9 için typedef.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[ArgTraits::args Sabiti](../windows/argtraits-args-constant.md)|Parametre sayısını tutar `Invoke` yöntemi temsilci arabirimi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ArgTraits`

## <a name="requirements"></a>Gereksinimler

**Başlık:** event.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)