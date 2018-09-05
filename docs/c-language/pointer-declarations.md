---
title: İşaretçi bildirimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- pointer declarations
- declarations, pointers
- const keyword [C]
- pointers, declarations
ms.assetid: 8b3b7fc7-f44d-480d-b6f9-cebe4e5462a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2870b2958f2e18b711ea568fdda2ae01d41e37f6
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752729"
---
# <a name="pointer-declarations"></a>İşaretçi Bildirimleri

A *işaretçi bildirimi* işaretçi değişkeninin adları ve değişkenin işaret ettiği nesnenin türünü belirtir. Bir işaretçi olarak bildirilen bir değişken, bir bellek adresi tutar.

## <a name="syntax"></a>Sözdizimi

*bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İşaretçi*<sub>iyileştirilmiş</sub> *doğrudan bildirimcisi*

*doğrudan bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**(** *bildirimci* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **[** *sabit-ifade*<sub>iyileştirilmiş</sub> **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **(** *parametre türü listesi* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci* **(** *tanımlayıcı listesi*<sub>iyileştirilmiş</sub> **)**

*İşaretçi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> *tür niteleyici listesi*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> *tür niteleyici listesi*<sub>iyileştirilmiş</sub> *işaretçi*

*tür niteleyici listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyici listesi* *tür niteleyicisi*

*Tür tanımlayıcısı* verir olabilen herhangi temel nesnesi, yapı veya birleşim türü türü. İşaretçi değişkenler, İşlevler, diziler ve diğer işaretçilerin da işaret edebilir. (Bildirme ve daha karmaşık işaretçi türleri yorumlama hakkında daha fazla bilgi için bkz [daha karmaşık Bildirimcileri yorumlama](../c-language/interpreting-more-complex-declarators.md).)

Yaparak *tür tanımlayıcısı* **void**, işaretçi başvurduğu türü belirtimi erteleyebilirsiniz. Böyle bir öğe olarak belirtilen bir "işaretçisine **void**" ve olarak yazılan `void *`. Bildirilen bir değişken için bir işaretçi olarak *void* herhangi bir türde bir nesneye işaret etmek için kullanılabilir. Ancak, işaret ettiği nesnenin veya işaretçinin üzerinde çoğu işlemi gerçekleştirmek için işaret ettiği tür açıkça her işlem için belirtilmelidir. (Türündeki değişkenler **char** <strong>\*</strong> ve türü **void** <strong>\*</strong> olmadan bir tür atama ile uyumlu olan Cast.) Bu tür dönüştürme bir tür ataması gerçekleştirilebilir (bkz [tür atama dönüştürmeleri](../c-language/type-cast-conversions.md) daha fazla bilgi için).

*Tür niteleyici* olabilir **const** veya **geçici**, veya her ikisini de. Bunlar, sırasıyla, program tarafından işaretçisi değiştirilemez belirtin (**const**), veya işaretçi de avustralya'dan arama program kontrolü bazı işlem tarafından değiştirilebilecek (**geçici**). (Bkz [tür niteleyicileri](../c-language/type-qualifiers.md) hakkında daha fazla bilgi için **const** ve **geçici**.)

*Bildirimci* can ve değişken adları içeren bir tür değiştiricisi. Örneğin, varsa *bildirimci* bir dizisine bir işaretçi olarak değiştirilmişse bir dizi, işaretçi türü temsil eder.

Yapı, birleşim veya numaralandırma türü tanımlamadan önce bir yapı, birleşim veya numaralandırma türü için bir işaretçi bildirebilirsiniz. İşaretçi, örnekte gösterildiği gibi yapı veya birleşim etiketini kullanarak bildirin. Derleyici yapı veya birleşim işaretçi değişkeninin için alan ayırmak için boyutu bilmeniz gerekmez çünkü bu tür bildirimleri izin verilir.

## <a name="examples"></a>Örnekler
Aşağıdaki örnekler, işaretçi bildirimleri gösterir.

```
char *message; /* Declares a pointer variable named message */
```

*İleti* sahip bir değişken işaretçisi işaret **char** türü.

```
int *pointers[10];  /* Declares an array of pointers */
```

*İşaretçileri* sahip 10 öğe dizisi; her öğeye sahip bir değişken işaretçisi **int** türü.

```
int (*pointer)[10]; /* Declares a pointer to an array of 10 elements */
```

*İşaretçi* 10 öğe olan bir dizi değişkeni işaret eder. Bu dizinin her öğesinde **int** türü.

```
int const *x;      /* Declares a pointer variable, x,
                      to a constant value */
```

İşaretçi *x* farklı bir işaret edecek şekilde değiştirilebilir **int** değeri, ancak değeri için BT noktaları değiştirilemez.

```
const int some_object = 5 ;
int other_object = 37;
int *const y = &fixed_object;
int volatile *const z = &some_object;
int *const volatile w = &some_object;
```

Değişken *y* bu bildirimlerinde için sabit bir işaretçi olarak bildirilen bir **int** değeri. İşaret için değer değiştirilebilir, ancak işaretçi her zaman aynı konuma işaret etmelidir: adresini *fixed_object*. Benzer şekilde, *z* sabit bir işaretçi olduğu halde işaret edecek şekilde de bildirilen bir **int** değeri program tarafından değiştirilemez. Ek tanımlayıcısı **geçici** rağmen belirten değeri **const int** işaret ettiği *z* değiştirilemez program tarafından yasal olabilir programın aynı anda çalışan bir işlem tarafından değiştirildi. Bildirimi *w* programı işaret değerini değiştiremez ve program işaretçi değiştiremezsiniz belirtir.

```
struct list *next, *previous; /* Uses the tag for list */
```

Bu örnek iki işaretçi değişkeni bildirir *sonraki* ve *önceki*, yapı türüne işaret *listesi*. Bu bildirim tanımı önce görünebilir *listesi* yapı türü (sonraki örneğe bakın), sürece *listesi* bildirimiyle aynı görünürlük türü tanımına sahip.

```
struct list
{
    char *token;
    int count;
    struct list *next;
} line;
```

Değişken *satırı* adlı yapı türüne sahip *listesi*. *Listesi* yapı türüne sahip üç üye: ilk üye işaretçisi olan bir **char** değerdir, ikinci bir **int** değer ve üçüncü bir işaretçidir başka bir *listesi* yapısı.

```
struct id
{
    unsigned int id_no;
    struct name *pname;
} record;
```

Değişken *kayıt* yapı türüne sahip *kimliği*. Unutmayın *sağlayıcı adı* adlı başka bir yapı türü için bir işaretçi olarak bildirilen *adı*. Bu bildirim önce görünebilir *adı* türü tanımlanmıştır.

## <a name="see-also"></a>Ayrıca Bkz.

[Bildirimler ve Değişken Bildirimleri](../c-language/declarators-and-variable-declarations.md)