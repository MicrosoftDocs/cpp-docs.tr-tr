---
title: 'Vector&lt;bool&gt;:: Reference sınıfı'
ms.date: 11/04/2016
f1_keywords:
- vector/vector<bool>::reference
helpviewer_keywords:
- vector<bool> reference class
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
ms.openlocfilehash: 65bfc91cf5dc79fb1e5151a6f62c394b4579883b
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453208"
---
# <a name="vectorltboolgtreference-class"></a>Vector&lt;bool&gt;:: Reference sınıfı

Sınıfı, benzetimi`bool&`yapılacak [vektör\<bool > sınıfı](../standard-library/vector-bool-class.md) tarafından sunulan bir ara sunucu sınıfıdır. `vector<bool>::reference`

## <a name="remarks"></a>Açıklamalar

C++ yerel olarak doğrudan başvuruların bitlere atanmasına izin vermediğinden, benzetimli bir başvuru gereklidir. `vector<bool>`, bu proxy sınıfı kullanılarak başvurulabilen her öğe için yalnızca bir bit kullanır. Bununla birlikte, belirli atamalar geçersiz olduğundan başvuru benzetimi tam değil. Örneğin, `vector<bool>::reference` nesnenin adresi alınamadığından, kullanmayı `vector<bool>::operator&` denedikleri aşağıdaki kod doğru değildir:

```cpp
vector<bool> vb;
// ...
bool* pb = &vb[1]; // conversion error - do not use
bool& refb = vb[1];   // conversion error - do not use
```

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[yazmayı](../standard-library/vector-bool-reference-flip.md)|Bir vektör öğesinin Boolean değerini tersine çevirir.|
|[işleç bool](../standard-library/vector-bool-reference-operator-bool.md)|Kaynağından `vector<bool>::reference` **bool**'a örtük bir dönüştürme sağlar.|
|[operator=](../standard-library/vector-bool-reference-operator-assign.md)|Bir bite bir Boolean değeri, veya başvurulan bir öğenin tuttuğu değeri atar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi**: \<vektör >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<vektör >](../standard-library/vector.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
