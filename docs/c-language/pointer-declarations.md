---
description: 'Daha fazla bilgi edinin: Işaretçi bildirimleri'
title: İşaretçi Bildirimleri
ms.date: 11/04/2016
helpviewer_keywords:
- pointer declarations
- declarations, pointers
- const keyword [C]
- pointers, declarations
ms.assetid: 8b3b7fc7-f44d-480d-b6f9-cebe4e5462a6
ms.openlocfilehash: 3c1670d1dd86e7df7f164e357ff99f3ed31e7339
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195924"
---
# <a name="pointer-declarations"></a>İşaretçi Bildirimleri

*İşaretçi bildirimi* bir işaretçi değişkenini adlandırır ve değişkenin işaret ettiği nesnenin türünü belirtir. İşaretçi olarak belirtilen bir değişken bir bellek adresini tutar.

## <a name="syntax"></a>Syntax

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretçi*<sub>opt</sub> *doğrudan bildirimci*

*doğrudan bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Tanımlayıcısını*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**(** *bildirimci* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-declarator* **[** *sabit ifade*<sub>katılımı</sub> **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-declarator* **(** *parametre-tür-listesi* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-declarator* **(** *tanımlayıcı listesi*<sub>opt</sub> **)**

*işaretçi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong>*tür niteleyicisi-List*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong>*tür niteleyicisi-liste*<sub>opt</sub> *işaretçisi*

*tür niteleyicisi-Listele*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi-liste* *tür niteleyicisi*

*Tür belirleyicisi* , nesne türünü verir; bu, herhangi bir temel, yapı veya birleşim türü olabilir. İşaretçi değişkenleri Ayrıca işlevler, diziler ve diğer işaretçileri işaret edebilir. (Daha karmaşık işaretçi türlerini bildirme ve yorumlama hakkında daha fazla bilgi için, [daha karmaşık Bildirimcilerin yorumlanması](../c-language/interpreting-more-complex-declarators.md)bölümüne bakın.)

*Tür belirleyicisi* yaparak **`void`** , işaretçinin başvurduğu türün belirtimini erteleyebilirsiniz. Böyle bir öğe "işaretçi" olarak adlandırılır **`void`** ve olarak yazılır `void *` . *Void* işaretçisi olarak belirtilen bir değişken, herhangi bir türdeki bir nesneyi işaret etmek için kullanılabilir. Ancak, işaretçi üzerinde veya işaret ettiği nesne üzerinde birçok işlemi gerçekleştirmek için, işaret ettiği türün her işlem için açıkça belirtilmesi gerekir. (Türündeki **`char`** <strong>\*</strong> değişkenler ve türü **`void`** <strong>\*</strong> , tür atama olmadan atama uyumludur.) Bu tür dönüştürme bir tür cast ile gerçekleştirilebilir (daha fazla bilgi için bkz. [tür dönüştürme dönüştürmeleri](../c-language/type-cast-conversions.md) .).

*Tür niteleyicisi* veya ya da **`const`** **`volatile`** her ikisi birden olabilir. Bunlar sırasıyla, işaretçinin programın kendisi tarafından değiştirilemeyeceğini ( **`const`** ) veya işaretçinin meşru bir şekilde program denetiminin () dışında bir işlem tarafından değiştirilmesini belirler **`volatile`** . (Ve hakkında daha fazla bilgi için bkz. [Tür niteleyicileri](../c-language/type-qualifiers.md) **`const`** **`volatile`** .)

*Bildirimci* , değişkeni adlandırır ve bir tür değiştiricisi içerebilir. Örneğin, *bildirimci* bir diziyi temsil ediyorsa, işaretçinin türü dizi işaretçisi olacak şekilde değiştirilir.

Yapı, birleşim veya numaralandırma türünü tanımladıktan önce bir yapı, birleşim veya numaralandırma türüne yönelik bir işaretçi bildirebilirsiniz. Aşağıdaki örneklerde gösterildiği gibi, yapıyı veya UNION etiketini kullanarak işaretçiyi bildirirsiniz. Derleyicinin, işaretçi değişkeni için alan ayırmak üzere yapının veya birleşimin boyutunu bilmesi gerekmiyorsa bu tür bildirimlere izin verilir.

## <a name="examples"></a>Örnekler

Aşağıdaki örneklerde işaretçi bildirimleri gösterilmektedir.

```
char *message; /* Declares a pointer variable named message */
```

*İleti* işaretçisi türünde bir değişkene işaret eder **`char`** .

```
int *pointers[10];  /* Declares an array of pointers */
```

*İşaretçiler* dizisinde 10 öğe vardır; her öğe, türünde bir değişkene yönelik bir işaretçidir **`int`** .

```
int (*pointer)[10]; /* Declares a pointer to an array of 10 elements */
```

*İşaretçi* değişkeni 10 öğe içeren bir diziye işaret eder. Bu dizideki her öğenin türü vardır **`int`** .

```
int const *x;      /* Declares a pointer variable, x,
                      to a constant value */
```

*X* işaretçisi farklı bir değere işaret etmek üzere değiştirilebilir **`int`** , ancak bunun işaret ettiği değer değiştirilemez.

```
const int some_object = 5 ;
int other_object = 37;
int *const y = &fixed_object;
int volatile *const z = &some_object;
int *const volatile w = &some_object;
```

Bu bildirimlerden *y* değişkeni, bir değere sabit bir işaretçi olarak bildirilmiştir **`int`** . İşaret ettiği değer değiştirilebilir, ancak işaretçinin kendisi her zaman aynı konuma işaret etmelidir: *fixed_object* adresi. Benzer şekilde, *z* sabit bir işaretçidir, ancak aynı zamanda **`int`** değeri program tarafından değiştirilemeyen bir değere işaret etmek için de bildirilmiştir. Ek tanımlayıcı, **`volatile`** *z* tarafından işaret edilen **const int** değerinin program tarafından değiştirilemeyeceğini, meşru bir şekilde programla aynı şekilde çalışan bir işlem tarafından değiştirilmesini gösterir. *W* bildirimi programın işaret ettiği değeri değiştiremez ve programın işaretçiyi değiştiremez.

```
struct list *next, *previous; /* Uses the tag for list */
```

Bu örnek, yapı türü *listesini* işaret eden *Next* ve *Previous* olmak üzere iki işaretçi değişkeni bildirir. *Liste türü tanımı* bildirimle aynı görünürlüğe sahip olduğu sürece, bu bildirim *liste* yapı türü tanımından önce görünebilir (sonraki örneğe bakın).

```
struct list
{
    char *token;
    int count;
    struct list *next;
} line;
```

Değişken *çizgisi* , *list* adlı yapı türüne sahiptir. *Liste* yapısı türü üç üyeye sahiptir: ilk üye bir değere işaretçidir, ikincisi ise bir **`char`** **`int`** değerdir ve üçüncüsü ise başka bir *liste* yapısına yönelik bir işaretçidir.

```
struct id
{
    unsigned int id_no;
    struct name *pname;
} record;
```

Değişken *kaydının* yapı türü *kimliği* vardır. *Pname* 'in *Name* adlı başka bir yapı türünün işaretçisi olarak bildirildiği unutulmamalıdır. Bu bildirim *ad* türü tanımlanmadan önce görünebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimciler ve değişken bildirimleri](../c-language/declarators-and-variable-declarations.md)
