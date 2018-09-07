---
title: is_move_assignable sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_move_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_move_assignable
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12647c6f2243b0804343f0485737a28c79afc6f0
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100241"
---
# <a name="ismoveassignable-class"></a>is_move_assignable sınıfı

Atanan türü olabilir, testleri taşıyın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Bir türü taşıma atanabilir ise bir başvuru türü bir rvalue başvuru türüne atanabilir. Tür koşulu eşdeğerdir `is_assignable<T&, T&&>`. Atanabilir türleri başvurulabilir skaler türler ve taşıma atama işleçleri derleyici tarafından oluşturulan veya kullanıcı tanımlı olan sınıf türleri taşıyın.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
