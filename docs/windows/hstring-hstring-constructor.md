---
title: HString::HString Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
dev_langs:
- C++
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 59ec7c1635b825cc300e28e5c02e2a3864a6c123
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442259"
---
# <a name="hstringhstring-constructor"></a>HString::HString Oluşturucusu

Yeni bir örneğini başlatır **Hstrıng** sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
HString(HSTRING hstr = nullptr) throw();
HString(HString&& other) throw();
```

#### <a name="parameters"></a>Parametreler

*HSTR*<br/>
Bir HSTRING tanıtıcısı.

*Diğer*<br/>
Mevcut bir **Hstrıng** nesne.

## <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, yeni bir başlatır **Hstrıng** boş olan nesne.

İkinci Oluşturucu, yeni bir başlatır **Hstrıng** varolan değerin bir nesneye *diğer* parametresi ve ardından yok eder *diğer* parametresi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[HString Sınıfı](../windows/hstring-class.md)