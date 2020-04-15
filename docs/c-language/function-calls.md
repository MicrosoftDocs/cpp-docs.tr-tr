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

*İşlev çağrısı,* denetimi ve bağımsız değişkenleri (varsa) bir işleve geçen ve şu forma sahip bir ifadedir:

*expression* (*expression-list*<sub>opt</sub>)

*ifadenin* bir işlev adı olduğu veya bir işlev adresine değerlendirildiği ve *ifade listesiifadelerin* (virgülle ayrılmış) listesidir. Bu ikinci ifadelerin değerleri, işleve geçirilen bağımsız değişkenlerdir. İşlev bir değer döndürmezse, onu döndüren `void`bir işlev olarak beyan emişsiniz.

İşlev çağrısından önce bir bildirim varsa, ancak parametrelerle ilgili bilgi verilmiyorsa, bildirilmemiş bağımsız değişkenler yalnızca olağan aritmetik dönüşümlerden geçer.

> [!NOTE]
> İşlev bağımsız değişken listesindeki ifadeler herhangi bir sırada değerlendirilebilir, bu nedenle değerleri başka bir bağımsız değişkenin yan etkileriyle değiştirilebilen bağımsız değişkenlerin tanımlanmamış değerleri vardır. İşlev-arama işleci tarafından tanımlanan sıra noktası, yalnızca denetim çağrılan işleve geçmeden önce bağımsız değişken listesindeki tüm yan etkilerin değerlendirildiğini garanti eder. (Bağımsız değişkenlerin yığına itildiği sıranın ayrı bir konu olduğunu unutmayın.) Daha fazla bilgi için [Sıra Noktaları'na](../c-language/c-sequence-points.md) bakın.

Herhangi bir işlev çağrısındaki tek gereksinim, parantez lerden önceki ifadenin bir işlev adresine değerlendirilmesi gerektiğidir. Bu, bir işlevin herhangi bir işlev işaretçisi ifadesi yle çağrılabileceği anlamına gelir.

## <a name="example"></a>Örnek

Bu örnek, deyimden `switch` çağrılan işlev çağrılarını göstermektedir:

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

Bu örnekte, işlev `main`çağrısı ,

```
work( count, lift );
```

bir sonda değişkeni `count`geçer ve işlevin `lift` adresini `work`işleve . İşlev tanımlayıcısı bir işaretçi ifadesine değer verdiğinden, işlev adresinin yalnızca işlev tanımlayıcısı vererek geçirildiğini unutmayın. Bir işlev tanımlayıcısını bu şekilde kullanmak için, tanımlayıcı kullanılmadan önce işlevin bildirilmesi veya tanımlanması gerekir; aksi takdirde, tanımlayıcı tanınmıyor. Bu durumda, `work` `main` fonksiyonun başında bir prototip verilir.

Parametre, `function` bir `int` bağımsız değişkeni alan ve uzun bir değer döndüren bir işlevin işaretçisi olarak bildirilir. **long** `work` Parametre adı etrafında parantez gereklidir; bunlar olmadan, bildirimde işaretçiyi **uzun** bir değere döndüren bir işlev belirtilir.

İşlev `work` aşağıdaki işlev çağrısını kullanarak for **döngüsü** içinden seçili işlevi çağırır:

```
( *function )( i );
```

Bir bağımsız `i`değişken, çağrılan işleve geçirilir.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../c-language/functions-c.md)
