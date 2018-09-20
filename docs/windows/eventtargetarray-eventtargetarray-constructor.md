---
title: EventTargetArray::EventTargetArray Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
dev_langs:
- C++
helpviewer_keywords:
- EventTargetArray, constructor
ms.assetid: 6c6d3737-3cd3-4515-a8f6-d27901bb8ed2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dc59b9c93cebb622f40881d961709079abcd9166
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388637"
---
# <a name="eventtargetarrayeventtargetarray-constructor"></a>EventTargetArray::EventTargetArray Oluşturucusu

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
EventTargetArray(
   _Out_ HRESULT* hr,
   size_t items
);
```

### <a name="parameters"></a>Parametreler

*İK*<br/>
Bu oluşturucu işlemlerinden sonra parametre *ik* dizinin ayırma başarılı veya başarısız olduğunu gösterir. İçin olası değerler aşağıdaki tabloda *ik*.

S_OK işlemi başarılı oldu.

Dizi için E_OUTOFMEMORY bellek ayrılamıyor.

S_FALSE parametresi *öğeleri* sıfırdan küçük veya ona eşit.

*Öğeleri*<br/>
Ayrılacak dizi öğelerinin sayısı.

## <a name="remarks"></a>Açıklamalar

Yeni bir örneğini başlatır **EventTargetArray** sınıfı.

**EventTargetArray** bir dizi olay işleyicileri tutmak için kullanılan bir `EventSource` nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** event.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[EventTargetArray Sınıfı](../windows/eventtargetarray-class.md)<br/>
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)