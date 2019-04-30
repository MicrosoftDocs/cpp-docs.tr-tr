---
title: is_trivially_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_assignable
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
ms.openlocfilehash: eeef85a0b26c25eb745258c7e0e35394f0cab979
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413503"
---
# <a name="istriviallyassignable-class"></a>is_trivially_assignable sınıfı

Bir değeri olup olmadığını test `From` türü basit bir şekilde atanabilen `To` türü

## <a name="syntax"></a>Sözdizimi

```cpp
template <class To, class From>
struct is_trivially_assignable;
```

### <a name="parameters"></a>Parametreler

*Alıcı*<br/>
Atamayı alan nesnenin türü.

*Kaynak*<br/>
Değer sağlayan bir nesne türü.

## <a name="remarks"></a>Açıklamalar

İfade `declval<To>() = declval<From>()` iyi biçimlendirilmiş olmalıdır ve derleyici için Önemsiz olmayan bir işlem istemek için bilinmesi gerekir. Her ikisi de `From` ve `To` tam türler olmalıdır **void**, veya bilinmeyen bağlı bir dizi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
