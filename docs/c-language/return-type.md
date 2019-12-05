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
ms.openlocfilehash: fe9280f434dd6267b03764df2ee663c494f007d8
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857040"
---
# <a name="return-type"></a>Dönüş Türü

Bir işlevin dönüş türü, işlevin döndürdüğü değerin boyutunu ve türünü belirler ve aşağıdaki sözdiziminde bulunan tür belirleyicisi öğesine karşılık gelir:

## <a name="syntax"></a>Sözdizimi

*işlev tanımı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi-belirticileri*<sub>opt</sub> *özniteliği-seq*<sub>opt</sub> *bildirimci* *bildirimi-List*<sub>opt</sub> *Bileþik-deyimin*

/\* *özniteliği-seq* , Microsoft 'a özgü \*/

*bildirim-tanımlayıcılar*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı Belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *bildirimi-tanımlayıcılar*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirimi-tanımlayıcılar*<sub>opt</sub>

*tür belirleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**void**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**karakteri**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**kısa**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**int**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int8** /\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int16** /\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int32** /\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int64** /\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**uzun**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**float**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Double**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**imzalı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**işaretsiz**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-or-Union-belirleyicisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enum belirleyicisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*typedef-adı*

*Tür belirleyicisi* herhangi bir temel, yapı veya birleşim türü belirtebilir. *Tür belirleyicisi*eklemezseniz, `int` dönüş türü varsayılır.

İşlev tanımında verilen dönüş türü, programın başka bir yerinde, işlevin bildirimlerinde dönüş türüyle eşleşmelidir. Bir işlev, bir ifade içeren `return` deyimi yürütüldüğünde bir değer döndürür. İfade değerlendirilir, gerekirse dönüş değeri türüne dönüştürülür ve işlevin çağrıldığı noktaya döndürülür. Bir işlev dönüş türü `void`ile bildirilirse, ifade içeren bir dönüş deyimi bir uyarı oluşturur ve ifade değerlendirilmez.

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

Bu örnek `STUDENT` türünü `typedef` bildirimiyle tanımlar ve `STUDENT` dönüş türüne sahip olacak `sortstu` işlevi tanımlar. İşlevi, iki yapı bağımsız değişkenlerinden birini seçer ve döndürür. İşlevin sonraki çağrılarında, derleyici bağımsız değişken türlerinin `STUDENT`olduğundan emin olmak için kontrol eder.

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

Bu örnek, bir karakter dizisine bir işaretçi döndüren bir işlevi tanımlar. İşlevi bağımsız değişken olarak iki karakter dizisi (dizeler) alır ve iki dizenin kısaldığına bir işaretçi döndürür. Bir dizi işaretçisi dizi öğelerinden birincilerine işaret eder ve türüne sahiptir; Bu nedenle, işlevinin dönüş türü `char`türünde bir işaretçidir.

Prototip ve dönüş değerleri için doğru tür denetlemesi etkin olacak şekilde, prototipler önerilse de, onları çağırmadan önce `int` dönüş türü ile işlevler bildirmemelidir.

## <a name="see-also"></a>Ayrıca bkz.

[C İşlev Tanımları](../c-language/c-function-definitions.md)
