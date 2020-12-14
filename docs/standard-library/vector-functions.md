---
description: 'Daha fazla bilgi edinin: &lt; vektör &gt; işlevleri'
title: '&lt;vektör &gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- vector/std::swap
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
helpviewer_keywords:
- std::swap [vector]
ms.openlocfilehash: c59e2626a2062be90d2cb8201b058d5ee148ef55
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187890"
---
# <a name="ltvectorgt-functions"></a>&lt;vektör &gt; işlevleri

## <a name="swap"></a><a name="swap"></a> Kur

İki vektörün öğelerini değiş tokuş eder.

```cpp
template <class Type, class Allocator>
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Değiştirilecek öğeleri sağlayan vektör veya öğeleri, vektörünün *sol* tarafında değiş tokuş edilecek vektör.

*tarafta*\
Öğeleri vektör *sağdakilerle* değiş tokuş edilecek vektör.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, üye işlevini yürütmek için kapsayıcı sınıfı vektörü üzerinde özelleştirilmiş bir algoritmadır `left` . [vector:: Swap](../standard-library/vector-class.md) *(sağ*). Bunlar, derleyici tarafından işlev şablonlarının Kısmi sıralama örnekleridir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. **`template`** \< **class T**> Algoritma sınıfında, **void Swap**( **t&**, **t&**) şablon işlevinin genel sürümü atama ile çalışır ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

### <a name="example"></a>Örnek

Şablon sürümünü kullanan bir örnek için [vector:: Swap](../standard-library/vector-class.md) üye işlevine yönelik kod örneğine bakın `swap` .
