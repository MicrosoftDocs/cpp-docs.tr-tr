---
title: Ad alanları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- union keyword [C], tags
- enumeration tags
- structure tags
- names [C++], declared elements
- name spaces [C++]
- tags, structure tags
- union keyword [C]
ms.assetid: b4bda1d1-cb5e-4f60-ac2b-29af93d8a9a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b0fe8a097da3de67d149665928524395988c730
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32390066"
---
# <a name="name-spaces"></a>Ad Alanları
"Ad alanları" derleyici ayarlar farklı türde öğe için kullanılan tanımlayıcıları ayırt etmek için. Her ad alanı içinde adları çakışmayı önlemek için benzersiz olmalıdır, ancak aynı adı birden fazla ad alanı görünebilir. Farklı ad alanlarında öğeleri olması koşuluyla iki veya daha fazla farklı öğeler için aynı tanımlayıcısı kullanabileceğiniz anlamına gelir. Derleyici program tanımlayıcıda söz dizimi bağlamında göre başvuruları çözebilirsiniz.  
  
> [!NOTE]
>  Bir ad alanı C++ "ad" özelliği ile sınırlı C kavramı karıştırmayın. Bkz: [ad alanları](../cpp/namespaces-cpp.md) c *++ dil başvurusu* daha fazla bilgi için.  
  
 Bu liste c dilinde kullanılan ad alanları açıklar  
  
 Deyimi etiketleri  
 Adlandırılmış deyimi etiketleri deyimleri bir parçasıdır. Deyimi etiketleri tanımları her zaman iki nokta üst üste ancak parçası olan tarafından izlenen **durumda** etiketler. Her zaman deyimi etiketleri kullanımlarını hemen anahtar sözcüğü izleyin `goto`. Deyimi etiketleri diğer adlarını veya diğer işlevleri etiket adları farklı olması gerekmez.  
  
 Yapısı, union ve numaralandırma etiketleri  
 Bu etiketler tür tanımlayıcıları yapısı, union ve numaralandırma parçası olan ve, varsa, her zaman hemen ayrılmış sözcükler izleyin `struct`, **UNION**, veya `enum`. Etiket adları tüm diğer yapısı, numaralandırma veya aynı görünürlük birleşim etiketleriyle farklı olması gerekir.  
  
 Yapıları veya birleşimler üyeleri  
 Üye adlarının her yapı ve birleşim türü ile ilişkili ad alanları ayrılır. Diğer bir deyişle, aynı tanımlayıcısı aynı anda yapıları veya birleşimler herhangi bir sayıda bir bileşen adı olabilir. Bileşen adlarına tanımlarını yapısı veya birleşim türü tanımlayıcıları içinde her zaman oluşur. Her zaman bileşen adlarına kullanımlarını hemen üye seçim işleçleri izleyin (**->** ve **.**). Üyenin adını yapı veya birleşim içinde benzersiz olmalıdır, ancak farklı yapılar ve birleşimleri, üyelerin adları dahil olmak üzere bu programı başka bir adı ya da yapısı adı farklı olması gerekmez.  
  
 Sıradan tanımlayıcıları  
 Tüm diğer adları değişkenler, İşlevler (resmi parametreleri ve yerel değişkenleri dahil) ve numaralandırma sabitleri içeren bir ad alanı ayrılır. İçinde blok tanımlayabilirsiniz şekilde tanımlayıcı adları görünürlük, iç içe.  
  
 TypeDef adları  
 TypeDef adları aynı kapsamda tanımlayıcıları olarak kullanılamaz.  
  
 Yapı etiketleri, Yapı üyeleri ve değişken adları üç farklı ad alanlarında olduğundan, örneğin, üç öğe adlı `student` Bu örnekte çakışmasını. Bağlamın her öğenin her oluşumu doğru yorumu izin `student` programı. (Yapıları hakkında daha fazla bilgi için bkz: [yapı bildirimleri](../c-language/structure-declarations.md).)  
  
```  
struct student {  
   char student[20];  
   int class;  
   int id;  
   } student;  
```  
  
 Zaman `student` sonra görünen `struct` anahtar sözcüğü, derleyicisi tanır, yapısı etiketi olarak. Zaman `student` üye seçimi işlecinden sonra görüntülenir (**->** veya **.**), ad yapısı üyesine başvuruyor. Diğer bağlamlarda `student` yapısı değişkenine başvuruyor. Anlamı gizler beri ancak etiketi ad alanı aşırı önerilmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program Yapısı](../c-language/program-structure.md)