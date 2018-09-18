---
title: Statement (C) iade | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- ( ) parentheses in return statements
ms.assetid: 18cd82cf-f899-4b28-83ad-4eff353ddcb4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 466a56bf4d1a309aadccbcbbccc91de6a59e6e1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067362"
---
# <a name="return-statement-c"></a>return Deyimi (C)

`return` Deyimi bir işlevin yürütülmesini sonlandırır ve denetim çağırma işlevine döndürür. Çağıran işlevin çağrının hemen ardından bir noktada yürütmeyi devam ettirir. A `return` ifadesi bir değer de çağırma işlevine dönebilirsiniz. Bkz: [dönüş türü](../c-language/return-type.md) daha fazla bilgi için.

## <a name="syntax"></a>Sözdizimi

*atlama-deyimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dönüş** *ifade*<sub>iyileştirilmiş</sub> **;**

Değerini *ifade*, varsa, çağırma işlevine döndürülür. Varsa *ifade* olan atlanırsa, işlev dönüş değeri tanımsızdır. İfade varsa, değerlendirilir ve ardından işlev tarafından döndürülen tür dönüştürülür. İşlev dönüş türüyle bildirilmişlerse `void`, `return` içeren bir ifade deyimi, bir uyarı oluşturur ve ifade değerlendirilmez.

Hayır ise `return` çağrılan işlevin son deyim yürütüldükten sonra deyimi görünen işlev tanımında denetimi otomatik olarak çağırma işlevine döndürür. Bu durumda, çağrılan işlev dönüş değeri tanımsızdır. Dönüş değeri gerekli değilse, için işlevi bildirin `void` dönüş türü; Aksi takdirde, varsayılan dönüş türü `int`.

Birçok Programcı parantez içine almak için kullanın. *ifade* bağımsız değişkeni `return` deyimi. Ancak, C parantezler gerektirmez.

Bu örnek gösterir `return` deyimi:

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

Bu örnekte, `main` işlevi iki işlev çağrısı: `sq` ve `draw`. `sq` İşlevi değerini döndürür `x * x` için `main`, dönüş değeri atanır burada `y`. Dönüş ifade parantezler `sq` ifadesinin bir parçası değerlendirilir ve dönüş deyimi tarafından gerekli değildir. Dönüş türüne dönüştürmeden önce dönüş ifadesi değerlendirilir beri `sq` beklenmeyen sonuçlara neden bir olası tamsayı taşma önlemek için dönüş türü ile bir atama ifadesi türü zorlar. `draw` İşlevi olarak bildirilen bir `void` işlevi. Kendi parametre değerlerini yazdırır ve ardından boş dönüş deyimi işlev sona erer ve bir değer döndürmez. Dönüş değeri atama denemesi `draw` verilmesi bir tanılama iletisi neden olur. `main` İşlevi ardından değerini döndürür `x` işletim sistemi.

Örnek çıktısı şuna benzer:

```Output
i = 2147483647, ll = 4611686014132420609
```

## <a name="see-also"></a>Ayrıca Bkz.

[Deyimler](../c-language/statements-c.md)