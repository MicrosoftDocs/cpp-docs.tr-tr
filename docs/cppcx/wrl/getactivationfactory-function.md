---
description: 'Daha fazla bilgi edinin: GetActivationFactory Işlevi'
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
ms.openlocfilehash: ae2384e0620282723c6f10090a0028347408b271
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124637"
---
# <a name="getactivationfactory-function"></a>GetActivationFactory İşlevi

Şablon parametresi tarafından belirtilen tür için bir etkinleştirme fabrikası alır.

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
Etkinleştirme fabrikası türünü belirten bir şablon parametresi.

*Activatableclassıd*<br/>
Etkinleştirme fabrikasının üretediği sınıfın adı.

*Çar*<br/>
Bu işlem tamamlandığında, *T* türü için etkinleştirme fabrikasına bir başvuru.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, bu işlemin neden başarısız olduğunu belirten bir HRESULT hatası.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Ad alanı:** Windows:: Foundation

## <a name="see-also"></a>Ayrıca bkz.

[Windows:: Foundation ad alanı](windows-foundation-namespace.md)
