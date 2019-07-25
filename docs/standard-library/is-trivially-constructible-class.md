---
title: is_trivially_constructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_constructible
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
ms.openlocfilehash: 6f177463b985d3e7b2f7ab7783f9c3db0dcd5722
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448007"
---
# <a name="istriviallyconstructible-class"></a>is_trivially_constructible sınıfı

Belirtilen bağımsız değişken türleri kullanıldığında bir türün daha düşük bir şekilde oluşturulabilir olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Sorgulanacak tür.

*Args*\
*T*yapıcısında eşleştirilecek bağımsız değişken türleri.

## <a name="remarks"></a>Açıklamalar

Tür koşulunda bir örnek, tür *T* bağımsız *değişkenlerdeki bağımsız*değişken türleri kullanılarak önemli bir şekilde oluşturulabilir ise true, aksi durumda false barındırır. Değişken  tanımı `T t(std::declval<Args>()...);` doğru biçimlendirilmişse ve önemsiz olmayan işlemler çağırılırdiğinde, tür T oldukça uygun bir şekilde oluşturulabilir. *T* ve *args* içindeki tüm türlerin her ikisi de, bilinmeyen türler, **void**veya dizileri olmalıdır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
