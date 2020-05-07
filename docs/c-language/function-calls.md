---
title: işlev Çağrıları
ms.date: 11/04/2016
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls, about function calls
- function calls
ms.assetid: 2cfa897d-3874-4820-933c-e624f75d1712
ms.openlocfilehash: cce1a888f3e1224822ab4e97c67bf59da4c46fc9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81334569"
---
# <a name="function-calls"></a>işlev Çağrıları

*İşlev çağrısı* , denetim ve bağımsız değişkenleri (varsa) işleve geçiren bir ifadedir ve şu biçimdedir:

*ifade* (*ifade listesi*<sub>opt</sub>)

Burada *ifadesi* bir işlev adı, veya işlev adresi olarak değerlendirilir ve *ifade listesi* bir ifade listesidir (virgülle ayrılmış olarak). Bu ikinci ifadelerin değerleri, işleve geçirilen bağımsız değişkenlerdir. İşlev bir değer döndürmezse, bunu döndüren `void`bir işlev olarak bildirirsiniz.

Bir bildirim, işlev çağrısından önce mevcutsa, ancak parametrelerle ilgili hiçbir bilgi verilmemişse, bildirilmemiş tüm bağımsız değişkenler normal aritmetik Dönüştürmelere doğru bir şekilde geçer.

> [!NOTE]
> İşlev bağımsız değişken listesindeki ifadeler herhangi bir sırada değerlendirilebilir, bu nedenle değerleri başka bir bağımsız değişkenden yan etkilere göre değiştirilebilen bağımsız değişkenlerin tanımsız değerleri vardır. İşlev çağrısı işleci tarafından tanımlanan sıra noktası, denetim çağrılan işleve geçmeden önce bağımsız değişken listesindeki tüm yan etkileri değerlendirirler. (Bağımsız değişkenlerin yığına gönderildiği sıranın ayrı bir önemi olduğunu unutmayın.) Daha fazla bilgi için bkz. [dizi noktaları](../c-language/c-sequence-points.md) .

Herhangi bir işlev çağrısındaki tek gereksinim, parantezden önceki ifadenin bir işlev adresini değerlendirmelidir. Bu, bir işlevin herhangi bir işlev işaretçisi ifadesi aracılığıyla çağrılabilecek anlamına gelir.

## <a name="example"></a>Örnek

Bu örnekte, bir `switch` deyimden çağrılan işlev çağrıları gösterilmektedir:

```
int main()
{
    /* Function prototypes */

    long lift( int ), step( int ), drop( int );
    void work( int number, long (*function)(int i) );

    int select, count;
    .
    .
    .
    select = 1;
    switch( select )
    {
        case 1: work( count, lift );
                break;

        case 2: work( count, step );
                break;

        case 3: work( count, drop );
                /* Fall through to next case */
        default:
                break;
    }
}

/* Function definition */

void work( int number, long (*function)(int i) )
{
    int i;
    long j;

    for ( i = j = 0; i < number; i++ )
            j += ( *function )( i );
}
```

Bu örnekte, işlev çağrısı `main`,

```
work( count, lift );
```

bir tamsayı değişkeni `count`, ve işlevin `lift` adresini işleve `work`geçirir. İşlev tanımlayıcısı bir işaretçi ifadesi olarak değerlendirildiğinden işlev adresinin yalnızca işlev tanımlayıcısı vererek geçtiğini unutmayın. Bir işlev tanımlayıcısını bu şekilde kullanmak için, tanımlayıcı kullanılmadan önce işlevin bildirilmesini veya tanımlanması gerekir; Aksi takdirde, tanımlayıcı tanınmıyor. Bu durumda, `work` `main` işlevinin başlangıcında için bir prototipi verilir.

İçindeki `function` `work` parametresi bir `int` bağımsız değişken alan ve **uzun** bir değer döndüren bir işlevin işaretçisi olacak şekilde bildirilmiştir. Parametre adının etrafındaki parantezler gereklidir; Bu olmadan, bildirim, **uzun** bir değere işaretçi döndüren bir işlevi belirtir.

İşlevi `work` , aşağıdaki işlev çağrısını kullanarak, **for** döngüsü içindeki seçili işlevi çağırır:

```
( *function )( i );
```

Bir bağımsız değişken `i`, çağrılan işleve geçirilir.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../c-language/functions-c.md)
