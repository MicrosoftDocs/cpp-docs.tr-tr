---
title: Kapsam Kuralları Özeti
ms.date: 11/04/2016
helpviewer_keywords:
- class scope [C++], rules
- classes [C++], scope
- class names [C++], scope rules
- names [C++], class
- scope [C++], class names
ms.assetid: 47e26482-0111-466f-b857-598c15d05105
ms.openlocfilehash: 1f8b79c637662d79051b72e6aabefc99c450bdc5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160885"
---
# <a name="summary-of-scope-rules"></a>Kapsam Kuralları Özeti

Bir ad kullanımı (aşırı yükün belirlendiği noktaya kadar) kendi kapsamı içinde benzersiz olmalıdır. Ad bir işlevi ifade eder, işlev sayı ve parametre türüne göre belirsiz olmalıdır. Ad belirsiz kalırsa, [üye erişim](../cpp/member-access-control-cpp.md) kuralları uygulanır.

## <a name="constructor-initializers"></a>Oluşturucu başlatıcıları

[Oluşturucu başlatıcıları](constructors-cpp.md#member_init_list) , belirtilen oluşturucunun en dıştaki bloğunun kapsamında değerlendirilir. Bu nedenle, oluşturucunun parametre adlarını kullanabilirler.

## <a name="global-names"></a>Genel adlar

Bir nesne, işlev veya Numaralandırıcı, herhangi bir işlev veya sınıf dışında veya genel birli kapsam operatörü (`::`) tarafından önek olarak kullanılırsa ve bu ikili işleçlerden herhangi biri ile birlikte kullanılmazsa genel bir addır:

- Kapsam çözünürlüğü (`::`)

- Nesneler ve başvurular için üye seçimi ( **.** )

- İşaretçiler için üye seçimi ( **->** )

## <a name="qualified-names"></a>Nitelikli adlar

İkili kapsam çözümleme işleciyle kullanılan adlara (`::`) "nitelenmiş adlar" denir. İkili kapsam çözümleme işlecinden sonra belirtilen ad, işlecin solunda belirtilen sınıfın üyesi veya temel sınıfının üyesi olmalıdır.

Üye seçim işlecinden sonra belirtilen adlar ( **.** ya da **->** ), işlecin solunda belirtilen nesnenin sınıf türünün üyesi veya temel sınıfının üyeleri olmalıdır. Üye seçim işlecinin ( **->** ) sağında belirtilen adlar, **->** sol tarafı bir sınıf nesnesi ve sınıfın başka bir sınıf türüne yönelik bir işaretçi olarak değerlendirilen aşırı yüklenmiş bir üye seçme işleci ( **->** ) tanımladığından başka bir sınıf türünün nesneleri de olabilir. (Bu sağlama, [sınıf üyesi erişimi](../cpp/member-access.md)bölümünde daha ayrıntılı bir şekilde ele alınmıştır.)

Derleyici, aşağıdaki sırayı kullanarak ve ad bulunduğunda durarak adları arar:

1. Ad bir işlev içerisinde kullanılırsa geçerli blok kapsamı; aksi takdirde, genel kapsam.

1. En dıştaki işlev kapsamı (işlev parametreleri içerir) dahil olmak üzere, kapsayan her bir blok kapsamı üzerinden dışa doğru.

1. Ad üye işlevinin içerisinde kullanılırsa, sınıfın kapsamında ad aranır.

1. Sınıfın temel sınıflarında ad aranır.

1. Kapsayan iç içe geçmiş sınıf kapsamı (varsa) ve temelleri aranır. Arama, en dıştaki kapsayan sınıf kapsamı aranana dek devam eder.

1. Genel kapsam aranır.

Bununla birlikte, bu arama sırasında aşağıdaki gibi değişiklikler yapabilirsiniz:

1. Öncesinde `::` olan adlar, aramayı genel bir kapsamdan başlamaya zorlar.

1. **Sınıf**, **Yapı**ve **birleşim** anahtar kelimeleri tarafından önlenen adlar derleyicinin yalnızca **sınıf**, **Yapı**veya **birleşim** adlarını aramasına izin vermez.

1. Kapsam çözümleme işlecinin (`::`) sol tarafındaki adlar yalnızca **sınıf**, **Yapı**, **ad alanı**veya **birleşim** adları olabilir.

Ad statik olmayan bir üyeye başvuruyor, ancak statik üye işlevinde kullanılıyorsa, bir hata iletisi oluşturulur. Benzer şekilde, ad kapsayan bir sınıftaki herhangi bir statik olmayan üyeye başvuruyorsa, kapsanan sınıfların **Bu** işaretçileri kapsayan sınıf içerdiği için bir hata iletisi oluşturulur.

## <a name="function-parameter-names"></a>İşlev parametresi adları

İşlev tanımlarındaki işlev parametresi adları, işlevin en dıştaki bloğunun kapsamında olduğu kabul edilir. Bu nedenle, bunlar yerel adlardır ve işlevden çıkıldığında kapsam dışı olur.

İşlev bildirimlerinde işlev parametresi adları (prototürler) bildirimin yerel kapsamındadır ve bildirimin sonundaki kapsam dışına çıkar.

Varsayılan parametreler, önceki iki paragrafta açıklandığı gibi varsayılan oldukları parametre kapsamıdır. Bununla birlikte, bunlar yerel değişkenlere veya statik olmayan sınıf üyelerine erişemez. Varsayılan parametreler, işlev çağrısının noktasında değerlendirilir, ancak işlev bildiriminin orijinal kapsamında değerlendirilir. Bu nedenle, üye işlevleri için varsayılan parametreler her zaman sınıf kapsamında değerlendirilir.

## <a name="see-also"></a>Ayrıca bkz.

[Devralma](../cpp/inheritance-cpp.md)
