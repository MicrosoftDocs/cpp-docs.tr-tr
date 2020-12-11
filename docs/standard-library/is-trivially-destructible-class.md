---
description: 'Hakkında daha fazla bilgi edinin: is_trivially_destructible sınıfı'
title: is_trivially_destructible sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_destructible
helpviewer_keywords:
- is_trivially_destructible
ms.assetid: 3f7a787d-2448-40c5-ac51-a228318e02ce
ms.openlocfilehash: 41f36c027175cbf67049eed986b9188ba1532048
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154363"
---
# <a name="is_trivially_destructible-class"></a>is_trivially_destructible sınıfı

Türün, bir ölçüde geri dönüşlü şekilde geri çevrilebilir olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_trivially_destructible;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* türü, bir geri çevrilebilir tür ise true, yok edicinin ise önemsiz olmayan işlemler kullanmak için derleyici tarafından bilinir. Aksi takdirde, yanlış olur.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
