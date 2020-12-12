---
description: 'Hakkında daha fazla bilgi edinin: is_nothrow_constructible sınıfı'
title: is_nothrow_constructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_constructible
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
ms.openlocfilehash: 0bb822a42d149a552f18ff4d1b1c723ef9b88172
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323609"
---
# <a name="is_nothrow_constructible-class"></a>is_nothrow_constructible sınıfı

Bir türün oluşturulabilir olup olmadığını test eder ve belirtilen bağımsız değişken türleri kullanıldığında throw olarak bilinir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class... Args>
struct is_nothrow_constructible;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

*Args*\
*T* yapıcısında eşleştirilecek bağımsız değişken türleri.

## <a name="remarks"></a>Açıklamalar

Tür koşulunun bir örneği, *T* türü bağımsız *değişkenler* içindeki bağımsız değişken türleri kullanılarak oluşturulabilir ise true, Oluşturucu derleyicinin throw tarafından bilinmez; Aksi takdirde yanlış olur. Değişken tanımı düzgün biçimlendirilmişse tür *T* oluşturulabilir `T t(std::declval<Args>()...);` . Hem *T* hem de *args* içindeki tüm türler, tamamlanmış bir veya daha fazla türde **`void`** bir dizi olmalıdır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
