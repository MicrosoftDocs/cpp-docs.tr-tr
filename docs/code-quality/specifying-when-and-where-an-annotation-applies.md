---
title: Açıklamanın Ne Zaman ve Nereye Uygulanacağını Belirtme
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _Group_
- _At_
- _When_
- _At_buffer_
ms.assetid: 8e4f4f9c-5dfa-4835-87df-ecd1698fc650
ms.openlocfilehash: af1f5a454659cad6584d63b5de23223f27170198
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77418755"
---
# <a name="specifying-when-and-where-an-annotation-applies"></a>Açıklamanın Ne Zaman ve Nereye Uygulanacağını Belirtme

Ek açıklama koşullu olduğunda, çözümleyiciye belirtmek için diğer ek açıklamalar gerekebilir.  Örneğin, bir işlevin zaman uyumlu veya zaman uyumsuz olabilecek bir değişkeni varsa, işlev şu şekilde davranır: zaman uyumlu durumda, her zaman başarılı olur, ancak zaman uyumsuz durumda, hemen başarısız olmazsa bir hata bildirir. İşlev zaman uyumlu olarak çağrıldığında, sonuç değerinin denetlenmesi, döndürülmeyeceği için kod Çözümleyicisi 'ne değer vermez.  Ancak, işlev zaman uyumsuz olarak çağrıldığında ve işlev sonucu denetlenirse, ciddi bir hata oluşabilir. Bu örnekte, denetlemeyi etkinleştirmek için, bu makalede daha sonra açıklanan `_When_` ek açıklamasını kullanabileceğiniz bir durum gösterilmektedir.

## <a name="structural-annotations"></a>Yapısal ek açıklamaları

Ek açıklamaların ne zaman ve nerede uygulanacağını denetlemek için aşağıdaki yapısal ek açıklamaları kullanın.

|Ek Açıklama|Açıklama|
|----------------|-----------------|
|`_At_(expr, anno-list)`|`expr`, lvalue veren bir ifadedir. `anno-list` ek açıklamalar `expr`tarafından adlandırılan nesneye uygulanır. `expr` `anno-list`içindeki her ek açıklama için, ek açıklamanın ön koşul olarak yorumlanması durumunda ve ek açıklama koşul sonrası olarak yorumlandığında koşul sonrası olarak yorumlanır.|
|`_At_buffer_(expr, iter, elem-count, anno-list)`|`expr`, lvalue veren bir ifadedir. `anno-list` ek açıklamalar `expr`tarafından adlandırılan nesneye uygulanır. `expr` `anno-list`içindeki her ek açıklama için, ek açıklamanın ön koşul olarak yorumlanması durumunda ve ek açıklamanın koşul sonrası yorumlanması durumunda koşul sonrası olarak yorumlanır.<br /><br /> `iter`, ek açıklamanın kapsamına alınmış bir değişkenin adıdır (`anno-list`dahil). `iter` örtük bir tür `long`sahip. Herhangi bir kapsayan kapsamda aynı adlandırılmış değişkenler değerlendirmeden gizlenir.<br /><br /> `elem-count`, bir tamsayı değerlendiren bir ifadedir.|
|`_Group_(anno-list)`|`anno-list` ek açıklamaların hepsi, her ek açıklamaya uygulanan Grup ek açıklaması için geçerli olan herhangi bir niteleyiciye sahip olarak kabul edilir.|
|`_When_(expr, anno-list)`|`expr`, `bool`dönüştürülebileceği bir ifadedir. Sıfır olmayan (`true`) olduğunda, `anno-list` belirtilen ek açıklamalar geçerli kabul edilir.<br /><br /> Varsayılan olarak, `anno-list`her ek açıklama için, ek açıklama bir önkoşulun ise ve ek açıklama bir koşul ise çıktı değerlerini kullanarak, `expr` giriş değerlerini kullanma olarak yorumlanır. Varsayılan değeri geçersiz kılmak için, giriş değerlerinin kullanılması gerektiğini göstermek üzere bir koşulu değerlendirirken `_Old_` iç öğesini kullanabilirsiniz. **Note:**  Farklı ek açıklamalar `*pLength``_When_` kullanmanın bir sonucu olarak etkinleştirilebilir, çünkü önkoşuldaki `expr` sonucu, koşul sonrası tarafından değerlendirilen sonuçtan farklı olabilir.|

## <a name="see-also"></a>Ayrıca bkz.

- [C/C++ Kod Hatalarını Azaltmak için SAL Ek Açıklamalarını Kullanma](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [SAL'yi Anlama](../code-quality/understanding-sal.md)
- [İşlev Parametrelerini ve Dönüş Değerlerini Açıklama](../code-quality/annotating-function-parameters-and-return-values.md)
- [İşlev Davranışını Yorumlama](../code-quality/annotating-function-behavior.md)
- [Yapıları ve Sınıfları Yorumlama](../code-quality/annotating-structs-and-classes.md)
- [Kilitlenme Davranışını Yorumlama](../code-quality/annotating-locking-behavior.md)
- [İç İşlevler](../code-quality/intrinsic-functions.md)
- [En İyi Yöntemler ve Örnekler](../code-quality/best-practices-and-examples-sal.md)
