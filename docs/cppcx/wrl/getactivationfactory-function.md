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
ms.openlocfilehash: 430b4ed3f6a02fd3db2bcab05fbb7f21f5367b5c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213986"
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

*Şı*<br/>
Etkinleştirme fabrikası türünü belirten bir şablon parametresi.

*Activatableclassıd*<br/>
Etkinleştirme fabrikasının üretediği sınıfın adı.

*Çar*<br/>
Bu işlem tamamlandığında, *T*türü için etkinleştirme fabrikasına bir başvuru.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, bu işlemin neden başarısız olduğunu belirten bir HRESULT hatası.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Ad alanı:** Windows:: Foundation

## <a name="see-also"></a>Ayrıca bkz.

[Windows::Foundation Ad Alanı](windows-foundation-namespace.md)
