---
title: 'Vector &lt; bool &gt; :: Reference sınıfı'
ms.date: 11/04/2016
f1_keywords:
- vector/vector<bool>::reference
helpviewer_keywords:
- vector<bool> reference class
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
ms.openlocfilehash: 3dde17522c05a05bda04c338682b4b3f9920a972
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228108"
---
# <a name="vectorltboolgtreference-class"></a>Vector &lt; bool &gt; :: Reference sınıfı

`vector<bool>::reference`Sınıfı, benzetimini yapmak için [vektör \<bool> sınıfı](../standard-library/vector-bool-class.md) tarafından sunulan bir proxy sınıfıdır `bool&` .

## <a name="remarks"></a>Açıklamalar

C++ yerel olarak doğrudan başvuruların bitlere atanmasına izin vermediğinden, benzetimli bir başvuru gereklidir. `vector<bool>`, bu proxy sınıfı kullanılarak başvurulabilen her öğe için yalnızca bir bit kullanır. Bununla birlikte, belirli atamalar geçersiz olduğundan başvuru benzetimi tam değil. Örneğin, `vector<bool>::reference` nesnenin adresi alınamadığından, kullanmayı denedikleri aşağıdaki kod `vector<bool>::operator&` doğru değildir:

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
|[işleç bool](../standard-library/vector-bool-reference-operator-bool.md)|Öğesinden öğesine örtük bir dönüştürme `vector<bool>::reference` sağlar **`bool`** .|
|[işleç =](../standard-library/vector-bool-reference-operator-assign.md)|Bir bite bir Boolean değeri, veya başvurulan bir öğenin tuttuğu değeri atar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**:\<vector>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<vector>](../standard-library/vector.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
