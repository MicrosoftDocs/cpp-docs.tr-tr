---
title: '&lt;vektör&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vector/std::swap
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
helpviewer_keywords:
- std::swap [vector]
ms.openlocfilehash: dbcb2524736bcb99693f3a4b27790c3447d58fe3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="ltvectorgt-functions"></a>&lt;vektör&gt; işlevleri


## <a name="swap"></a>  Değiştirme

İki vektör öğelerini değiş tokuş eder.

```cpp
template <class Type, class Allocator>
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`right` Öğeleri takas için sağlama vektör veya öğeleri olan vektör olanlar değiştirilebilmesi için vektör `left`.

`left` Öğeleri olan vektör olanlar değiştirilebilmesi için vektör `right`.

### <a name="remarks"></a>Açıklamalar

Üye işlevini yürütmek için kapsayıcı sınıfı vektör özelleştirilmiş bir algoritma şablon işlevi olan `left`. [Vector::Swap](../standard-library/vector-class.md) *(sağ*). İşlev şablonlarının kısmi derleyici tarafından sıralaması örneğine bunlar. Şablon işlevleri işlev çağrısı şablonla eşleşmesi benzersiz değil şekilde aşırı zaman derleyici şablon işlevi en özelleştirilmiş sürümünü seçin. Genel bir şablon işlevi sürümü **şablonu** \< **sınıfı T**> **void takas**( **T &**, **T &**), algoritma sınıfı tarafından atama çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özel sürüm kapsayıcı sınıfı iç gösterimi ile çalışabilirsiniz gibi daha hızlıdır.

### <a name="example"></a>Örnek

Üye işlevini kod örneğine bakın [vector::swap](../standard-library/vector-class.md) şablonu sürümünü kullanan bir örnek `swap`.

## <a name="see-also"></a>Ayrıca bkz.

[\<vektör >](../standard-library/vector.md)<br/>
