---
title: return Deyimi (C)
ms.date: 11/04/2016
helpviewer_keywords:
- ( ) parentheses in return statements
ms.assetid: 18cd82cf-f899-4b28-83ad-4eff353ddcb4
ms.openlocfilehash: c3975076ee65d267f3d278e20a7770e6750c06d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158391"
---
# <a name="return-statement-c"></a>return Deyimi (C)

`return` İfade bir işlevin yürütülmesini sonlandırır ve çağırma işlevine denetim döndürür. Yürütme, çağrının hemen ardından gelen noktada çağırma işlevinde sürdürülür. Bir `return` ifade, çağırma işlevine de bir değer döndürebilir. Daha fazla bilgi için bkz. [dönüş türü](../c-language/return-type.md) .

## <a name="syntax"></a>Sözdizimi

*sıçrama-deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Return** *ifadesi*<sub>opt</sub> **;**

Varsa *ifadesinin*değeri çağırma işlevine döndürülür. *İfade* atlanırsa, işlevin dönüş değeri tanımsızdır. Varsa ifadesi değerlendirilir ve ardından işlev tarafından döndürülen türe dönüştürülür. İşlev dönüş türü `void`ile bildirilirse, ifade içeren bir `return` deyim uyarı oluşturur ve ifade değerlendirilmez.

Bir işlev `return` tanımında hiçbir ifade görünürse, çağrılan işlevin son ifadesi yürütüldükten sonra Denetim otomatik olarak çağırma işlevine döner. Bu durumda, çağrılan işlevin dönüş değeri tanımsızdır. Dönüş değeri gerekmiyorsa, işlevi dönüş türüne sahip `void` olacak şekilde bildirin; Aksi takdirde, varsayılan dönüş türü olur `int`.

Birçok programcı, `return` deyiminin *ifade* bağımsız değişkenini içine almak için ayraçları kullanır. Ancak C, parantezler gerektirmez.

Bu örnek, `return` ifadesini gösterir:

```C
#include <limits.h>
#include <stdio.h>

void draw( int i, long long ll );
long long sq( int s );

int main()
{
    long long y;
    int x = INT_MAX;

    y = sq( x );
    draw( x, y );
    return x;
}

long long sq( int s )
{
    // Note that parentheses around the return expression
    // are allowed but not required here.
    return( s * (long long)s );
}

void draw( int i, long long ll )
{
    printf( "i = %d, ll = %lld\n", i, ll );
    return;
}
```

Bu örnekte, `main` işlevi iki işlevi çağırır: `sq` ve. `draw` `sq` İşlevi, dönüş değerinin atandığı `x * x` öğesine `main`değerini döndürür `y`. İçindeki `sq` dönüş ifadesinin etrafındaki parantezler, ifadenin bir parçası olarak değerlendirilir ve return deyimi için gerekli değildir. Dönüş ifadesi, dönüş türüne dönüştürülmeden önce değerlendirildiğinden, `sq` olası bir tamsayı taşmasını engellemek için ifade türünü bir tür olarak dönüş türü olarak zorlar, bu da beklenmedik sonuçlara yol açabilir. `draw` İşlev bir `void` işlev olarak bildirilmiştir. Parametrelerinin değerlerini yazdırır ve sonra boş return ifadesinin işlevi sonlanır ve bir değer döndürmez. Dönüş değerini `draw` atama girişimi bir tanılama iletisinin verilmemesine neden olur. `main` İşlev daha sonra değerini `x` işletim sistemine döndürür.

Örneğin çıktısı şuna benzer:

```Output
i = 2147483647, ll = 4611686014132420609
```

## <a name="see-also"></a>Ayrıca bkz.

[Deyimler](../c-language/statements-c.md)
