---
title: Yapı Bildirimleri
ms.date: 11/04/2016
helpviewer_keywords:
- structure declarations
- anonymous structures
- types [C], declarations
- structure members
- embedded structures
ms.assetid: 5be3be77-a236-4153-b574-7aa77675df7f
ms.openlocfilehash: 3b9aa30cfeecbd60fda61e6a484043c82c9a3b28
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217057"
---
# <a name="structure-declarations"></a>Yapı Bildirimleri

"Yapı bildirimi", bir türü adlandırır ve farklı türlere sahip bir değişken değerleri ("Üyeler" veya yapının "alanları" olarak adlandırılır) belirtir. "Tag" adlı bir isteğe bağlı tanımlayıcı, yapı türünün adını verir ve yapı türüne sonraki başvurularda kullanılabilir. Bu yapı türünün bir değişkeni, bu tür tarafından tanımlanan tüm diziyi tutar. C 'deki yapılar, diğer dillerdeki "kayıtlar" olarak bilinen türlere benzerdir.

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

*struct-bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*belirtici niteleyicisi-List* *struct-declarator-list* **;**

*belirtici niteleyicisi-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *belirleyicisi-niteleyici-List*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *belirleyicisi-niteleyici-List*<sub>opt</sub>

*struct-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-declarator* *yapısı-bildirimci-List* **,** *struct-declarator*

*struct-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *bildirimci*<sub>opt</sub> **:** *sabit ifadesi*

Yapı türünün bildirimi, bir yapı için boşluk yapmaz. Yalnızca yapı değişkenlerinin daha sonraki bildirimlerine yönelik bir şablondur.

Daha önce tanımlanmış bir *tanımlayıcı* (etiket), başka bir yerde tanımlanmış bir yapı türüne başvurmak için kullanılabilir. Bu durumda, tanım görünür olduğu sürece *struct-declaration-List* yinelenemez. Yapı türleri için yapılara işaretçilerin bildirimleri ve yapı türleri için tür tanımları bildirimleri yapı türü tanımlanmadan önce yapı etiketini kullanabilir. Ancak, alanların boyutunun gerçek kullanılmadan önce yapı tanımına de karşılaşmalıdır. Bu, Type ve Type etiketinin tamamlanmamış bir tanımıdır. Bu tanımın tamamlanması için, bir tür tanımının daha sonra aynı kapsamda görünmesi gerekir.

*Struct-declaration-List* , yapı üyelerinin türlerini ve adlarını belirtir. *Struct-declaration-List* bağımsız değişkeni bir veya daha fazla değişken veya bit alanı bildirimi içerir.

*Yapı-bildirim-listesinde* belirtilen her değişken yapı türünün bir üyesi olarak tanımlanır. *Yapı-bildirim-listesi* içindeki değişken bildirimleri, bu bölümde ele alınan diğer değişken bildirimleriyle aynı biçimde, bildirimlerin depolama sınıfı tanımlayıcıları veya başlatıcıları içeremeyeceği durumlar dışında aynı biçimdedir. Yapı üyeleri tür **`void`** , tamamlanmamış tür veya işlev türü dışında herhangi bir değişken türüne sahip olabilir.

Üye, göründüğü yapının türüne sahip olacak şekilde bildirilemez. Ancak, bir üye yapı türünün bir etiketi olduğu sürece göründüğü yapı türüne yönelik bir işaretçi olarak bildirilebilecek. Bu, bağlı yapıların listesini oluşturmanızı sağlar.

Yapılar diğer tanımlayıcılarla aynı kapsamı izler. Yapı tanımlayıcıları, aynı görünürlüğe sahip diğer yapı, birleşim ve numaralandırma etiketlerinden farklı olmalıdır.

*Struct-declaration-List* içindeki her *struct-declaration* liste içinde benzersiz olmalıdır. Ancak, *Yapı-bildirim listesindeki* tanımlayıcı adların, sıradan değişken adlarından veya diğer yapı bildirimi listelerindeki tanımlayıcılardan farklı olması gerekmez.

İç içe yapılara Ayrıca dosya kapsamı düzeyinde bildirildiği halde erişilebilir. Örneğin, bu bildirim verildiğinde:

```C
struct a
{
    int x;
    struct b
    {
      int y;
    } var2;
} var1;
```

Bu bildirimlerin ikisi de geçerlidir:

```C
struct a var3;
struct b var4;
```

## <a name="examples"></a>Örnekler

Bu örnekler Yapı bildirimlerini gösterir:

```C
struct employee   /* Defines a structure variable named temp */
{
    char name[20];
    int id;
    long class;
} temp;
```

`employee`Yapı üç üyeye sahiptir: `name` , `id` ve `class` . `name`Üye bir 20 öğeli dizidir ve `id` `class` **`int`** sırasıyla ve türündeki basit üyeleridir **`long`** . Tanımlayıcı, `employee` Yapı tanımlayıcısıdır.

```C
struct employee student, faculty, staff;
```

Bu örnek üç yapı değişkenini tanımlar: `student` , `faculty` , ve `staff` . Her yapının aynı üç üye listesi vardır. Üyeler, önceki örnekte tanımlanan yapı türüne sahip olacak şekilde bildirilmiştir `employee` .

```C
struct           /* Defines an anonymous struct and a */
{                /* structure variable named complex  */
    float x, y;
} complex;
```

`complex`Yapısında **`float`** , ve türünde iki üye bulunur `x` `y` . Yapı türünün etiketi yok ve bu nedenle adlandırılmamış veya anonim.

```C
struct sample   /* Defines a structure named x */
{
    char c;
    float *pf;
    struct sample *next;
} x;
```

Yapının ilk iki üyesi bir **`char`** değişkendir ve bir değer işaretçisidir **`float`** . Üçüncü üye, `next` tanımlanmakta olan yapı türüne yönelik bir işaretçi olarak bildirilmiştir ( `sample` ).

Anonim yapılar, adlı etiket gerekli olmadığında yararlı olabilir. Bu durum, bir bildirimin tüm yapı örneklerini tanımladığı durumdur. Örneğin:

```C
struct
{
    int x;
    int y;
} mystruct;
```

Gömülü yapılar genellikle anonimdir.

```C
struct somestruct
{
    struct    /* Anonymous structure */
    {
        int x, y;
    } point;
    int type;
} w;
```

**Microsoft'a Özgü**

Derleyici, bir yapının son üyesi olarak boyutlandırılabilen veya sıfır boyutlu bir diziye izin verir. Bu, bir sabit dizinin boyutu farklı durumlarda kullanıldığında yararlı olabilir. Böyle bir yapının bildirimi şöyle görünür:

**`struct`***tanımlayıcı* **{** *-of-of-bildirimlerin* *türü* <em>dizi-adı</em>** \[ ];};**

Boyutlandırılabilen diziler yalnızca bir yapının son üyesi olarak görünebilir. Boyutlandırılmış dizi bildirimleri içeren yapılar, herhangi bir kapsayan yapıda hiçbir başka üye bildirildiği sürece diğer yapılar içinde iç içe olabilir. Bu tür yapıların dizilerine izin verilmez. **`sizeof`** İşleci, bu türün bir değişkenine veya türüne uygulandığında, dizinin boyutu için 0 varsayar.

Yapı bildirimleri, başka bir yapının veya birleşimin üyesi olduklarında bir bildirimci olmadan da belirlenebilir. Alan adları kapsayan yapıya yükseltilir. Örneğin, isimsiz bir yapı şöyle görünür:

```C
struct s
{
    float y;
    struct
    {
        int a, b, c;
    };
    char str[10];
} *p_s;
.
.
.
p_s->b = 100;  /* A reference to a field in the s structure */
```

Yapı başvuruları hakkında bilgi için bkz. [Yapı ve birleşim üyeleri](../c-language/structure-and-union-members.md) .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimciler ve değişken bildirimleri](../c-language/declarators-and-variable-declarations.md)
