---
title: is_trivially_constructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_constructible
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
ms.openlocfilehash: 1f835dd348c6ef7f2ca7cd01f04c5afc059a55b5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222335"
---
# <a name="is_trivially_constructible-class"></a>is_trivially_constructible sınıfı

Belirtilen bağımsız değişken türleri kullanıldığında bir türün daha düşük bir şekilde oluşturulabilir olup olmadığını test eder.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

*Args*\
*T*yapıcısında eşleştirilecek bağımsız değişken türleri.

## <a name="remarks"></a>Açıklamalar

Tür koşulunda bir örnek, tür *T* *Bağımsız değişkenlerdeki bağımsız*değişken türleri kullanılarak önemli bir şekilde oluşturulabilir ise true, aksi durumda false barındırır. Değişken *T* tanımı `T t(std::declval<Args>()...);` doğru biçimlendirilmişse ve önemsiz olmayan işlemler çağırılırdiğinde, tür T oldukça uygun bir şekilde oluşturulabilir. Hem *T* hem de *args* içindeki tüm türler, tamamlanmış bir veya daha fazla türde **`void`** bir dizi olmalıdır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
