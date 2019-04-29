---
title: Ad Alanları
ms.date: 11/04/2016
helpviewer_keywords:
- union keyword [C], tags
- enumeration tags
- structure tags
- names [C++], declared elements
- name spaces [C++]
- tags, structure tags
- union keyword [C]
ms.assetid: b4bda1d1-cb5e-4f60-ac2b-29af93d8a9a2
ms.openlocfilehash: 76ad9b797a4f192e8f22f8c040f5a308371a461b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325773"
---
# <a name="name-spaces"></a>Ad Alanları

"Ad alanları" derleyici ayarlar farklı türlerde öğeler için kullanılan tanımlayıcıları ayırt etmek için. Her ad alanı içinde adları çakışmayı önlemek için benzersiz olmalıdır, ancak aynı ada birden fazla ad alanı içinde görünebilir. Öğeleri farklı bir ad boşluk olması koşuluyla bu iki veya daha fazla farklı öğeler için aynı tanımlayıcıyı kullanabileceğiniz anlamına gelir. Derleyici program tanımlayıcıda söz dizimi bağlamında dayalı başvuruları çözebilirsiniz.

> [!NOTE]
> Bir ad alanı C++ "ad" özelliği ile sınırlı C kavramı karıştırmayın. Bkz: [ad alanları](../cpp/namespaces-cpp.md) daha fazla bilgi için C++ dil başvurusu.

Bu liste C'de kullanılan ad alanları açıklar.

Deyim etiketleri adlandırılmış deyim etiketleri deyimleri bir parçasıdır. Deyim etiketleri tanımları her zaman bir iki nokta üst üste ancak parçası değildir tarafından izlenen **çalışması** etiketler. Hemen izleyin anahtar sözcüğü her zaman deyim etiketleri kullanımları **goto**. Deyim etiketleri diğer adlarını veya diğer işlevlerinde etiket adları benzersiz olması gerekmez.

Yapı, birleşim ve numaralandırma etiketleri bu etiketleri yapı, birleşim ve numaralandırma tür tanımlayıcıları parçasıdır ve, varsa, ayrılmış sözcükler her zaman hemen izleyin **yapı**, **birleşim**, veya **enum**. Etiket adları tüm diğer yapısı, sabit listesi ya da aynı görünürlük birleşim etiketlerle farklı olmalıdır.

Üyeleri yapıları veya birleşimler üye adları, her yapı ve birleşim türü ile ilişkili ad alanları ayrılır. Diğer bir deyişle, aynı tanımlayıcıyı aynı anda yapıları veya birleşimler sayısında herhangi bir bileşen adı olabilir. Bileşen adlarına tanımlarını, yapı veya birleşim türü belirticisi içinde her zaman oluşur. Bileşen adlarına her zaman kullanımları üye seçim işleçleri hemen izleyin (**->** ve **.**). Bir üyenin adını yapı veya birleşim içinde benzersiz olmalıdır, ancak farklı yapılar ve birleşimler, üye adlarını da dahil olmak üzere, programdaki diğer adları ya da yapının adını benzersiz olması gerekmez.

Sıradan tanımlayıcıları, diğer tüm adların değişkenler, İşlevler (biçimsel parametreler ve yerel değişkenler dahil) ve numaralandırma sabitlerini içeren bir ad alanı ayrılır. Tanımlayıcı adları içinde blok tanımlayabilirsiniz böylece görünürlük, iç içe.

TypeDef adları Typedef adları aynı kapsamda tanımlayıcı olarak kullanılamaz.

Örneğin, yapı etiketleri, Yapı üyeleri ve değişken adları üç farklı bir ad alanı olduğundan, üç öğeye adlı `student` Bu örnekte çakışmasını. Her bir öğenin bağlam her geçtiği doğru yorumlanması izin `student` programı. (Yapıları hakkında daha fazla bilgi için bkz: [yapı bildirimleri](../c-language/structure-declarations.md).)

```C
struct student {
   char student[20];
   int class;
   int id;
   } student;
```

Zaman `student` sonra görünen **yapı** anahtar sözcüğü, derleyiciye tanır, yapısı etiket olarak. Zaman `student` üye seçme işlecinden sonra görünür (**->** veya **.**), yapı üyesine adıdır. Diğer bağlamlarda `student` yapısı değişkenine başvuruyor. Anlamı gizler beri ancak etiket ad alanı aşırı önerilmez.

## <a name="see-also"></a>Ayrıca bkz.

[Program Yapısı](../c-language/program-structure.md)
