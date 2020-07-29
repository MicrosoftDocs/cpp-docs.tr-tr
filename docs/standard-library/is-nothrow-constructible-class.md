---
title: is_nothrow_constructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_constructible
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
ms.openlocfilehash: e52b16965d849f992731c4ff4254fd218b944269
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217759"
---
# <a name="is_nothrow_constructible-class"></a>is_nothrow_constructible sınıfı

Bir türün oluşturulabilir olup olmadığını test eder ve belirtilen bağımsız değişken türleri kullanıldığında throw olarak bilinir.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class T, class... Args>
struct is_nothrow_constructible;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

*Args*\
*T*yapıcısında eşleştirilecek bağımsız değişken türleri.

## <a name="remarks"></a>Açıklamalar

Tür koşulunun bir örneği, *T* türü bağımsız *değişkenler*içindeki bağımsız değişken türleri kullanılarak oluşturulabilir ise true, Oluşturucu derleyicinin throw tarafından bilinmez; Aksi takdirde yanlış olur. Değişken tanımı düzgün biçimlendirilmişse tür *T* oluşturulabilir `T t(std::declval<Args>()...);` . Hem *T* hem de *args* içindeki tüm türler, tamamlanmış bir veya daha fazla türde **`void`** bir dizi olmalıdır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
