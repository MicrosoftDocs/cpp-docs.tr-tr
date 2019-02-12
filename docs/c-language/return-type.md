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
ms.openlocfilehash: 3f781e59672764dc518f3c6fad61d4021720362a
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56148146"
---
# <a name="return-type"></a>Dönüş Türü

Bir işlevin dönüş türü, işlev tarafından döndürülen değerin türü ve boyutu oluşturur ve aşağıdaki sözdiziminde tür belirleyiciye karşılık gelen:

## <a name="syntax"></a>Sözdizimi

*işlev tanımı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub> *öznitelik-seq*<sub>iyileştirilmiş</sub> *bildirimci* *bildirim listesi*  <sub>iyileştirilmiş</sub> *bileşik deyim*

/\* *öznitelik-seq* Microsoft Specific \*/

*bildirim tanımlayıcıları*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı tanımlayıcısı* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirticisi* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub>

*tür belirticisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Geçersiz kılma**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Char**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**kısa**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**int**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__int8**  / \* Microsoft'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__int16**  / \* Microsoft'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__int32**  / \* Microsoft'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__int64**  / \* Microsoft'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**uzun**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**kayan nokta**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**çift**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**İmzalı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**İşaretsiz**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct veya union tanımlayıcısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sabit listesi belirticisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*TypeDef adı*

*Tür tanımlayıcısı* herhangi temel belirtebilirsiniz yapı veya birleşim türü. Dahil etmezseniz *tür tanımlayıcısı*, dönüş türü `int` varsayılır.

Programdaki başka yerlerde İşlev bildirimlerinde dönüş türü işlev tanımında belirtilen dönüş türü eşleşmelidir. Bir işlev bir değer döndürür, bir `return` içeren bir ifade deyimi yürütüldüğünde. Gerekli ve işlev çağrıldı noktasına döndürülen dönüş değeri türüne dönüştürülerek ifade değerlendirilir. Bir işlevin dönüş türüyle bildirilirse `void`, bir ifade içeren bir dönüş deyimi bir uyarı oluşturur ve ifade değerlendirilmez.

Aşağıdaki örnekler, işlev dönüş değerleri gösterir.

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

Bu örnek tanımlar `STUDENT` tür bir `typedef` bildirimi ve işlevi tanımlayan `sortstu` olmasını `STUDENT` dönüş türü. İşlev seçer ve iki yapıyı bağımsız değişkenlerinden biri döndürür. Derleyici işlev için sonraki çağrılar içinde denetler bağımsız değişken türleri olduğundan emin olmak için `STUDENT`.

> [!NOTE]
> Yapının tamamını yerine yapı işaretçileri geçirerek verimliliği Gelişmiş.

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

Bu örnek, bir karakter dizisine bir işaretçi döndüren bir işlevin tanımlar. İşlev, iki karakter dizileri (dize) bağımsız değişkenler olarak alır ve kısa bir işaretçi döndürür iki dizenin. Bir dizi işaretçiye işaret ilk dizi öğelerinin ve türü; Bu nedenle, işlevin dönüş türünü tür işaretçisi olan `char`.

İşlevleri bildirmelisiniz olmayan `int` dönüş türü, çağırmadan önce rağmen böylece doğru tür bağımsız değişkenleri ve dönüş değerleri için denetimini etkin prototipleri önerilir.

## <a name="see-also"></a>Ayrıca bkz.

[C İşlev Tanımları](../c-language/c-function-definitions.md)
