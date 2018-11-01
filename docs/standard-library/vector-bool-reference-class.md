---
title: 'vektör&lt;bool&gt;:: reference sınıfı'
ms.date: 11/04/2016
f1_keywords:
- vector/vector<bool>::reference
helpviewer_keywords:
- vector<bool> reference class
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
ms.openlocfilehash: 7930c1cd93cd05a752d4997b9480c766ee26bd99
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471506"
---
# <a name="vectorltboolgtreference-class"></a>vektör&lt;bool&gt;:: reference sınıfı

`vector<bool>::reference` Tarafından sağlanan bir proxy sınıfı [vektör\<bool > sınıfı](../standard-library/vector-bool-class.md) benzetimini yapmak için `bool&`.

## <a name="remarks"></a>Açıklamalar

C++ yerel olarak doğrudan başvuruların bitlere atanmasına izin vermediğinden, benzetimli bir başvuru gereklidir. `vector<bool>` Bu proxy sınıfı kullanılarak başvurulabilen öğesi başına yalnızca bir bit kullanır. Bununla birlikte, belirli atamalar geçersiz olduğundan başvuru benzetimi tam değil. Örneğin, çünkü adresini `vector<bool>::reference` nesne olamaz alınamadığından, kullanmaya çalışırsa aşağıdaki kodu `vector<bool>::operator&` doğru değildir:

```cpp
vector<bool> vb;
// ...
bool* pb = &vb[1]; // conversion error - do not use
bool& refb = vb[1];   // conversion error - do not use
```

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Çevir](../standard-library/vector-bool-reference-flip.md)|Bir vektör öğesinin Boolean değerini tersine çevirir.|
|[bool işleci](../standard-library/vector-bool-reference-operator-bool.md)|Örtük bir dönüştürme sağlar `vector<bool>::reference` için **bool**.|
|[operator=](../standard-library/vector-bool-reference-operator-assign.md)|Bir bite bir Boolean değeri, veya başvurulan bir öğenin tuttuğu değeri atar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<vektör >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<vektör >](../standard-library/vector.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
