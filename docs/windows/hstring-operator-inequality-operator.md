---
title: HString::Operator! = işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator!=
dev_langs:
- C++
ms.assetid: dcdd2aca-e7d6-4bf1-b2de-03efbb430a93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b5446fb6fa0722018e4ab7734019e677b6acec7c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435213"
---
# <a name="hstringoperator-operator"></a>HString::Operator!= İşleci

İki parametrenin eşit olup olmadığını gösterir.

## <a name="syntax"></a>Sözdizimi

```cpp
inline bool operator!=( const HString& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HStringReference& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HString& lhs,
                        const HStringReference& rhs) throw()

inline bool operator!=( const HSTRING& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HString& lhs,
                        const HSTRING& rhs) throw()  
```

### <a name="parameters"></a>Parametreler

*lhs*<br/>
Karşılaştırılacak ilk parametre. *lhs* olabilir bir **Hstrıng** veya `HStringReference` nesnesi veya bir HSTRING tanıtıcısına.

*Sol*<br/>
Karşılaştırılacak ikinci parametre. *sol* olabilir bir **Hstrıng** veya `HStringReference` nesnesi veya bir HSTRING tanıtıcısına.

## <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *lhs* ve *sol* parametreleri eşit; Aksi takdirde değil **false**.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[HString Sınıfı](../windows/hstring-class.md)