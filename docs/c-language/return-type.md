---
title: Dönüş Türü
ms.date: 11/04/2016
helpviewer_keywords:
- function return types
- return values [C++], function procedures
- function return types, syntax
- return values [C++]
- data types [C++], function return types
- return keyword [C++], function return types
- functions [C++], return types
ms.assetid: 3e5b8a97-b341-48c5-8be8-8986980ef586
ms.openlocfilehash: 1d905e02be02784b562b9d1a8f72a9bfa4057b9b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226333"
---
# <a name="return-type"></a>Dönüş Türü

Bir işlevin dönüş türü, işlevin döndürdüğü değerin boyutunu ve türünü belirler ve aşağıdaki sözdiziminde bulunan tür belirleyicisi öğesine karşılık gelir:

## <a name="syntax"></a>Sözdizimi

*işlev tanımı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bildirim-belirticileri*<sub>opt</sub> *özniteliği-seq*<sub>opt</sub> *bildirimci* *bildirimi-List*<sub>opt</sub> *bileşik-deyimin*

/\**öznitelik-Seq* , Microsoft 'a özgüdür\*/

*bildirim-tanımlayıcılar*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı Belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub>

*tür belirleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`void`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`char`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`short`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`int`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__int8`** /\*Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__int16`** /\*Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__int32`** /\*Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__int64`** /\*Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`long`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`float`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`double`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`signed`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`unsigned`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct veya-Union-Belirleyicisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Sabit Listesi belirticisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*TypeDef-adı*

*Tür belirleyicisi* herhangi bir temel, yapı veya birleşim türü belirtebilir. *Tür belirleyicisi*eklemezseniz, dönüş türü **`int`** varsayılır.

İşlev tanımında verilen dönüş türü, programın başka bir yerinde, işlevin bildirimlerinde dönüş türüyle eşleşmelidir. Bir işlev **`return`** , bir ifade içeren bir deyim yürütüldüğünde bir değer döndürür. İfade değerlendirilir, gerekirse dönüş değeri türüne dönüştürülür ve işlevin çağrıldığı noktaya döndürülür. Bir işlev dönüş türü ile bildirilirse, bir **`void`** ifade içeren bir dönüş deyimi uyarı oluşturur ve ifade değerlendirilmez.

Aşağıdaki örnekler işlev dönüş değerlerini gösterir.

```C
typedef struct
{
    char name[20];
    int id;
    long class;
} STUDENT;

/* Return type is STUDENT: */

STUDENT sortstu( STUDENT a, STUDENT b )
{
    return ( (a.id < b.id) ? a : b );
}
```

Bu örnek, `STUDENT` türü bir bildirimiyle tanımlar **`typedef`** ve `sortstu` dönüş türüne sahip işlevi tanımlar `STUDENT` . İşlevi, iki yapı bağımsız değişkenlerinden birini seçer ve döndürür. İşlevin sonraki çağrılarında, derleyici bağımsız değişken türlerinin olduğundan emin olmak için kontrol eder `STUDENT` .

> [!NOTE]
> Verimlilik, yapının tamamı yerine, yapıya işaretçi geçirilerek geliştirilebilir.

```C
char *smallstr( char s1[], char s2[] )
{
    int i;

    i = 0;
    while ( s1[i] != '\0' && s2[i] != '\0' )
        i++;
    if ( s1[i] == '\0' )
        return ( s1 );
    else
        return ( s2 );
}
```

Bu örnek, bir karakter dizisine bir işaretçi döndüren bir işlevi tanımlar. İşlevi bağımsız değişken olarak iki karakter dizisi (dizeler) alır ve iki dizenin kısaldığına bir işaretçi döndürür. Bir dizi işaretçisi dizi öğelerinden birincilerine işaret eder ve türüne sahiptir; Bu nedenle, işlevinin dönüş türü, türüne yönelik bir işaretçidir **`char`** .

**`int`** Prototip ve dönüş değerleri için doğru tür denetlemesi etkin olacak şekilde, prototipler önerilse de, dönüş türü olan işlevleri bildirmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[C Işlev tanımları](../c-language/c-function-definitions.md)
