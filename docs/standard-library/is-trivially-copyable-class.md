---
description: 'Hakkında daha fazla bilgi edinin: is_trivially_copyable sınıfı'
title: is_trivially_copyable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copyable
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
ms.openlocfilehash: 0c3590f1549f064492b361ae2ddeff665e9365ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118478"
---
# <a name="is_trivially_copyable-class"></a>is_trivially_copyable sınıfı

Türün bir üçlü kopyalanabilir türü olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_trivially_copyable;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* bir örnek bir kopyalanabilir türü ise true, aksi takdirde false değerini tutar. Üçlü kopyalanabilir türlerinin önemsiz olmayan kopyalama işlemleri, taşıma işlemleri veya yok ediciler yoktur. Genellikle, bir kopyalama işlemi bit düzeyinde bir kopya olarak uygulanmıyorsa önemsiz olarak değerlendirilir. Hem yerleşik türler hem de kopyalanabilir türler dizileri, önemli kopyalanabilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
