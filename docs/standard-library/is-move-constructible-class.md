---
title: is_move_constructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: 1b1e450338a123c51b80f40f2369207c8b987cd6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383639"
---
# <a name="ismoveconstructible-class"></a>is_move_constructible sınıfı

Türü bir taşıma oluşturucusuna sahip olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Değerlendirilecek tür

## <a name="remarks"></a>Açıklamalar

Gerekirse true değerlendirir türü bir tür koşulu *T* taşıma işlemi kullanılarak oluşturulabilir. Bu koşulu eşdeğerdir `is_constructible<T, T&&>`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
