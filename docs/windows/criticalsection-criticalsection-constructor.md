---
title: CriticalSection::CriticalSection Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CriticalSection, constructor
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b992f4ad781105a8795a7bf95ff8b831ab961275
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400685"
---
# <a name="criticalsectioncriticalsection-constructor"></a>CriticalSection::CriticalSection Oluşturucusu

Mutex nesnesine benzer, ancak yalnızca tek bir işlem iş parçacığı tarafından kullanılan bir eşitleme nesnesi başlatır.

## <a name="syntax"></a>Sözdizimi

```cpp
explicit CriticalSection(
   ULONG spincount = 0
);
```

### <a name="parameters"></a>Parametreler

*spincount*<br/>
Kritik bölüm nesnenin dönüş sayısı. Varsayılan değer 0’dır.

## <a name="remarks"></a>Açıklamalar

Kritik bölümler ve spincounts hakkında daha fazla bilgi için bkz: `InitializeCriticalSectionAndSpinCount` işlevi **eşitleme** Windows API platformlarının bölümü.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[CriticalSection Sınıfı](../windows/criticalsection-class.md)