---
title: C numaralandırma bildirimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declarations, enumerations
- define directive (#define), alternative to
- enumerators, declaring
- '#define directive, alternative to'
- named constants, enumeration declarations
- declaring enumerations
ms.assetid: bd18f673-4dda-4bc1-92fd-d1ce10074910
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 697e4f37c8a59c40df80e29ff89f2021f61fb468
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389747"
---
# <a name="c-enumeration-declarations"></a>C Numaralandırma Bildirimleri
Numaralandırma adlandırılmış tamsayı sabitleri kümesinden oluşur. Bir numaralandırma türü bildirimi (isteğe bağlı) numaralandırması etiketin adını verir ve adlandırılmış tamsayı tanımlayıcıları kümesini tanımlar ("numaralandırma,"Numaralandırıcı sabitleri,"Ayarla" adlı "numaralandırıcılar" veya "üye"). Numaralandırma türü sahip bir değişken, türü tarafından tanımlanan numaralandırma kümesinin değerlerden biri depolar.  
  
 Değişkenleri `enum` türü ifadeleri dizinini ve tüm aritmetik ve ilişkisel işleçleri işlenenleri olarak kullanılabilir. Numaralandırmalar sağlamak için bir alternatif `#define` değerleri sizin için oluşturulan ve normal ölçüm kuralları uyma avantajları ile önişlemci yönergesi.  
  
 ANSI C, her zaman bir numaralandırıcı sabiti değerini tanımlayan bir ifade olması `int` yazın; bu nedenle, tek bir için gerekli depolama alanına bir numaralandırma değişkeni ile ilişkilendirilmiş depolama `int` değeri. Bir numaralandırma sabit veya numaralandırılmış türde bir değer kullanılabilir herhangi bir yerden bir tamsayı ifade C dil izin verir.  
  
## <a name="syntax"></a>Sözdizimi  
 *Liste belirticisi*:  
 **Enum***tanımlayıcısı* kabul **{** *numaralandırıcı listesi* **}**   
  
 **Enum***tanımlayıcısı*  
  
 İsteğe bağlı *tanımlayıcısı* tarafından tanımlanan numaralandırma türü adları *numaralandırıcı listesi*. Bu tanımlayıcı, çoğunlukla listesi tarafından belirtilen numaralandırması "etiketi" adı verilir. Formun türü tanımlayıcısı  
  
```  
  
enum  
identifier  
{  
enumerator-list  
}  
  
```  
  
 bildirir *tanımlayıcısı* tarafından belirtilen numaralandırması etiket olması *numaralandırıcı listesi* nonterminal. *Numaralandırıcı listesi* "Numaralandırıcı içerik." tanımlar *Numaralandırıcı listesi* aşağıda ayrıntılı olarak açıklanmıştır.  
  
 Bir etiketi bildirimi etiket kullanan ancak atlayın görünür, sonraki bildirimleri ise *numaralandırıcı listesi* daha önce bildirilen numaralandırılmış türünü belirtin. Etiket için tanımlanan numaralandırma türü başvurması gerekir ve bu sabit listesi türü geçerli kapsamda olmalıdır. Numaralandırma türü başka bir yerde tanımlamış *numaralandırıcı listesi* bu bildirimi görünmez. Bildirimleri türlerinin numaralandırmalar türetilmiş ve `typedef` numaralandırma türü tanımlanmadan önce Numaralandırma türleri için bildirimleri numaralandırması etiketi kullanabilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
 *Numaralandırıcı listesi*:  
 *Numaralandırıcı*  
  
 *Numaralandırıcı listesi* **,**  `enumerator`  
  
 `enumerator`:  
 *Numaralandırma sabiti*  
  
 *Numaralandırma sabiti***=***sabit ifadesi*  
  
 *Numaralandırma sabiti*:  
 *Tanımlayıcı*  
  
 Her *numaralandırma sabiti* içinde bir *numaralandırma listesini* numaralandırma kümesi değerini adları. Varsayılan olarak, ilk *numaralandırma sabiti* değeri 0 ile ilişkilidir. Sonraki *numaralandırma sabiti* listede değeri ile ilişkilendirilen ( *sabit ifadesi* + 1) açıkça başka bir değerle ilişkilendirmenizi sürece. Adı bir *numaralandırma sabiti* değerine denktir.  
  
 Kullanabileceğiniz *numaralandırma sabiti sabiti deyim =* varsayılan değerleri bir dizi geçersiz kılmak için. Bu nedenle, varsa *numaralandırma sabiti sabiti deyim =* görünür *numaralandırıcı listesi*, *numaralandırma sabiti* tarafındanverilendeğer,ilişkilendirilmiş.*sabit ifadesi*. *Sabit ifadesi* olmalıdır `int` yazın ve negatif olabilir.  
  
 Aşağıdaki kuralları bir numaralandırma kümesi üyeleri için geçerlidir:  
  
-   Bir numaralandırma kümesi yinelenen sabit değerler içerebilir. Örneğin, belki de adlı değeri 0 ile iki farklı tanımlayıcılar ilişkilendirmek `null` ve `zero`, aynı kümesi içinde.  
  
-   Numaralandırma listesini tanımlayıcılarında sıradan değişken adları ve tanımlayıcıları diğer numaralandırması listelerinde de dahil olmak üzere aynı görünürlük ile aynı kapsamda diğer tanımlayıcıları farklı olması gerekir.  
  
-   Numaralandırma etiketleri normal ölçüm kuralları uymaktadır. Bunlar, diğer numaralandırması, yapı ve birleşim etiketleriyle aynı görünürlük farklı olmalıdır.  
  
## <a name="examples"></a>Örnekler  
 Bu örneklerde numaralandırma bildirimleri gösterilmektedir:  
  
```  
enum DAY            /* Defines an enumeration type    */  
{  
    saturday,       /* Names day and declares a       */  
    sunday = 0,     /* variable named workday with    */   
    monday,         /* that type                      */  
    tuesday,  
    wednesday,      /* wednesday is associated with 3 */  
    thursday,  
    friday  
} workday;  
```  
  
 Değer 0 ile ilişkili `saturday` varsayılan olarak. Tanımlayıcı `sunday` açıkça 0 olarak ayarlayın. Kalan tanımlayıcılar 1 ile 5 arasındaki değerleri varsayılan olarak verilir.  
  
 Bu örnekte, bir değer kümesinden `DAY` değişkenine atanan `today`.  
  
```  
enum DAY today = wednesday;  
```  
  
 Numaralandırma sabiti adını değer atamak için kullanılır. Bu yana `DAY` numaralandırma türü önceden olarak bildirildiğini, yalnızca numaralandırma etiketi `DAY` gereklidir.  
  
 Açıkça bir tamsayı değeri numaralandırılmış veri türü değişkenine atamak için bir cast türünü kullanın:  
  
```  
workday = ( enum DAY ) ( day_value - 1 );  
```  
  
 Bu atama C'de önerilir ancak gerekli değildir.  
  
```  
enum BOOLEAN  /* Declares an enumeration data type called BOOLEAN */  
{  
    false,     /* false = 0, true = 1 */  
    true   
};   
  
enum BOOLEAN end_flag, match_flag; /* Two variables of type BOOLEAN */  
```  
  
 Bu bildirim ayrıca olarak belirtilebilir.  
  
```  
enum BOOLEAN { false, true } end_flag, match_flag;\  
```  
  
 veya as  
  
```  
enum BOOLEAN { false, true } end_flag;  
enum BOOLEAN match_flag;  
```  
  
 Bu değişkenler kullanan bir örnek şuna benzeyebilir:  
  
```  
if ( match_flag == false )  
    {  
     .  
     .   /* statement */   
     .  
    }  
    end_flag = true;  
```  
  
 Adlandırılmamış Numaralandırıcı veri türleri de bildirilebilir. Veri türünün adı atlanmış ancak değişkenleri bildirilebilir. Değişkeni `response` tanımlanan türünde bir değişken değil:  
  
```  
enum { yes, no } response;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit Listeleri](../cpp/enumerations-cpp.md)