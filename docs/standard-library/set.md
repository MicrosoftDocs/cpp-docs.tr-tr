---
title: '&lt;set&gt;'
ms.date: 11/04/2016
f1_keywords:
- <set>
helpviewer_keywords:
- set header
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
ms.openlocfilehash: f5f33cbb179e3d0304f8128066dc04d6c3927d8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565379"
---
# <a name="ltsetgt"></a>&lt;set&gt;

Kapsayıcı şablon sınıfları kümesi ve multiset ve kendi destek şablonları tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <set>

```

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|Sürümü Ayarla|Multiset sürümü|Açıklama|
|-----------------|----------------------|-----------------|
|[işleç! = (set)](../standard-library/set-operators.md#op_neq)|[işleç! = (multiset)](../standard-library/set-operators.md#op_neq)|İşlecin sol tarafındaki multiset nesne veya kümesini kümesi veya işlecin sağ tarafındaki multiset nesneye eşit olup olmadığını sınar.|
|[operator < (set)](../standard-library/set-operators.md#op_lt)|[operator < (multiset)](../standard-library/set-operators.md#op_lt_multiset)|İşlecin sol tarafındaki multiset nesne veya kümesini kümesi veya çok kümeli nesnesinin işlecin sağ tarafındaki küçüktür olup olmadığını sınar.|
|[operator < = (set)](../standard-library/set-operators.md#op_lt_eq)|[İşleç\<= (multiset)](../standard-library/set-operators.md#op_lt_eq_multiset)|Kümesi veya çok kümeli nesne işlecinin sol tarafındaki küçüktür veya eşittir kümesi veya işlecin sağ tarafındaki multiset nesne olup olmadığını sınar.|
|[işleç == (set)](../standard-library/set-operators.md#op_eq_eq)|[işleç == (multiset)](../standard-library/set-operators.md#op_eq_eq_multiset)|İşlecin sol tarafındaki multiset nesne veya kümesini kümesi veya işlecin sağ tarafındaki multiset nesneye eşit olup olmadığını sınar.|
|[operator > (set)](../standard-library/set-operators.md#op_gt)|[operator > (multiset)](../standard-library/set-operators.md#op_gt_multiset)|İşlecin sol tarafındaki multiset nesne veya kümesini kümesi veya çok kümeli nesnesinin işlecin sağ tarafındaki büyük olup olmadığını sınar.|
|[operator > = (set)](../standard-library/set-operators.md#op_gt_eq)|[operator > = (multiset)](../standard-library/set-operators.md#op_gt_eq_multiset)|Büyüktür veya eşittir kümesi veya işlecin sağ tarafındaki multiset nesne kümesi ya da işlecinin sol tarafındaki multiset nesne olup olmadığını sınar.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Sürümü Ayarla|Multiset sürümü|Açıklama|
|-----------------|----------------------|-----------------|
|[değiştirme](../standard-library/set-functions.md#swap)|[Swap (multiset)](../standard-library/set-functions.md#swap_multiset)|İki kümeleri veya multisets öğelerini birbiriyle değiştirir.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[set Sınıfı](../standard-library/set-class.md)|Depolama ve, içerdiği öğelerin değerlerinin benzersiz olduğu ve verilerin otomatik sıralamasına göre anahtar değerler olarak hizmet verdikleri bir koleksiyondan verilerin alınması için kullanılır.|
|[multiset Sınıfı](../standard-library/multiset-class.md)|Depolama ve, içerdiği öğelerin değerlerinin benzersiz olması gerekmez ve hangi verilerin otomatik sıralamasına göre anahtar değerler olarak verdikleri bir koleksiyondan verilerin alınması için kullanılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
