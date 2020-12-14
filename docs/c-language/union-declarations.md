---
description: 'Daha fazla bilgi edinin: birleşim bildirimleri'
title: Birleşim Bildirimleri
ms.date: 11/04/2016
helpviewer_keywords:
- unions
- union keyword [C], declarations
- variant records
ms.assetid: 978c6165-e0ae-4196-afa7-6d94e24f62f7
ms.openlocfilehash: c544a4d92f452415fdd03ccef51d49f69e2b5dae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258830"
---
# <a name="union-declarations"></a>Birleşim Bildirimleri

"UNION bildirimi" bir değişken değerleri kümesini ve isteğe bağlı olarak UNION adını adlandırarak bir etiketi belirtir. Değişken değerleri birleşimin "Üyeler" olarak adlandırılır ve farklı türlere sahip olabilir. Birleşimler, diğer dillerdeki "varyant kayıtları" ile benzerdir.

## <a name="syntax"></a>Syntax

*struct veya-Union-belirleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct veya-Union* *tanımlayıcısı*<sub>opt</sub> **{** *struct-declaration-List* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct veya-Union* *tanımlayıcısı*

*struct veya-Union*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`struct`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`union`**

*struct-declaration-List*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-declaration-List* *struct-bildirimi*

Birleşim içeriği şu şekilde tanımlanır

*struct-bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*belirtici niteleyicisi-List* *struct-declarator-list*  **;**

*belirtici niteleyicisi-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *belirleyicisi-niteleyici-List*<sub>opt</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *belirleyicisi-niteleyici-List*<sub>opt</sub>

*struct-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-declarator-list*  **,**  *struct-declarator*

Türüne sahip bir değişken **`union`** , bu tür tarafından tanımlanan değerlerden birini depolar. Aynı kurallar yapı ve birleşim bildirimlerini yönetir. Birleşimlerde de bit alanları olabilir.

Birleşimlerin üyeleri tamamlanmamış bir tür, tür **`void`** veya işlev türüne sahip olamaz. Bu nedenle, Üyeler birleşimin bir örneği olamaz, ancak bildirildiği birleşim türüne işaretçiler olabilir.

Birleşim türü bildirimi yalnızca bir şablondur. Değişken bildirildiği sürece bellek ayrılmamış.

> [!NOTE]
> İki tür birleşimi bildirilirse ve bir değer depolanıyorsa, ancak birleşime diğer türle erişildiğinde sonuçlar güvenilir değildir. Örneğin, **`float`** ve birleşimi **`int`** bildirilmiştir. Bir **`float`** değer depolanır, ancak program daha sonra değerine bir olarak erişir **`int`** . Böyle bir durumda, değer, değerlerin iç depolamasına bağlıdır **`float`** . Tamsayı değeri güvenilir değil.

## <a name="examples"></a>Örnekler

Birleşimlerin örnekleri aşağıda verilmiştir:

```C
union sign   /* A definition and a declaration */
{
    int svar;
    unsigned uvar;
} number;
```

Bu örnek, türünde bir UNION değişkeni tanımlar `sign` ve iki üyeye sahip adlı bir değişken bildirir `number` : `svar` , işaretli bir tamsayı ve işaretsiz bir `uvar` tamsayı. Bu bildirim geçerli değerinin `number` imzalı ya da işaretsiz bir değer olarak depolanmasını sağlar. Bu birleşim türüyle ilişkili etiket `sign` .

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

`screen`Dizi 2.000 öğe içeriyor. Dizideki her öğe, iki üye içeren tek bir birleşimdir: `window1` ve `screenval` . `window1`Üye, iki bitlik alan üyesi olan bir yapıdır `icon` ve `color` . `screenval`Üye bir **`int`** . Herhangi bir zamanda, her UNION öğesi tarafından temsil **`int`** edilen ya da temsil `screenval` eden yapıyı barındırır `window1` .

**Microsoft'a Özgü**

İç içe birleşimler, başka bir yapının veya birleşimin üyesi olduklarında anonim olarak bildirilebilir. Bu, isimsiz bir birleşimin bir örneğidir:

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

Birleşimler genellikle herhangi bir zamanda birleşimde yer alan veri türlerine veren bir alanı içeren bir yapı içinde iç içe geçmiş olur. Bu, bu tür bir Union için bildirime örnektir:

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

Başvuru sendikaları hakkında bilgi için bkz. [Yapı ve birleşim üyeleri](../c-language/structure-and-union-members.md) .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimciler ve değişken bildirimleri](../c-language/declarators-and-variable-declarations.md)
