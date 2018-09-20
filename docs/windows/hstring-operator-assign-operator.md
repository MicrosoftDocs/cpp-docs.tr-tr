---
title: HString::Operator = işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator=
dev_langs:
- C++
ms.assetid: 8e68c1ff-bc57-4526-810e-af3c284b4e30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8e528bed14f3f6f3b35270975833bdd17fd777db
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422655"
---
# <a name="hstringoperator-operator"></a>HString::Operator= İşleci

Başka bir değer taşır **Hstrıng** geçerli nesneye **Hstrıng** nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
HString& operator=(HString&& other) throw()  
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Mevcut bir **Hstrıng** nesne.

## <a name="remarks"></a>Açıklamalar

Varolan değerin *diğer* nesne geçerli kopyalanır **Hstrıng** nesnesi ve ardından *diğer* nesnesi yok edildiğinde.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[HString Sınıfı](../windows/hstring-class.md)