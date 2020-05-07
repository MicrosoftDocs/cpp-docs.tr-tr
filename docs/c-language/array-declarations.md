---
title: Dizi Bildirimleri
ms.date: 11/04/2016
helpviewer_keywords:
- multidimensional arrays
- declaring arrays
- arrays [C++], declaring
ms.assetid: 5f958b97-cef0-4058-bbc6-37c460aaed9b
ms.openlocfilehash: 4bc75e86601da77758490544cc5b02c485dcee46
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62313551"
---
# <a name="array-declarations"></a>Dizi Bildirimleri

"Dizi bildirimi" diziyi adlandırır ve öğelerinin türünü belirtir. Ayrıca dizideki öğe sayısını da tanımlayabilir. Dizi türündeki bir değişken, dizi öğelerinin türüne yönelik bir işaretçi olarak değerlendirilir.

## <a name="syntax"></a>Sözdizimi

*bildirim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim-belirteçleri* *init-declarator-list*<sub>opt</sub> **;**

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator-list*  **,**  *init-declarator*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci* **=** *başlatıcısı*

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretçi*<sub>opt</sub> *doğrudan bildirimci*

*Direct-bildirimci*:/\* bir işlev bildirimci\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-declarator*  **[**  *sabit ifade*<sub>katılımı</sub> **]**

*Sabit ifade* isteğe bağlı olduğundan, sözdiziminin iki biçimi vardır:

- İlk form bir dizi değişkenini tanımlar. Köşeli ayraçlar içindeki *sabit ifade* bağımsız değişkeni dizideki öğelerin sayısını belirtir. Varsa, *sabit ifadesi*integral türüne ve sıfırdan büyük bir değere sahip olmalıdır. Her öğe tür *belirleyicisi*tarafından verilen türe sahiptir; bu, dışında `void`herhangi bir tür olabilir. Dizi öğesi bir işlev türü olamaz.

- İkinci form, başka bir yerde tanımlanmış bir değişken bildirir. Köşeli ayraçlar değil parantez içinde *sabit ifade* bağımsız değişkenini atlar. Bu formu yalnızca, diziyi önceden oluşturduysanız veya bir parametre olarak bildirildiği ya da programın başka bir yerde açıkça tanımlanmış bir diziye başvuru olarak bildirildiği durumlarda kullanabilirsiniz.

Her iki formda da, *doğrudan bildirimci* değişkeni adlandırır ve değişkenin türünü değiştirebilir. *Doğrudan bildirimci* izleyen köşeli ayraçlar (**[]**), bildirimcisini bir dizi türü olarak değiştirir.

Tür niteleyicileri dizi türünde bir nesnenin bildiriminde görünebilir, ancak niteleyiciler dizi kendisi yerine öğeler için geçerlidir.

Dizi bildirimcisini, bu formdaki parantez içine alınmış sabit ifadelerin bir listesiyle izleyerek, dizi dizilerini ("çok boyutlu" dizi) bildirebilirsiniz:

> *tür belirleyicisi* *bildirimci* **[** *sabit-ifade* **]** **[** *sabit-ifade* **]** ...

Köşeli ayraçlar içindeki her bir *sabit ifade* , belirli bir boyuttaki öğelerin sayısını tanımlar: iki boyutlu diziler iki köşeli ayraçlı ifadeye sahiptir, üç boyutlu diziler üç ve bu şekilde devam eder. Diziyi oluşturduysanız, parametreyi bir parametre olarak bildirdiyseniz veya onu programın başka bir yerinde açıkça tanımlanmış bir diziye başvuru olarak bildirilirse, ilk sabit ifadeyi atlayabilirsiniz.

[Daha karmaşık bildirimcilerin yorumlanması](../c-language/interpreting-more-complex-declarators.md)bölümünde açıklandığı gibi karmaşık Bildirimciler kullanarak çeşitli nesne türlerine işaretçiler dizisi tanımlayabilirsiniz.

Diziler satıra göre saklanır. Örneğin, aşağıdaki dizi her biri üç sütunlu iki satırdan oluşur:

```C
char A[2][3];
```

İlk satırın üç sütunu, ilk olarak ikinci satırın üç sütununun ardından depolanır. Yani, son alt simge en hızlı şekilde değişir.

Bir dizinin tek bir öğesine başvurmak için, [sonek işleçleri](../c-language/postfix-operators.md)bölümünde açıklandığı gibi bir alt simge ifadesi kullanın.

## <a name="examples"></a>Örnekler

Bu örneklerde dizi bildirimleri gösterilmektedir:

```C
float matrix[10][15];
```

Adlı `matrix` iki boyutlu dizide, her birinin **float** türüne sahip 150 öğesi vardır.

```C
struct {
    float x, y;
} complex[100];
```

Bu bir yapı dizisinin bir bildirimidir. Bu dizide 100 öğe vardır; her öğe iki üye içeren bir yapıdır.

```C
extern char *name[];
```

Bu ifade, işaretçilerin bir dizisinin türünü ve adını bildirir `char`. Gerçek tanımı başka bir `name` yerde gerçekleşir.

**Microsoft'a Özgü**

Bir dizinin en büyük boyutunu tutmak için gereken tamsayı türü **size_t**boyutudur. STDDEF başlık dosyasında tanımlanmıştır. H, **size_t** 0x00000000 `unsigned int` Ile 0x7CFFFFFF arasındadır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Değişken Bildirimleri](../c-language/declarators-and-variable-declarations.md)
