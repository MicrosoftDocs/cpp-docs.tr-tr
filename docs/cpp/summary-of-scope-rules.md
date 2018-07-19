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
ms.openlocfilehash: 2ce7c57688fae22c3bba844cff480ae3aec03785
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39028144"
---
# <a name="summary-of-scope-rules"></a>Kapsam Kuralları Özeti
Bir ad kullanımı (aşırı yükün belirlendiği noktaya kadar) kendi kapsamı içinde benzersiz olmalıdır. Ad bir işlevi gösteriyorsa, işlev numarası ve parametre türüne göre benzersiz olmalıdır. Adı kalırsa, [üye erişimi](../cpp/member-access-control-cpp.md) kuralları uygulanır.  
  
## <a name="constructor-initializers"></a>Oluşturucu başlatıcıları  
 Oluşturucu başlatıcıları (açıklanan [başlatma tabanları ve üyeleri](http://msdn.microsoft.com/2f71377e-2b6b-49da-9a26-18e9b40226a1)) için bunlar belirtilir oluşturucunun en dıştaki bloğunun kapsamında değerlendirilir. Bu nedenle oluşturucunun parametre adları kullanabilirler.  
  
## <a name="global-names"></a>Genel adlar  
 Herhangi bir işlev veya sınıf dışında sunulan veya genel birli kapsam işleciyle önekli bir nesne, işlev veya numaralandırıcı adı genel ise (`::`), ve bu ikili işleçlerde biriyle birlikte kullanılmıyorsa:  
  
-   Kapsam çözümleme (`::`)  
  
-   Nesneleri ve başvurular için üye seçimi (**.**)  
  
-   Üye seçimi işaretçileri (**->**)  
  
## <a name="qualified-names"></a>Nitelikli adlar  
 İkili kapsam çözümleme işleciyle kullanılan adlara (`::`) "nitelenmiş adlar" denir. İkili kapsam çözümleme işlecinden sonra belirtilen ad, işlecin solunda belirtilen sınıfın üyesi veya temel sınıfının üyesi olmalıdır.  
  
 Üye seçme işlecinden sonra belirtilen adlar (**.** veya **->**) işlecinin sol veya temel sınıfının üyesi belirtilen nesnenin sınıf türünün üyeleri olmalıdır. Belirtilen üye seçme işleci sağ tarafındaki adlar (**->**) nesneleri de olabilir sol tarafında, başka bir sınıf türünde sağlanan **->** bir sınıf nesnesi ve sınıfı aşırı yüklenmiş üye seçme işleci tanımlar (**->**) olarak değerlendirilen başka bir sınıf türü işaretçisi. (Bu sağlama daha ayrıntılı olarak ele alınan [sınıfın üyesi erişimi](../cpp/member-access.md).)  
  
 Derleyici, aşağıdaki sırayı kullanarak ve ad bulunduğunda durarak adları arar:  
  
1.  Ad bir işlev içerisinde kullanılırsa geçerli blok kapsamı; aksi takdirde, genel kapsam.  
  
2.  Aracılığıyla en dıştaki işlev kapsamı (işlev parametreleri içeren) dahil olmak üzere her kapsayan blok kapsamına dışa.  
  
3.  Ad üye işlevinin içerisinde kullanılırsa, sınıfın kapsamında ad aranır.  
  
4.  Sınıfın temel sınıflarında ad aranır.  
  
5.  Kapsayan iç içe geçmiş sınıf kapsamı (varsa) ve temelleri aranır. Arama, en dıştaki kapsayan sınıf kapsamı aranana dek devam eder.  
  
6.  Genel kapsam aranır.  
  
 Bununla birlikte, bu arama sırasında aşağıdaki gibi değişiklikler yapabilirsiniz:  
  
1.  Öncesinde `::` olan adlar, aramayı genel bir kapsamdan başlamaya zorlar.  
  
2.  Adları öncesinde **sınıfı**, **yapı**, ve **birleşim** anahtar sözcükler, sistemi, yalnızca aramak için derleyiciyi **sınıfı**,  **Yapı**, veya **birleşim** adları.  
  
3.  Kapsam çözümleme işlecinin sol tarafındaki adlar (`::`) yalnızca **sınıfı**, **yapı**, **ad alanı**, veya **birleşim**adları.  
  
 Ad statik olmayan bir üyeye başvuruyor, ancak statik üye işlevinde kullanılıyorsa, bir hata iletisi oluşturulur. Ad kapsayan sınıfta statik olmayan bir üye başvuruyorsa, kapsayan sınıflarda kapsayan sınıf olmadığı için benzer şekilde, bir hata iletisi oluşturulur **bu** işaretçileri.  
  
## <a name="function-parameter-names"></a>İşlev parametre adları  
 İşlev tanımlarındaki işlev parametre adları, işlevin en dıştaki bloğun kapsamında olacak şekilde değerlendirilir. Bu nedenle, bunlar yerel adlardır ve işlevden çıkıldığında kapsam dışı olur.  
  
 İşlev bildirimlerindeki (prototipler) işlev parametre adları bildirimin yerel kapsamı içinde olan ve bildirim sonunda kapsam dışına.  
  
 Varsayılan parametreler parametrenin varsayılan oldukları iki önceki paragrafta açıklandığı gibi kapsamındaki. Bununla birlikte, bunlar yerel değişkenlere veya statik olmayan sınıf üyelerine erişemez. Varsayılan parametreleri işlev çağrısı noktasında değerlendirilir, ancak bunlar işlev bildiriminin orijinal kapsamında değerlendirilir. Bu nedenle, üye işlevleri için varsayılan parametreleri her zaman sınıf kapsamında değerlendirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devralma](../cpp/inheritance-cpp.md)