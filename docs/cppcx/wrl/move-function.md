---
title: Move İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Move
helpviewer_keywords:
- Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
ms.openlocfilehash: 8d7c959ecb2d3c06872871ba062d2be603489141
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031280"
---
# <a name="move-function"></a>Move İşlevi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
inline typename RemoveReference<T>::Type&& Move(
   _Inout_ T&& arg
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Bağımsız değişken türü.

*bağımsız değişken*<br/>
Taşımak için bir bağımsız değişken.

## <a name="return-value"></a>Dönüş Değeri

Parametre *arg* başvurusunu veya rvalue başvurusunu nitelikler sonra varsa kaldırıldı.

## <a name="remarks"></a>Açıklamalar

Belirtilen bağımsız değişken bir konumdan diğerine taşır.

Daha fazla bilgi için **taşıma semantiği** bölümünü [Rvalue başvuru Bildirimcisi: & &](../../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** internal.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)