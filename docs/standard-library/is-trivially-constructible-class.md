---
description: 'Hakkında daha fazla bilgi edinin: is_trivially_constructible sınıfı'
title: is_trivially_constructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_constructible
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
ms.openlocfilehash: 4a5c3e20366c4e87aa731c6d6a69787286b947b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247637"
---
# <a name="is_trivially_constructible-class"></a>is_trivially_constructible sınıfı

Belirtilen bağımsız değişken türleri kullanıldığında bir türün daha düşük bir şekilde oluşturulabilir olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

*Args*\
*T* yapıcısında eşleştirilecek bağımsız değişken türleri.

## <a name="remarks"></a>Açıklamalar

Tür koşulunda bir örnek, tür *T* *Bağımsız değişkenlerdeki bağımsız* değişken türleri kullanılarak önemli bir şekilde oluşturulabilir ise true, aksi durumda false barındırır. Değişken  tanımı `T t(std::declval<Args>()...);` doğru biçimlendirilmişse ve önemsiz olmayan işlemler çağırılırdiğinde, tür T oldukça uygun bir şekilde oluşturulabilir. Hem *T* hem de *args* içindeki tüm türler, tamamlanmış bir veya daha fazla türde **`void`** bir dizi olmalıdır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
