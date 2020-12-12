---
description: 'Hakkında daha fazla bilgi edinin: is_constructible sınıfı'
title: is_constructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_constructible
helpviewer_keywords:
- is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
ms.openlocfilehash: 66d17141693933850ce78dc15abe108664d56c8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323821"
---
# <a name="is_constructible-class"></a>is_constructible sınıfı

Belirtilen bağımsız değişken türleri kullanıldığında bir türün oluşturulabilir olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class... Args>
struct is_constructible;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

*Args*\
*T* yapıcısında eşleştirilecek bağımsız değişken türleri.

## <a name="remarks"></a>Açıklamalar

Tür koşulunun bir örneği, *T* türü, bağımsız *değişkenlerdeki bağımsız* değişken türleri kullanılarak oluşturulabilir ise true, aksi durumda false değerini taşır. Değişken tanımı düzgün biçimlendirilmişse tür *T* oluşturulabilir `T t(std::declval<Args>()...);` . Hem *T* hem de *args* içindeki tüm türler, tamamlanmış bir veya daha fazla türde **`void`** bir dizi olmalıdır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
