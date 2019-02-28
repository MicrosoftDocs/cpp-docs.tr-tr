---
title: Dizi Bildirimleri
ms.date: 11/04/2016
helpviewer_keywords:
- multidimensional arrays
- declaring arrays
- arrays [C++], declaring
ms.assetid: 5f958b97-cef0-4058-bbc6-37c460aaed9b
ms.openlocfilehash: 4bc75e86601da77758490544cc5b02c485dcee46
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147782"
---
# <a name="array-declarations"></a>Dizi Bildirimleri

Bir "dizi bildirimi" dizi adları ve, öğelerinin türünü belirtir. Dizideki öğelerin sayısını da tanımlayabilirsiniz. Dizi türüne sahip bir değişken, dizi öğelerinin türü işaretçisi olarak kabul edilir.

## <a name="syntax"></a>Sözdizimi

*bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları* *init-declarator-list*<sub>iyileştirilmiş</sub> **;**

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator-list* **,** *init-declarator*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci* **=** *Başlatıcı*

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İşaretçi*<sub>iyileştirilmiş</sub> *doğrudan bildirimcisi*

*doğrudan bildirimci*: /\* işlev bildirimcisi \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **[** *sabit-ifade*<sub>iyileştirilmiş</sub> **]** 

Çünkü *sabit-ifade* söz dizimine sahip iki forms isteğe bağlıdır:

- İlk form, bir dizi değişkenini tanımlar. *Sabit-ifade* köşeli ayraçlar içindeki bağımsız değişken dizideki öğelerin sayısını belirtir. *Sabit-ifade*, varsa, integral türü ve sıfırdan büyük bir değer olmalıdır. Her öğe tarafından verilen türünde *tür tanımlayıcısı*, dışında herhangi bir tür olabilen `void`. Bir dizi öğesine bir işlev türü olamaz.

- İkinci form, başka yerde tanımlanmış bir değişken bildirir. Bunu atlar *sabit-ifade* köşeli ayraçlar, ancak ayraçlar bağımsız değişken. Yalnızca, daha önce bir parametre olarak bildirilen dizi başlatıldı veya başka bir diziye bir başvuru açıkça tanımlanmış olarak bildirilmiş varsa bu formu kullanabilir programı.

Her iki formlarında *doğrudan bildirimci* can ve değişken adları değişkenin türünü değiştirin. Köşeli ayraçlar (**[]**) aşağıdaki *doğrudan bildirimci* bildirimci bir dizi türü için değiştirin.

Tür niteleyicileri dizi türünde bir nesnenin bildiriminde görünebilir ancak niteleyicileri dizi yerine öğelerine uygulanır.

Bu formda parantezli sabit ifadeler listesini içeren bir dizi bildiricisi izleyerek ("çok boyutlu" bir dizi) oluşan bir dizi bildirebilirsiniz:

> *tür belirticisi* *bildirimci* **[** *sabit-ifade* **]** **[** *sabit-ifade* **]** ...

Her *sabit-ifade* köşeli ayraç içinde belirli bir boyut içindeki öğelerin sayısını tanımlar: iki boyutlu diziler sahip iki ayraçlı ifadeler, üç boyutlu diziler üç sahip ve benzeri. Bir parametre olarak bildirilen dizi başlatılır veya başka bir diziye bir başvuru açıkça tanımlanmış olarak bildirilen ilk sabit ifade atlayabilirsiniz programı.

İşaretçileri dizilerini çeşitli nesneleri karmaşık Bildirimciler kullanarak açıklandığı tanımlayabileceğiniz [daha karmaşık Bildirimcileri yorumlama](../c-language/interpreting-more-complex-declarators.md).

Diziler satıra göre depolanır. Örneğin, aşağıdaki dizi üç sütun olan iki satır oluşur:

```C
char A[2][3];
```

Üç sütunu ilk satırın ikinci satırın üç sütunu tarafından izlenen ilk olarak depolanır. Başka bir deyişle, son alt simge en hızlı bir şekilde değişir.

Bir dizinin tek bir öğesine başvurmak için bir alt simge ifadesi açıklandığı kullanın [sonek işleçleri](../c-language/postfix-operators.md).

## <a name="examples"></a>Örnekler

Bu örneklerde, dizi bildirimleri gösterilmektedir:

```C
float matrix[10][15];
```

Adlı iki boyutlu dizi `matrix` her sahip 150 öğelere sahip **float** türü.

```C
struct {
    float x, y;
} complex[100];
```

Bu bir dizi yapılarının bildirimidir. Bu dizi 100 öğeleri; yine de sahip istiyor musunuz? Her iki üyeleri içeren bir yapıya öğesidir.

```C
extern char *name[];
```

Bu ifade, türü ve bir işaretçiler dizisi adını bildirir `char`. Gerçek tanımı `name` başka bir yerde gerçekleşir.

**Microsoft'a özgü**

Bir dizinin en büyük boyutunu barındırmak için gereken tamsayı türü boyutudur **size_t**. STDDEF üstbilgi dosyasında tanımlanır. H **size_t** olduğu bir `unsigned int` 0x00000000 için 0x7CFFFFFF aralıkla.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Değişken Bildirimleri](../c-language/declarators-and-variable-declarations.md)
