---
title: İç İşlevler
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _String_length_
- _Param_
- _Curr_
- _Old_
- _Nullterm_length_
- _Inexpressible_
ms.assetid: adf29f8c-89fd-4a5e-9804-35ac83e1c457
ms.openlocfilehash: 0aed625cfa17c75bbfb36506436e9e2c52a7a13b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216680"
---
# <a name="intrinsic-functions"></a>İç İşlevler

SAL içindeki bir ifade, yan etkileri olmayan bir ifade olan bir C/C++ ifadesi olabilir; Örneğin, + +,--, ve işlev çağrılarının hepsi bu bağlamda yan etkilere sahiptir.  Ancak, SAL ifadelerde kullanılabilecek bazı işlev benzeri nesneler ve bazı ayrılmış semboller sağlar. Bunlar *iç işlevler*olarak adlandırılır.

## <a name="general-purpose"></a>Genel Amaçlı

Aşağıdaki ınstrinsic işlev ek açıklamaları SAL için genel yardımcı program sağlar.

|Ek Açıklama|Açıklama|
|----------------|-----------------|
|`_Curr_`|Şu anda açıklanmakta olan nesne için bir eş anlamlı.  `_At_`Ek açıklama kullanımda olduğunda, `_Curr_` ilk parametresiyle aynı olur `_At_` .  Aksi takdirde, ek açıklamanın sözcüksel olarak ilişkilendirildiği parametre veya tam işlev/dönüş değeridir.|
|`_Inexpressible_(expr)`|Bir arabelleğin boyutunun, bir ek açıklama ifadesi kullanılarak temsil edilebilmesi için çok karmaşık olduğu, örneğin bir girdi veri kümesi tarayarak ve ardından seçilen Üyeler sayımının hesaplandığı bir durumu ifade eder.|
|`_Nullterm_length_(param)`|`param`Arabellekteki öğelerin sayısı, bir null Sonlandırıcı dahil değildir. Toplama olmayan, void olmayan türdeki herhangi bir arabelleğe uygulanabilir.|
|`_Old_(expr)`|Önkoşula göre değerlendirildiğinde, `_Old_` giriş değerini döndürür `expr` .  Koşul sonrası değerlendirildiğinde değeri, `expr` önkoşullardan değerlendirildiği gibi döndürür.|
|`_Param_(n)`|`n`1 ile arasında sayarak `n` ve `n` sabit bir integral sabiti olan bir işleve olan TH parametresi. Parametre adlandırılmışsa, bu ek açıklama parametreye adına göre erişmek için aynıdır. **Note:** `n` bir üç nokta tarafından tanımlanan konumsal parametrelere başvurabilir veya adların kullanıldığı işlev Prototiplerde kullanılabilir.  |
|`return`|C/C++ ayrılmış anahtar sözcüğü, **`return`** bir işlevin dönüş değerini göstermek IÇIN Sal ifadesinde kullanılabilir.  Değer yalnızca gönderi durumunda kullanılabilir; Bu, ön durumunda kullanmak için bir sözdizimi hatasıdır.|

## <a name="string-specific"></a>Dizeye özgü

Aşağıdaki iç işlev ek açıklamaları dizelerin düzenlenmesini etkinleştirir. Bu işlevlerin dört dördü de aynı amaca sahiptir: null Sonlandırıcı 'dan önce bulunan türdeki öğelerin sayısını döndürmek için. Farklılıklar, başvurulan öğelerdeki veri türleridir. Karakterlerden oluşan null ile sonlandırılmış bir arabelleğin uzunluğunu belirtmek isterseniz, `_Nullterm_length_(param)` önceki bölümde yer alan ek açıklamayı kullanın.

|Ek Açıklama|Açıklama|
|----------------|-----------------|
|`_String_length_(param)`|`param`dizedeki öğe sayısı olan, ancak bir null Sonlandırıcı dahil değil. Bu ek açıklama, karakter dizesi türleri için ayrılmıştır.|
|`strlen(param)`|`param`dizedeki öğe sayısı olan, ancak bir null Sonlandırıcı dahil değil. Bu ek açıklama, karakter dizileri üzerinde kullanılmak üzere ayrılmıştır ve C çalışma zamanı işlevine [strlen ()](/cpp/c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l)benzerdir.|
|`wcslen(param)`|`param`, bir null Sonlandırıcı (dahil değil) olan dizedeki öğe sayısıdır. Bu ek açıklama geniş karakter dizileri üzerinde kullanılmak üzere ayrılmıştır ve C çalışma zamanı işlevine [wcslen ()](/cpp/c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l)benzerdir.|

## <a name="see-also"></a>Ayrıca bkz.

- [C/C++ Kod Hatalarını Azaltmak için SAL Ek Açıklamalarını Kullanma](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [SAL'ı Anlama](../code-quality/understanding-sal.md)
- [İşlev Parametrelerini ve Dönüş Değerlerini Açıklama](../code-quality/annotating-function-parameters-and-return-values.md)
- [İşlev Davranışını Yorumlama](../code-quality/annotating-function-behavior.md)
- [Yapıları ve Sınıfları Yorumlama](../code-quality/annotating-structs-and-classes.md)
- [Kilitlenme Davranışını Yorumlama](../code-quality/annotating-locking-behavior.md)
- [Açıklamanın Ne Zaman ve Nereye Uygulanacağını Belirtme](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [En İyi Yöntemler ve Örnekler](../code-quality/best-practices-and-examples-sal.md)
