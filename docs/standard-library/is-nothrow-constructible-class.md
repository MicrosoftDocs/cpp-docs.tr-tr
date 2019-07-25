---
title: is_nothrow_constructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_constructible
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
ms.openlocfilehash: 7ec4fc3ef5d9a799d5d77124870fbb337061c94c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455998"
---
# <a name="isnothrowconstructible-class"></a>is_nothrow_constructible sınıfı

Bir türün oluşturulabilir olup olmadığını test eder ve belirtilen bağımsız değişken türleri kullanıldığında throw olarak bilinir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class... Args>
struct is_nothrow_constructible;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Sorgulanacak tür.

*Args*\
*T*yapıcısında eşleştirilecek bağımsız değişken türleri.

## <a name="remarks"></a>Açıklamalar

Tür koşulunun bir örneği, *T* türü bağımsız *değişkenler*içindeki bağımsız değişken türleri kullanılarak oluşturulabilir ise true, Oluşturucu derleyicinin throw tarafından bilinmez; Aksi takdirde yanlış olur. Değişken  tanımı `T t(std::declval<Args>()...);` düzgün biçimlendirilmişse tür T oluşturulabilir. *T* ve *args* içindeki tüm türlerin her ikisi de, bilinmeyen türler, **void**veya dizileri olmalıdır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
