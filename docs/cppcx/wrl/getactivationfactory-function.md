---
title: GetActivationFactory İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
helpviewer_keywords:
- GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
ms.openlocfilehash: 82c83e95648eeb0fc8985777156659a2ffb876a8
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787053"
---
# <a name="getactivationfactory-function"></a>GetActivationFactory İşlevi

Şablon parametresi tarafından belirtilen tür için bir etkinleştirme üretecini alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
inline HRESULT GetActivationFactory(
   _In_ HSTRING activatableClassId,
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Şablon parametresi etkinleştirme fabrikası türünü belirtir.

*activatableClassId*<br/>
Etkinleştirme üretecin üretebileceği sınıfı adı.

*Fabrika*<br/>
Bu işlem tamamlandığında, bir başvuru türü için etkinleştirme fabrikası *T*.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, bu işlem başarısız olmasının gösteren HRESULT hatası.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Windows::Foundation

## <a name="see-also"></a>Ayrıca Bkz.

[Windows::Foundation Ad Alanı](windows-foundation-namespace.md)