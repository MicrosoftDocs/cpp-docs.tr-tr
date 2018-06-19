---
title: Kapsam kuralları özeti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- class scope [C++], rules
- classes [C++], scope
- class names [C++], scope rules
- names [C++], class
- scope [C++], class names
ms.assetid: 47e26482-0111-466f-b857-598c15d05105
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d901103f36493e74f73b2edb18faa1188e704ef
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32423876"
---
# <a name="summary-of-scope-rules"></a>Kapsam Kuralları Özeti
Bir ad kullanımı (aşırı yükün belirlendiği noktaya kadar) kendi kapsamı içinde benzersiz olmalıdır. Bir işlev adı gösterir işlevi sayısı ve türü parametrelerinin göre benzersiz olması gerekir. Ad anlaşılır, kalırsa [üye erişimi](../cpp/member-access-control-cpp.md) kuralları uygulanır.  
  
## <a name="constructor-initializers"></a>Oluşturucu başlatıcıları  
 Oluşturucu başlatıcıları (açıklanan [başlatma tabanları ve üyeleri](http://msdn.microsoft.com/en-us/2f71377e-2b6b-49da-9a26-18e9b40226a1)) hangi için bunlar belirtilen Oluşturucusu dıştaki bloğunu kapsamında değerlendirilir. Bu nedenle, bunlar Oluşturucusu ait parametre adları kullanabilirsiniz.  
  
## <a name="global-names"></a>Genel adlar  
 İse veya herhangi bir işlev veya sınıf dışında sunulan genel birli kapsam işleciyle önekli bir nesne, işlev veya numaralandırıcı genel adıdır (`::`), ve bu ikili işleçler biriyle birlikte kullanılmıyorsa:  
  
-   Kapsam çözümü (`::`)  
  
-   Nesneleri ve başvuruları için üye seçimi (**.**)  
  
-   İşaretçileri için üye seçimi (**->**)  
  
## <a name="qualified-names"></a>Nitelikli adlar  
 İkili kapsam çözümleme işleciyle kullanılan adlara (`::`) "nitelenmiş adlar" denir. İkili kapsam çözümleme işlecinden sonra belirtilen ad, işlecin solunda belirtilen sınıfın üyesi veya temel sınıfının üyesi olmalıdır.  
  
 Üye seçim işleci sonra belirtilen adları (**.** veya **->**) işlecinin sol veya onun temel sınıfları üyeleri belirtilen nesnenin sınıf türü üyeleri olmalıdır. Üye seçim işlecinin sağ tarafta belirtilen adları (**->**) nesneler de olabilir sol tarafında sağlanan başka bir sınıf türü **->** bir sınıf nesnesi ve sınıfı bir aşırı yüklenmiş üye seçimi işleç tanımlar (**->**) başka bir sınıf türü için bir işaretçi için değerlendirir. (Bu sağlama daha ayrıntılı olarak ele alınmıştır [sınıf üye erişimi](../cpp/member-access.md).)  
  
 Derleyici, aşağıdaki sırayı kullanarak ve ad bulunduğunda durarak adları arar:  
  
1.  Ad bir işlev içerisinde kullanılırsa geçerli blok kapsamı; aksi takdirde, genel kapsam.  
  
2.  (İşlev parametreleri içeren) dış işlev kapsamı dahil olmak üzere her kapsayan blok kapsamı aracılığıyla dışa.  
  
3.  Ad üye işlevinin içerisinde kullanılırsa, sınıfın kapsamında ad aranır.  
  
4.  Sınıfın temel sınıflarında ad aranır.  
  
5.  Kapsayan iç içe geçmiş sınıf kapsamı (varsa) ve temelleri aranır. Arama, en dıştaki kapsayan sınıf kapsamı aranana dek devam eder.  
  
6.  Genel kapsam aranır.  
  
 Bununla birlikte, bu arama sırasında aşağıdaki gibi değişiklikler yapabilirsiniz:  
  
1.  Öncesinde `::` olan adlar, aramayı genel bir kapsamdan başlamaya zorlar.  
  
2.  Adları öncesinde tarafından **sınıfı**, `struct`, ve **UNION** anahtar sözcükler yalnızca aramak için derleyici zorla **sınıfı**, `struct`, veya **birleşimi**  adları.  
  
3.  Kapsam çözümü işleci sol tarafındaki adları (`::`) yalnızca **sınıfı**, `struct`, **ad alanı**, veya **UNION** adları.  
  
 Ad statik olmayan bir üyeye başvuruyor, ancak statik üye işlevinde kullanılıyorsa, bir hata iletisi oluşturulur. Adı herhangi bir statik olmayan üye kapsayan bir sınıf olarak başvuruyorsa, ekteki sınıfları kapsayan sınıfı olmadığı için benzer şekilde, bir hata iletisi oluşturulur **bu** işaretçileri.  
  
## <a name="function-parameter-names"></a>İşlev parametre adları  
 İşlev tanımları işlevi parametre adları işlevinin en dıştaki blok kapsamında olduğu kabul edilir. Bu nedenle, bunlar yerel adlardır ve işlevden çıkıldığında kapsam dışı olur.  
  
 İşlev bildirimleri (prototipleri) işlevi parametre adları yerel bildirimi kapsamındaki ve bildirimi sonunda kapsam dışına.  
  
 Varsayılan parametreler, önceki iki paragrafta açıklanan varsayılan oldukları parametre kapsamında bağlıdır. Bununla birlikte, bunlar yerel değişkenlere veya statik olmayan sınıf üyelerine erişemez. Varsayılan parametreleri noktasında işlev çağrısı değerlendirilir, ancak işlev bildirimi 's özgün kapsamında değerlendirilir. Bu nedenle, üye işlevleri için varsayılan parametreleri her zaman sınıfı kapsamında değerlendirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devralma](../cpp/inheritance-cpp.md)