---
title: Öncelik ve değerlendirme sırası
ms.date: 07/11/2019
helpviewer_keywords:
- associativity of operators [C++]
- precedence [C++], operators
- data binding [C++], operator precedence
- operators [C++], precedence
ms.assetid: 201f7864-0c51-4c55-9d6f-39c5d013bcb0
ms.openlocfilehash: 327a5a5344f17f1d84e0cebc1371d56426c95deb
ms.sourcegitcommit: 0e3da5cea44437c132b5c2ea522bd229ea000a10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2019
ms.locfileid: "67861070"
---
# <a name="precedence-and-order-of-evaluation"></a>Öncelik ve değerlendirme sırası

C işleçlerinin öncelik ve birleşimleri, ifadelerde işlenenlerin gruplandırılmasını ve değerlendirilmesini etkiler. Bir işlecin önceliği, daha yüksek veya daha düşük önceliğe sahip başka işleçler varsa bir anlam ifade eder. Önce daha yüksek önceliğe sahip işleçler değerlendirilir. Öncelik, "bağlama" sözcüğüyle de açıklanabilir. Daha yüksek önceliğe sahip işleçlerin daha sıkı bağlamaya sahip olduğu söylenir.

Aşağıdaki tabloda, C işleçlerinin öncelik ve ilişkilendirilebilirliği (işlenenlerin değerlendirilme sırası) özetlenmekte ve öncelikleri en yüksekten en düşüğe listelenmektedir. Birkaç işlecin birlikte göründüğü yerlerde, bu işleçler aynı önceliğe sahip olur ve ilişkilendirilebilirliklerine göre değerlendirilir. Tablodaki işleçleri ile başlayan bölümlerde açıklanmıştır [sonek işleçleri](../c-language/postfix-operators.md). Bu bölümün geri kalanında, öncelik ve ilişkilendirilebilirlik hakkında genel bilgiler verilmektedir.

## <a name="precedence-and-associativity-of-c-operators"></a>Öncelik ve ilişkisellik C işleçleri

| Sembol <sup>1</sup> | İşlem türü | İlişkilendirilebilirlik |
|-------------|-----------------------|-------------------|
| `[` `]` `(` `)` `.` `->`<br/>`++` `--` (sonek) | İfade | Soldan sağa |
| **sizeof** `&` `*` `+` `-` `~` `!`<br/>`++` `--` (ön ek) | Birli | Sağdan sola |
| *yuvarlamasını* | Birli | Sağdan sola |
| `*` `/` `%` | Çarpma | Soldan sağa |
| `+``-` | Eklenebilir | Soldan sağa |
| `<<``>>` | Bit düzeyinde kaydırma | Soldan sağa |
| `<` `>` `<=` `>=` | İlişkisel | Soldan sağa |
| `==``!=` | Eşitlik | Soldan sağa |
| `&` | Bit düzeyinde AND | Soldan sağa |
| `^` | Bit düzeyinde dışlamalı OR | Soldan sağa |
| `|` | Bit düzeyinde kapsamalı OR | Soldan sağa |
| `&&` | Mantıksal AND | Soldan sağa |
| `||` | Mantıksal OR | Soldan sağa |
| `? :` | Koşullu ifade | Sağdan sola |
| `=` `*=` `/=` `%=`<br/>`+=` `-=` `<<=` `>>=` `&=`<br/>`^=``|=` | Basit ve bileşik atama <sup>2</sup> | Sağdan sola |
| `,` | Sıralı değerlendirme | Soldan sağa |

<sup>1</sup> işleçler, öncelik azalan sırada listelenir. Aynı satırda veya grupta birkaç işleç görünüyorsa, bunlar eşit önceliğe sahip olur.

<sup>2</sup> tüm basit ve bileşik atama işleçleri eşit önceliğe sahiptir.

Bir ifade eşit önceliğe sahip birkaç işleç içerebilir. Böyle birkaç işleç bir ifadede aynı düzeyde göründüğünde, değerlendirme işlecin ilişkilendirilebilirliğine göre sağdan sola veya soldan sağa devam eder. Değerlendirmenin yönü, birden fazla çarpma içeren ifadelerin sonuçlarını etkilemez (`*`), toplama (`+`), veya ikili bit düzeyinde (`&`, `|`, veya `^`) aynı düzeyde işleci. İşlemlerin sırası dil tarafından tanımlanmaz. Derleyici, tutarlı bir sonuç sağladığı sürece bu tür ifadeleri herhangi bir sırada değerlendirebilir.

Yalnızca sıralı değerlendirme (`,`), mantıksal- ve (`&&`), mantıksal OR (`||`), koşullu ifade (`? :`), ve işleç çağrısı işleçleri dizi noktaları oluşturur ve bu nedenle belirli bir garanti işlenenleri için değerlendirme sırası. İşlev çağrısı işleci, işlev tanımlayıcısının arkasından gelen bir parantezler kümesidir. Sıralı değerlendirme işleci (`,`), işlenenlerini soldan sağa değerlendirmesi garanti edilir. (Bir işlev çağrısındaki virgül işlecinin sıralı değerlendirme işleci ile aynı değildir ve böyle bir garanti sağlamaz.) Daha fazla bilgi için [dizi noktaları](c-sequence-points.md).

Mantıksal işleçler de işlenenlerinin soldan sağa değerlendirilmesini garanti eder. Bununla birlikte, ifadenin sonucunu belirlemek için gereken en az sayıda işleneni değerlendirirler. Buna "kısa devre" değerlendirmesi adı verilir. Bu nedenle, ifadenin bazı işlenenleri değerlendirilmeyebilir. Örneğin, ifadede

`x && y++`

ikinci işlenen `y++`, yalnızca `x` true (sıfırdan farklı) olduğunda değerlendirilir. Bu nedenle, `y``x` yanlış (0) olduğunda artmaz.

## <a name="examples"></a>Örnekler

Aşağıdaki listede, derleyicinin bazı örnek ifadeleri otomatik olarak nasıl bağladığı gösterilmektedir:

| İfade | Otomatik Bağlama |
|----------------|-----------------------|
| `a & b || c` | `(a & b) || c` |
| `a = b || c` | `a = (b || c)` |
| `q && r || s--` | `(q && r) || s--` |

İlk ifadede, bit düzeyinde AND işleci (`&`), mantıksal OR işlecine (`||`) göre daha yüksek bir önceliğe sahiptir, bu nedenle `a & b` mantıksal OR işleminin ilk işlenenini oluşturur.

İkinci ifadede, mantıksal OR işleci (`||`) basit atama işlecine (`=`) göre daha yüksek bir önceliğe sahiptir, bu nedenle `b || c` atamada sağ işlenen olarak gruplandırılır. `a`'ya atanan değerin 0 veya 1 olduğuna dikkat edin.

Üçüncü ifade, beklenmedik bir sonuç oluşturabilecek doğru bir şekilde biçimlendirilmiş bir ifadeyi gösterir. Mantıksal AND işleci (`&&`), mantıksal OR işlecine (`||`) göre daha yüksek bir önceliğe sahiptir, bu nedenle `q && r` bir işlenen olarak gruplandırılır. Mantıksal işleçler işlenenlerin soldan sağa doğru garanti olduğundan `q && r` önce değerlendirilir `s--`. Ancak, varsa `q && r` sıfır olmayan bir değer olarak değerlendirilirse `s--` değerlendirilmez ve `s` azaltılmaz. Azaltma değil, `s` bir sorun, programınızda neden `s--` ifade ilk işleneni görünmesi gereken veya `s` ayrı bir işlemde indirildiği olmalıdır.

Aşağıdaki ifade geçersizdir ve derleme zamanında bir tanılama iletisi oluşturur:

| Geçersiz İfade | Varsayılan Gruplandırma |
|------------------------|----------------------|
| `p == 0 ? p += 1: p += 2` | `( p == 0 ? p += 1 : p ) += 2` |

Bu ifadede, eşitlik işleci (`==`) en yüksek önceliğe sahiptir, bu nedenle `p == 0` bir işlenen olarak gruplandırılır. Koşullu ifade işleci (`? :`) sonraki en yüksek önceliğe sahiptir. İlk işleneni `p == 0`, ikinci işleneni ise `p += 1`'dir. Ancak, koşullu ifade işlecinin son işleneni `p` yerine `p += 2` olarak kabul edilir; çünkü bu `p` örneği koşullu ifade işlecine, bileşik atama işlecine göre daha yakından bağlanır. `+= 2` sol işlenene sahip olmadığı için bir sözdizimi hatası oluşur. Bu türden hataları önlemek ve daha okunabilir bir kod oluşturmak için parantez kullanmanız gerekir. Örneğin, yukarıdaki örneği düzeltmek ve netleştirmek için parantezleri aşağıda gösterildiği gibi kullanabilirsiniz:

`( p == 0 ) ? ( p += 1 ) : ( p += 2 )`

## <a name="see-also"></a>Ayrıca bkz.

[C işleçleri](c-operators.md)
