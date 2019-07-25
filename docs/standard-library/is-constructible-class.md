---
title: is_constructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_constructible
helpviewer_keywords:
- is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
ms.openlocfilehash: dc0596ac7a3fc2bcbcbe49f5fa4b20a971e5e445
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452857"
---
# <a name="isconstructible-class"></a>is_constructible sınıfı

Belirtilen bağımsız değişken türleri kullanıldığında bir türün oluşturulabilir olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class... Args>
struct is_constructible;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Sorgulanacak tür.

*Args*\
*T*yapıcısında eşleştirilecek bağımsız değişken türleri.

## <a name="remarks"></a>Açıklamalar

Tür koşulunun bir örneği, *T* türü, bağımsız *değişkenlerdeki bağımsız*değişken türleri kullanılarak oluşturulabilir ise true, aksi durumda false değerini taşır. Değişken  tanımı `T t(std::declval<Args>()...);` düzgün biçimlendirilmişse tür T oluşturulabilir. *T* ve *args* içindeki tüm türlerin her ikisi de, bilinmeyen türler, **void**veya dizileri olmalıdır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
