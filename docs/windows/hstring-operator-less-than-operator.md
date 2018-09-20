---
title: HString::Operator&lt; işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator<
dev_langs:
- C++
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fa4a10235f37a3ea174965ad56f63d078e3cbde2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403597"
---
# <a name="hstringoperatorlt-operator"></a>HString::Operator&lt; işleci

İkinci parametre ilk parametre olup değerinden gösterir.

## <a name="syntax"></a>Sözdizimi

```cpp
inline bool operator<(
    const HString& lhs,
    const HString& rhs) throw()  
```

### <a name="parameters"></a>Parametreler

*lhs*<br/>
Karşılaştırılacak ilk parametre. *lhs* başvuru olabilir bir **Hstrıng**.

*Sol*<br/>
Karşılaştırılacak ikinci parametre. *Sol* başvuru olabilir bir **Hstrıng**.

## <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *lhs* parametresi değerinden daha küçük *sol* parametre; Aksi takdirde **false**.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[HString Sınıfı](../windows/hstring-class.md)