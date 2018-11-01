---
title: is_trivially_constructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_constructible
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
ms.openlocfilehash: c83bea8be5c88876ffa25337464caa62b998ab45
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628845"
---
# <a name="istriviallyconstructible-class"></a>is_trivially_constructible sınıfı

Belirtilen bağımsız değişken türler kullanıldığında bir türü basit bir şekilde atmamalıdır olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

*Args*<br/>
Bir oluşturucuda eşleştirmek için bağımsız değişken türleri *T*.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *T* bağımsız değişken türleri kullanarak basit bir şekilde atmamalıdır olduğu *Args*, aksi takdirde false tutar. Tür *T* basit bir şekilde atmamalıdır olduğundan, değişken tanımını `T t(std::declval<Args>()...);` iyi biçimlendirilmemiş ve önemsiz olmayan bir işlem çağırmak için bilinen. Her ikisi de *T* içindeki tüm türler *Args* tam türler olmalıdır **void**, veya bilinmeyen bağlı bir dizi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
