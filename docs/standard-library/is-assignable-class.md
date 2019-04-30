---
title: is_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_assignable
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
ms.openlocfilehash: b1357bf8c5ad4dfd5035855e34a8fd6a7ed73d15
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391016"
---
# <a name="isassignable-class"></a>is_assignable sınıfı

Bir değeri olup olmadığını test `From` türüne atanabilen bir `To` türü.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>Parametreler

*Alıcı*<br/>
Atamayı alan nesnenin türü.

*Kaynak*<br/>
Değer sağlayan bir nesne türü.

## <a name="remarks"></a>Açıklamalar

Değerlendirilmemiş ifade `declval<To>() = declval<From>()` iyi biçimlendirilmiş olmalıdır. Her ikisi de `From` ve `To` tam türler olmalıdır **void**, veya bilinmeyen bağlı bir dizi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
