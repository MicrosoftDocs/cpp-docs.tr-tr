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
ms.openlocfilehash: af708fd72904fb775ff1088948972bec159816c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436094"
---
# <a name="summary-of-scope-rules"></a>Kapsam Kuralları Özeti

Bir ad kullanımı (aşırı yükün belirlendiği noktaya kadar) kendi kapsamı içinde benzersiz olmalıdır. Ad bir işlevi gösteriyorsa, işlev numarası ve parametre türüne göre benzersiz olmalıdır. Adı kalırsa, [üye erişimi](../cpp/member-access-control-cpp.md) kuralları uygulanır.

## <a name="constructor-initializers"></a>Oluşturucu başlatıcıları

[Oluşturucu başlatıcıları](constructors-cpp.md#member_init_list) için bunlar belirtilir oluşturucunun en dıştaki bloğunun kapsamında değerlendirilir. Bu nedenle oluşturucunun parametre adları kullanabilirler.

## <a name="global-names"></a>Genel adlar

Herhangi bir işlev veya sınıf dışında sunulan veya genel birli kapsam işleciyle önekli bir nesne, işlev veya numaralandırıcı adı genel ise (`::`), ve bu ikili işleçlerde biriyle birlikte kullanılmıyorsa:

- Kapsam çözümleme (`::`)

- Nesneleri ve başvurular için üye seçimi (**.**)

- Üye seçimi işaretçileri (**->**)

## <a name="qualified-names"></a>Nitelikli adlar

İkili kapsam çözümleme işleciyle kullanılan adlara (`::`) "nitelenmiş adlar" denir. İkili kapsam çözümleme işlecinden sonra belirtilen ad, işlecin solunda belirtilen sınıfın üyesi veya temel sınıfının üyesi olmalıdır.

Üye seçme işlecinden sonra belirtilen adlar (**.** veya **->**) işlecinin sol veya temel sınıfının üyesi belirtilen nesnenin sınıf türünün üyeleri olmalıdır. Belirtilen üye seçme işleci sağ tarafındaki adlar (**->**) nesneleri de olabilir sol tarafında, başka bir sınıf türünde sağlanan **->** bir sınıf nesnesi ve sınıfı aşırı yüklenmiş üye seçme işleci tanımlar (**->**) olarak değerlendirilen başka bir sınıf türü işaretçisi. (Bu sağlama daha ayrıntılı olarak ele alınan [sınıfın üyesi erişimi](../cpp/member-access.md).)

Derleyici, aşağıdaki sırayı kullanarak ve ad bulunduğunda durarak adları arar:

1. Ad bir işlev içerisinde kullanılırsa geçerli blok kapsamı; aksi takdirde, genel kapsam.

1. Aracılığıyla en dıştaki işlev kapsamı (işlev parametreleri içeren) dahil olmak üzere her kapsayan blok kapsamına dışa.

1. Ad üye işlevinin içerisinde kullanılırsa, sınıfın kapsamında ad aranır.

1. Sınıfın temel sınıflarında ad aranır.

1. Kapsayan iç içe geçmiş sınıf kapsamı (varsa) ve temelleri aranır. Arama, en dıştaki kapsayan sınıf kapsamı aranana dek devam eder.

1. Genel kapsam aranır.

Bununla birlikte, bu arama sırasında aşağıdaki gibi değişiklikler yapabilirsiniz:

1. Öncesinde `::` olan adlar, aramayı genel bir kapsamdan başlamaya zorlar.

1. Adları öncesinde **sınıfı**, **yapı**, ve **birleşim** anahtar sözcükler, sistemi, yalnızca aramak için derleyiciyi **sınıfı**,  **Yapı**, veya **birleşim** adları.

1. Kapsam çözümleme işlecinin sol tarafındaki adlar (`::`) yalnızca **sınıfı**, **yapı**, **ad alanı**, veya **birleşim**adları.

Ad statik olmayan bir üyeye başvuruyor, ancak statik üye işlevinde kullanılıyorsa, bir hata iletisi oluşturulur. Ad kapsayan sınıfta statik olmayan bir üye başvuruyorsa, kapsayan sınıflarda kapsayan sınıf olmadığı için benzer şekilde, bir hata iletisi oluşturulur **bu** işaretçileri.

## <a name="function-parameter-names"></a>İşlev parametre adları

İşlev tanımlarındaki işlev parametre adları, işlevin en dıştaki bloğun kapsamında olacak şekilde değerlendirilir. Bu nedenle, bunlar yerel adlardır ve işlevden çıkıldığında kapsam dışı olur.

İşlev bildirimlerindeki (prototipler) işlev parametre adları bildirimin yerel kapsamı içinde olan ve bildirim sonunda kapsam dışına.

Varsayılan parametreler parametrenin varsayılan oldukları iki önceki paragrafta açıklandığı gibi kapsamındaki. Bununla birlikte, bunlar yerel değişkenlere veya statik olmayan sınıf üyelerine erişemez. Varsayılan parametreleri işlev çağrısı noktasında değerlendirilir, ancak bunlar işlev bildiriminin orijinal kapsamında değerlendirilir. Bu nedenle, üye işlevleri için varsayılan parametreleri her zaman sınıf kapsamında değerlendirilir.

## <a name="see-also"></a>Ayrıca bkz.

[Devralma](../cpp/inheritance-cpp.md)