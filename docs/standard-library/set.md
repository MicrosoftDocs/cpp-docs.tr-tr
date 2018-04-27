---
title: '&lt;ayarlama&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- <set>
dev_langs:
- C++
helpviewer_keywords:
- set header
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8cd38a4a165b3fcd006ef79ec0416a3a32e39dd3
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltsetgt"></a>&lt;set&gt;

Kapsayıcı şablon sınıfları kümesi ve multiset ve bunların destekleyen şablonları tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <set>

```

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|Kümesi sürümü|Çok kümeli sürümü|Açıklama|
|-----------------|----------------------|-----------------|
|[operator! = (set)](../standard-library/set-operators.md#op_neq)|[operator! = (multiset)](../standard-library/set-operators.md#op_neq)|Testleri kümesi veya çok kümeli nesne işlecinin sol tarafındaki kümesi veya çok kümeli bir nesneye sağ tarafında eşit değil.|
|[operator < (ayarlayın)](../standard-library/set-operators.md#op_lt)|[operator < (multiset)](../standard-library/set-operators.md#op_lt_multiset)|Testleri kümesi veya çok kümeli nesne işlecinin sol tarafındaki kümesi veya çok kümeli nesneyi sağ tarafında değerinden küçük.|
|[operator < = (set)](../standard-library/set-operators.md#op_lt_eq)|[İşleç\<= (multiset)](../standard-library/set-operators.md#op_lt_eq_multiset)|Testleri kümesi veya çok kümeli nesne işlecinin sol tarafındaki kümesi veya çok kümeli bir nesneye sağ tarafında eşit veya daha az ise.|
|[operator == (set)](../standard-library/set-operators.md#op_eq_eq)|[operator == (multiset)](../standard-library/set-operators.md#op_eq_eq_multiset)|Testleri kümesi veya çok kümeli nesne işlecinin sol tarafındaki kümesi veya çok kümeli bir nesneye sağ tarafında eşittir.|
|[operator > (ayarlayın)](../standard-library/set-operators.md#op_gt)|[operator > (multiset)](../standard-library/set-operators.md#op_gt_multiset)|Testleri kümesi veya çok kümeli nesne işlecinin sol tarafındaki kümesi veya çok kümeli nesneyi sağ tarafında değerinden daha büyük.|
|[operator > = (set)](../standard-library/set-operators.md#op_gt_eq)|[operator > = (multiset)](../standard-library/set-operators.md#op_gt_eq_multiset)|Testleri kümesi veya çok kümeli nesne işlecinin sol tarafındaki büyük veya ona eşit kümesi veya çok kümeli bir nesneye sağ tarafında ise.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Kümesi sürümü|Çok kümeli sürümü|Açıklama|
|-----------------|----------------------|-----------------|
|[Değiştirme](../standard-library/set-functions.md#swap)|[Swap (multiset)](../standard-library/set-functions.md#swap_multiset)|İki kümeleri veya multisets öğelerini değiş tokuş eder.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[set Sınıfı](../standard-library/set-class.md)|Depolama ve alma verilerini bulunan öğeleri değerlerini benzersiz ve hangi göre verileri otomatik olarak sıralanır anahtar değerleri hizmet veren bir koleksiyon için kullanılır.|
|[multiset Sınıfı](../standard-library/multiset-class.md)|Hangi bulunan öğeleri değerlerin benzersiz olması gerekmez ve hangi göre verileri otomatik olarak sıralanır anahtar değerleri hangi verdikleri koleksiyondan verilerinin alınması ve depolama için kullanılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
