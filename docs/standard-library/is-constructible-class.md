---
title: is_constructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_constructible
helpviewer_keywords:
- is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
ms.openlocfilehash: c921efd5b7e12873ce986952029ae39f118ad763
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336861"
---
# <a name="isconstructible-class"></a>is_constructible sınıfı

Belirtilen bağımsız değişken türler kullanıldığında bir tür atmamalıdır olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class... Args>
struct is_constructible;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

*Args*<br/>
Bir oluşturucuda eşleştirmek için bağımsız değişken türleri *T*.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *T* atmamalıdır olan bağımsız değişken türleri kullanarak *Args*, aksi takdirde false tutar. Tür *T* atmamalıdır olduğundan, değişken tanımını `T t(std::declval<Args>()...);` doğru oluşturulmamış. Her ikisi de *T* içindeki tüm türler *Args* tam türler olmalıdır **void**, veya bilinmeyen bağlı bir dizi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
