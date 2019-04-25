---
title: Birleşim Bildirimleri
ms.date: 11/04/2016
helpviewer_keywords:
- unions
- union keyword [C], declarations
- variant records
ms.assetid: 978c6165-e0ae-4196-afa7-6d94e24f62f7
ms.openlocfilehash: dbc85a467161457641dd86acf5f3720bf4e14247
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291047"
---
# <a name="union-declarations"></a>Birleşim Bildirimleri

"Birleşim bildirimi" bir dizi değişken değerleri ve isteğe bağlı olarak, birleşim adlandırma etiket belirtir. Değişken değerleri birleşimin "Üyeler" olarak adlandırılır ve farklı olabilir. Birleşimler, "değişken kayıtlar" diğer dillerdeki benzerdir.

## <a name="syntax"></a>Sözdizimi

*struct veya union tanımlayıcısı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*yapı veya birleşim* *tanımlayıcı*<sub>iyileştirilmiş</sub> **{** *yapı bildirim listesi* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*yapı veya birleşim* *tanımlayıcısı*

*yapı veya birleşim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Yapı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**birleşim**

*Yapı bildirim listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Yapı bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Yapı bildirim listesi* *yapı bildirimi*

Birleşim içeriği olarak tanımlanır

*Yapı bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*specifier-qualifier-list* *struct-declarator-list*  **;**

*Belirleyicisi niteleyici listesinin*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirticisi* *tanımlayıcısı niteleyici listesi*<sub>iyileştirilmiş</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *tanımlayıcısı niteleyici listesi*<sub>iyileştirilmiş</sub>

*Yapı-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Yapı bildirimcisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Yapı-declarator-list* **,** *yapı bildirimcisi*

Bir değişken **birleşim** türü türü tarafından tanımlanan değerlerden birini depolar. Yapı ve birleşim bildirimleri aynı kurallara yönetir. Birleşimler alanları bit.

Birleşimler üyelerinin yazın, bir eksik tür olamaz `void`, veya işlev türü. Bu nedenle üyeleri Birliği örneği olamaz ancak bildirilen birleşim türü işaretçileri olabilir.

Birleşim türü yalnızca bir şablonu bildirimidir. Bildirilen bir değişkenin kadar bellek ayrılmış değil.

> [!NOTE]
> İki tür UNION bildirilmiş ve bir değeri depolanan ancak birleşim bir türü ile erişilen, sonuçları güvenilir değil. Örneğin, bir birleşimini **float** ve `int` bildirilir. A **float** değeri depolanır, ancak bu programı daha sonra değeri olarak erişen bir `int`. Böyle bir durumda iç depolama alanında değer bağlıdır **float** değerleri. Tamsayı değeri güvenilir olmaz.

## <a name="examples"></a>Örnekler

Birleşimler örnekleri aşağıda verilmiştir:

```C
union sign   /* A definition and a declaration */
{
    int svar;
    unsigned uvar;
} number;
```

Bu örnek, birleşim değişkenini ile tanımlar `sign` yazın ve adlı bir değişken bildirir `number` iki üyesi olan: `svar`, imzalı bir tamsayı ve `uvar`, işaretsiz bir tamsayı. Bu bildirimi geçerli değerini sağlar `number` işaretli veya işaretsiz bir değer olarak depolanacak. Bu birleşim türü ile ilişkili etiket `sign`.

```C
union               /* Defines a two-dimensional */
{                   /*  array named screen */
    struct
    {
      unsigned int icon : 8;
      unsigned color : 4;
    } window1;
    int screenval;
} screen[25][80];
```

`screen` Dizi 2.000 öğeleri içerir. Dizideki her öğeye iki üyesi olan tek bir birleşimdir: `window1` ve `screenval`. `window1` İki bit alanı üyesi bir yapı üyesidir `icon` ve `color`. `screenval` Üyesi olan bir `int`. Birleşim her öğe herhangi bir zamanda bulunduran `int` tarafından temsil edilen `screenval` veya yapısı tarafından temsil edilen `window1`.

**Microsoft'a özgü**

İç içe geçmiş birleşimler başka bir yapı veya birleşim üyesi olduklarında, anonim olarak bildirilebilir. Bu, adsız bir birleşim örneğidir:

```C
struct str
{
    int a, b;
    union            / * Unnamed union */
    {
      char c[4];
      long l;
      float f;
   };
   char c_array[10];
} my_str;
.
.
.
my_str.l == 0L;  /* A reference to a field in the my_str union */
```

Birleşimler genellikle belirli bir zamanda birleşimde yer alan veri türünü vermiş bir alan içeren bir yapı içinde iç içe geçirilmiştir. Bu tür UNION bildirimi örnektir:

```C
struct x
{
    int type_tag;
    union
    {
      int x;
      float y;
    }
}
```

Bkz: [yapı ve birleşim üyeleri](../c-language/structure-and-union-members.md) birleşimler başvurma hakkında bilgi.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Değişken Bildirimleri](../c-language/declarators-and-variable-declarations.md)
