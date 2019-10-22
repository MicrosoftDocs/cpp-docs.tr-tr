---
title: '&lt;set&gt;'
ms.date: 11/04/2016
f1_keywords:
- <set>
helpviewer_keywords:
- set header
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
ms.openlocfilehash: fed6219c483bdade0132d5faae8b6597bcc5d732
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72686468"
---
# <a name="ltsetgt"></a>&lt;set&gt;

Küme ve çoklu küme ve destekleyici şablonlarının bulunduğu kapsayıcı sınıfı şablonları tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<set >

**Ad alanı:** std

> [!NOTE]
> @No__t_0set > kitaplığı `#include <initializer_list>` ifadesini de kullanır.

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|Sürümü ayarla|Çoklu küme sürümü|Açıklama|
|-|-|-|
|[işleç! = (küme)](../standard-library/set-operators.md#op_neq)|[işleç! = (çoklu küme)](../standard-library/set-operators.md#op_neq)|İşlecin sol tarafındaki küme veya çok kümeli nesne sağ taraftaki küme veya çok kümeli nesneye eşit değilse sınar.|
|[işleç < (küme)](../standard-library/set-operators.md#op_lt)|[işleç < (çoklu küme)](../standard-library/set-operators.md#op_lt_multiset)|İşlecin sol tarafındaki küme veya çoklu küme nesnesinin, sağ taraftaki küme veya çoklu küme nesnesinden küçük olup olmadığını test eder.|
|[işleç < = (küme)](../standard-library/set-operators.md#op_lt_eq)|[işleç \< = (çoklu küme)](../standard-library/set-operators.md#op_lt_eq_multiset)|İşlecin sol tarafındaki küme veya çoklu küme nesnesinin, sağ taraftaki küme veya çok kümeli nesneden küçük veya ona eşit olup olmadığını sınar.|
|[işleç = = (küme)](../standard-library/set-operators.md#op_eq_eq)|[işleç = = (çoklu küme)](../standard-library/set-operators.md#op_eq_eq_multiset)|İşlecin sol tarafındaki küme veya çoklu küme nesnesinin, sağ taraftaki küme veya çok kümeli nesneye eşit olup olmadığını sınar.|
|[işleç > (küme)](../standard-library/set-operators.md#op_gt)|[işleç > (çoklu küme)](../standard-library/set-operators.md#op_gt_multiset)|İşlecin sol tarafındaki küme veya çok kümeli nesne sağ taraftaki küme veya çok kümeli nesneden büyükse test eder.|
|[işleç > = (küme)](../standard-library/set-operators.md#op_gt_eq)|[işleç > = (çoklu küme)](../standard-library/set-operators.md#op_gt_eq_multiset)|İşlecin sol tarafındaki küme veya çoklu küme nesnesinin, sağ taraftaki küme veya çok kümeli bir nesneden büyük veya ona eşit olup olmadığını sınar.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Sürümü ayarla|Çoklu küme sürümü|Açıklama|
|-|-|-|
|[Kur](../standard-library/set-functions.md#swap)|[takas (çoklu küme)](../standard-library/set-functions.md#swap_multiset)|İki kümenin veya birden çok kümenin öğelerini değiş tokuş eder.|

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[set Sınıfı](../standard-library/set-class.md)|İçerdiği öğelerin değerlerinin benzersiz olduğu ve verilerin otomatik olarak sıralandığı anahtar değerleri olarak kullanıldığı bir koleksiyondan verilerin depolanması ve alınması için kullanılır.|
|[multiset Sınıfı](../standard-library/multiset-class.md)|İçerdiği öğelerin değerlerinin benzersiz olmaması ve verilerin otomatik olarak sıralandığı değere göre anahtar değerler olarak kullandıkları bir koleksiyondan verilerin depolanması ve alınması için kullanılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md) \
[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
