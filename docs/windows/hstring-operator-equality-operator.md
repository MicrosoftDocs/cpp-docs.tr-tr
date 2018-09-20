---
title: HString::Operator == işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator==
dev_langs:
- C++
ms.assetid: 77ff4c1a-e62a-4256-bf9d-0f017137c630
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dee6fd7b50d116264ea6b8b9a6b7bac3936e95cf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413724"
---
# <a name="hstringoperator-operator"></a>HString::Operator== İşleci

İki parametrenin eşit olup olmadığını gösterir.

## <a name="syntax"></a>Sözdizimi

```cpp
inline bool operator==(
               const HString& lhs,
               const HString& rhs) throw()

inline bool operator==(
                const HString& lhs,
                const HStringReference& rhs) throw()

inline bool operator==(
                const HStringReference& lhs,
                const HString& rhs) throw()

inline bool operator==(
                 const HSTRING& lhs,
                 const HString& rhs) throw()

inline bool operator==(
                 const HString& lhs,
                 const HSTRING& rhs) throw()  
```

### <a name="parameters"></a>Parametreler

*lhs*<br/>
Karşılaştırılacak ilk parametre. *lhs* olabilir bir **Hstrıng** veya `HStringReference` nesnesi veya bir HSTRING tanıtıcısına.

*Sol*<br/>
Karşılaştırılacak ikinci parametre. *sol* olabilir bir **Hstrıng** veya `HStringReference` nesnesi veya bir HSTRING tanıtıcısına.

## <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *lhs* ve *sol* parametreleri eşit; Aksi takdirde **false**.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[HString Sınıfı](../windows/hstring-class.md)