---
title: İşlev çağrılarında | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls, about function calls
- function calls
ms.assetid: 2cfa897d-3874-4820-933c-e624f75d1712
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd62a5a4d2ef4c4b2337557b9eb6a37533167dc0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016929"
---
# <a name="function-calls"></a>işlev Çağrıları

A *işlev çağrısı* denetimi ve bağımsız değişken bir işleve geçirir (varsa) bir ifade olan ve biçime sahiptir:

*ifade* (*ifade listesi*<sub>iyileştirilmiş</sub>)

Burada *ifade* bir işlev adı veya bir işlev adresini değerlendirir ve *ifade listesi* (virgülle ayrılmış) ifadelerin listesidir. Bu ikinci ifadelerin değerleri, işleve geçirilen bağımsız değişkenlerdir. İşlev bir değer döndürmeyen sonra döndüren bir işlev olarak bildirmek `void`.

Önceki işlev çağrısında bir bildirimi var, ancak parametreleri hiçbir bilgiyi, bildirilmemiş herhangi bir bağımsız değişken yalnızca olağan aritmetik dönüştürmelerden.

> [!NOTE]
>  Değerleri başka bir bağımsız değişkende yan etkileri tarafından değiştirilebilir bağımsız değişkenleri değerleri tanımsız şekilde ifadeleri işlevi bağımsız değişken listesindeki herhangi bir sırada değerlendirilebilir. İşlev çağrısı işleci tarafından tanımlanan bir dizi noktası, yalnızca denetim çağrılan işleve geçirmeden önce tüm yan etkiler bağımsız değişken listesinde değerlendirilir güvence altına alır. (Bağımsız değişkenler yığına itilir sırasını birkaç farklı olduğunu unutmayın.) Bkz: [dizi noktaları](../c-language/c-sequence-points.md) daha fazla bilgi için.

Herhangi bir işlev çağrısındaki tek gereksinim, parantezler önce ifade bir işlev adresini değerlendirmelidir olmasıdır. Başka bir deyişle, bir işlev herhangi bir işlev işaretçisi ifade çağrılabilir.

## <a name="example"></a>Örnek

Bu örnekte çağrılır işlev çağrıları bir `switch` deyimi:

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

Bu örnekte, bir işlevi çağırmak `main`,

```
work( count, lift );
```

bir tamsayı değişkeni geçirir `count`ve işlevin adresini `lift` işleve `work`. İşlev adresi için bir işaretçi ifadesi bir işlev tanımlayıcı değerlendirildiğinden yalnızca işlev tanımlayıcı vererek geçirildiğini unutmayın. Bir işlev tanımlayıcı bu şekilde kullanmak için işlev gerekir bildirilemez veya tanımlayıcı kullanılmadan önce tanımlanan; Aksi takdirde, tanımlayıcının tanınmıyor. Bu durumda, bir prototip için de `work` başında verilen `main` işlevi.

Parametre `function` içinde `work` bir alan bir işlev işaretçisi olarak bildirilmiştir `int` bağımsız değişkeni ve döndüren bir **uzun** değeri. Parametre adı parantez gereklidir; bunlar olmadan bir işaretçi döndüren bir işlevin bildirimi belirtebilirdiniz bir **uzun** değeri.

İşlev `work` içinde seçili fonksiyonu çağıran **için** döngü kullanarak aşağıdaki işlev çağrısı:

```
( *function )( i );
```

Tek bir bağımsız değişken `i`, çağrılan işleve geçirilir.

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevler](../c-language/functions-c.md)