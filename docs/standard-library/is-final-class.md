---
title: is_final sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_final
helpviewer_keywords:
- is_final
ms.assetid: 9dbad82f-6685-4909-94e8-98e4a93994b9
ms.openlocfilehash: f605b160f6ed71aaafcc7c391e17180e4b243444
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446545"
---
# <a name="isfinal-class"></a>is_final sınıfı

Türü olarak işaretlenmiş bir sınıf türü olup olmadığını sınar `final`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_final;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *T* sınıf türü olarak işaretlenmiş `final`, aksi takdirde false tutar. Varsa *T* bir sınıf türü tam bir tür olmalıdır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[final Tanımlayıcısı](../cpp/final-specifier.md)<br/>
