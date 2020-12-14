---
description: 'Daha fazla bilgi edinin: öncelik ve değerlendirme sırası'
title: Öncelik ve değerlendirme sırası
ms.date: 07/11/2019
helpviewer_keywords:
- associativity of operators [C++]
- precedence [C++], operators
- data binding [C++], operator precedence
- operators [C++], precedence
ms.assetid: 201f7864-0c51-4c55-9d6f-39c5d013bcb0
ms.openlocfilehash: 2e0046b8fefab99c29ac9c47322b7547ec573e63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312442"
---
# <a name="precedence-and-order-of-evaluation"></a>Öncelik ve değerlendirme sırası

C işleçlerinin öncelik ve birleşimleri, ifadelerde işlenenlerin gruplandırılmasını ve değerlendirilmesini etkiler. Bir işlecin önceliği, daha yüksek veya daha düşük önceliğe sahip başka işleçler varsa bir anlam ifade eder. Önce daha yüksek önceliğe sahip işleçler değerlendirilir. Öncelik, "bağlama" sözcüğüyle de açıklanabilir. Daha yüksek önceliğe sahip işleçlerin daha sıkı bağlamaya sahip olduğu söylenir.

Aşağıdaki tabloda, C işleçlerinin öncelik ve ilişkilendirilebilirliği (işlenenlerin değerlendirilme sırası) özetlenmekte ve öncelikleri en yüksekten en düşüğe listelenmektedir. Birkaç işlecin birlikte göründüğü yerlerde, bu işleçler aynı önceliğe sahip olur ve ilişkilendirilebilirliklerine göre değerlendirilir. Tablodaki işleçler, [sonek işleçleriyle](../c-language/postfix-operators.md)başlayan bölümlerde açıklanmıştır. Bu bölümün geri kalanında, öncelik ve ilişkilendirilebilirlik hakkında genel bilgiler verilmektedir.

## <a name="precedence-and-associativity-of-c-operators"></a>C işleçlerinin önceliği ve ilişkilendirilebilirliği

| Sembol <sup>1</sup> | İşlem türü | İlişkilendirilebilirlik |
|-------------|-----------------------|-------------------|
| `[` `]` `(` `)` `.` `->`<br/>`++``--`(sonek) | Expression | Soldan sağa |
| **`sizeof`** `&` `*` `+` `-` `~` `!`<br/>`++``--`(ön ek) | Birli | Sağdan sola |
| *tür atamaları* | Birli | Sağdan sola |
| `*` `/` `%` | Çarpımsal | Soldan sağa |
| `+` `-` | Toplamsal | Soldan sağa |
| `<<` `>>` | Bit düzeyinde kaydırma | Soldan sağa |
| `<` `>` `<=` `>=` | İlişkisel | Soldan sağa |
| `==` `!=` | Eşitlik | Soldan sağa |
| `&` | Bit düzeyinde AND | Soldan sağa |
| `^` | Bit düzeyinde dışlamalı OR | Soldan sağa |
| `|` | Bit düzeyinde kapsamalı OR | Soldan sağa |
| `&&` | Mantıksal AND | Soldan sağa |
| `||` | Mantıksal OR | Soldan sağa |
| `? :` | Koşullu ifade | Sağdan sola |
| `=` `*=` `/=` `%=`<br/>`+=` `-=` `<<=` `>>=` `&=`<br/>`^=` `|=` | Basit ve bileşik atama <sup>2</sup> | Sağdan sola |
| `,` | Sıralı değerlendirme | Soldan sağa |

<sup>1</sup> işleçler azalan öncelik sırasıyla listelenmiştir. Aynı satırda veya grupta birkaç işleç görünüyorsa, bunlar eşit önceliğe sahip olur.

<sup>2</sup> tüm basit ve bileşik atama işleçleri eşit önceliğe sahiptir.

Bir ifade eşit önceliğe sahip birkaç işleç içerebilir. Böyle birkaç işleç bir ifadede aynı düzeyde göründüğünde, değerlendirme işlecin ilişkilendirilebilirliğine göre sağdan sola veya soldan sağa devam eder. Değerlendirmenin yönü, aynı düzeyde birden fazla çarpma ( `*` ), toplama ( `+` ) veya ikili bit düzeyinde ( `&` , `|` , veya `^` ) işleç içeren ifadelerin sonuçlarını etkilemez. İşlemlerin sırası dil tarafından tanımlanmaz. Derleyici, tutarlı bir sonuç sağladığı sürece bu tür ifadeleri herhangi bir sırada değerlendirebilir.

Yalnızca sıralı değerlendirme ( `,` ), mantıksal-ve ( `&&` ), mantıksal OR () `||` , koşullu ifade ( `? :` ) ve işlev çağrısı işleçleri dizi noktaları oluşturur ve bu nedenle kendi işlenenleri için belirli bir değerlendirme sırası garantisi. İşlev çağrısı işleci, işlev tanımlayıcısının arkasından gelen bir parantezler kümesidir. Sıralı değerlendirme operatörü (), `,` İşlenenlerini soldan sağa değerlendirmek için garanti edilir. (Bir işlev çağrısındaki virgül işleci, sıralı değerlendirme işleciyle aynı değil ve böyle bir garanti sağlamıyor.) Daha fazla bilgi için bkz. [dizi noktaları](c-sequence-points.md).

Mantıksal işleçler de işlenenlerinin soldan sağa değerlendirilmesini garanti eder. Bununla birlikte, ifadenin sonucunu belirlemek için gereken en az sayıda işleneni değerlendirirler. Buna "kısa devre" değerlendirmesi adı verilir. Bu nedenle, ifadenin bazı işlenenleri değerlendirilmeyebilir. Örneğin, ifadede

`x && y++`

ikinci işlenen `y++`, yalnızca `x` true (sıfırdan farklı) olduğunda değerlendirilir. Bu nedenle, `y``x` yanlış (0) olduğunda artmaz.

## <a name="examples"></a>Örnekler

Aşağıdaki listede, derleyicinin bazı örnek ifadeleri otomatik olarak nasıl bağladığı gösterilmektedir:

| Expression | Otomatik Bağlama |
|----------------|-----------------------|
| `a & b || c` | `(a & b) || c` |
| `a = b || c` | `a = (b || c)` |
| `q && r || s--` | `(q && r) || s--` |

İlk ifadede, bit düzeyinde AND işleci (`&`), mantıksal OR işlecine (`||`) göre daha yüksek bir önceliğe sahiptir, bu nedenle `a & b` mantıksal OR işleminin ilk işlenenini oluşturur.

İkinci ifadede, mantıksal OR işleci (`||`) basit atama işlecine (`=`) göre daha yüksek bir önceliğe sahiptir, bu nedenle `b || c` atamada sağ işlenen olarak gruplandırılır. `a`'ya atanan değerin 0 veya 1 olduğuna dikkat edin.

Üçüncü ifade, beklenmedik bir sonuç oluşturabilecek doğru bir şekilde biçimlendirilmiş bir ifadeyi gösterir. Mantıksal AND işleci (`&&`), mantıksal OR işlecine (`||`) göre daha yüksek bir önceliğe sahiptir, bu nedenle `q && r` bir işlenen olarak gruplandırılır. Mantıksal işleçler işlenenlerin soldan sağa değerlendirilmesini garanti altına aldığı için, daha `q && r` önce değerlendirilir `s--` . Ancak, `q && r` sıfır dışında bir değer olarak değerlendirilirse, `s--` değerlendirilmez ve `s` azaltılır. `s`Azaltılanmayacaksa, programınızda bir sorun oluşmasına neden olur, `s--` ifadenin ilk işleneni olarak görünmelidir veya `s` ayrı bir işlemde küçültülüyor olmalıdır.

Aşağıdaki ifade geçersizdir ve derleme zamanında bir tanılama iletisi oluşturur:

| Geçersiz İfade | Varsayılan Gruplandırma |
|------------------------|----------------------|
| `p == 0 ? p += 1: p += 2` | `( p == 0 ? p += 1 : p ) += 2` |

Bu ifadede, eşitlik işleci (`==`) en yüksek önceliğe sahiptir, bu nedenle `p == 0` bir işlenen olarak gruplandırılır. Koşullu ifade işleci (`? :`) sonraki en yüksek önceliğe sahiptir. İlk işleneni `p == 0`, ikinci işleneni ise `p += 1`'dir. Ancak, koşullu ifade işlecinin son işleneni `p` yerine `p += 2` olarak kabul edilir; çünkü bu `p` örneği koşullu ifade işlecine, bileşik atama işlecine göre daha yakından bağlanır. `+= 2` sol işlenene sahip olmadığı için bir sözdizimi hatası oluşur. Bu türden hataları önlemek ve daha okunabilir bir kod oluşturmak için parantez kullanmanız gerekir. Örneğin, yukarıdaki örneği düzeltmek ve netleştirmek için parantezleri aşağıda gösterildiği gibi kullanabilirsiniz:

`( p == 0 ) ? ( p += 1 ) : ( p += 2 )`

## <a name="see-also"></a>Ayrıca bkz.

[C işleçleri](c-operators.md)
