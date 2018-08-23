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
ms.openlocfilehash: 80af8f463d6cd1af631c6cb37c0239e7a9e85c3f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595891"
---
# <a name="hstringhstring-constructor"></a>HString::HString Oluşturucusu

Yeni bir örneğini başlatır **Hstrıng** sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
HString(HSTRING hstr = nullptr) throw();
HString(HString&& other) throw();
```

#### <a name="parameters"></a>Parametreler

*HSTR*  
Bir HSTRING tanıtıcısı.

*Diğer*  
Mevcut bir **Hstrıng** nesne.

## <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, yeni bir başlatır **Hstrıng** boş olan nesne.

İkinci Oluşturucu, yeni bir başlatır **Hstrıng** varolan değerin bir nesneye *diğer* parametresi ve ardından yok eder *diğer* parametresi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[HString Sınıfı](../windows/hstring-class.md)