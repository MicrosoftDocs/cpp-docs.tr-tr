---
title: Yapı bildirimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- structure declarations
- anonymous structures
- types [C], declarations
- structure members
- embedded structures
ms.assetid: 5be3be77-a236-4153-b574-7aa77675df7f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ffb239db12111f80e894c68cff568338bb3ed038
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207276"
---
# <a name="structure-declarations"></a>Yapı Bildirimleri
Bir "yapı bildirimi" bir tür adları ve bir dizi farklı türlere sahip olabilen ("üye" ya da yapının "alanları" olarak adlandırılır) değişken değerleri belirtir. Bir "etiket" adlı isteğe bağlı bir tanımlayıcı, yapı türü adını verir ve sonraki başvurularda yapı türü için kullanılabilir. Bu yapı türünde bir değişken türü tarafından tanımlanan tüm dizisi içerir. Yapıları C, diğer dillerdeki "kayıt" olarak bilinen türleri benzerdir.  
  
## <a name="syntax"></a>Sözdizimi  
 *struct veya union tanımlayıcısı*:  
 *yapı veya birleşim tanımlayıcısı* iyileştirilmiş **{** *yapı bildirim listesi* **}**  
  
 *yapı veya birleşim tanımlayıcısı*  
  
 *yapı veya birleşim*:  
 **struct**  
  
 **birleşim**  
  
 *Yapı bildirim listesi*:  
 *Yapı bildirimi*  
  
 *Yapı bildirim listesi yapı bildirimi*  
  
 Yapı içeriği olarak tanımlanır  
  
 *Yapı bildirimi*:  
 *Belirleyicisi niteleyici listesinin yapı bildirimci listesi***;**   
  
 *Belirleyicisi niteleyici listesinin*:  
 *tür belirticisi tanımlayıcısı niteleyici listesi* iyileştirilmiş  
  
 *tür niteleyicisi tanımlayıcısı niteleyici listesi* iyileştirilmiş  
  
 *Yapı-declarator-list*:  
 *Yapı bildirimcisi*  
  
 *Yapı-declarator-list***,***yapı bildirimcisi*   
  
 *Yapı-declarator*:  
 `declarator`  
  
 Bir yapı türü bildirimini alan bir yapı için kenara ayarlı değil. Yapı değişkenleri, sonraki Bildirimlerde için yalnızca bir şablon var.  
  
 Önceden tanımlı bir *tanımlayıcı* (etiketi), başka yerde tanımlanmış bir yapı türü başvurmak için kullanılabilir. Bu durumda, *yapı bildirim listesi* tanımı görünür olduğu sürece yinelenemez. Yapı türü tanımlanmadan önce işaretçileri yapıların ve yapı türleri için tür tanımları, bildirimleri yapısı etiketini kullanabilirsiniz. Ancak, yapı tanımı alanların boyutunu gerçek kullanımı önce karşılaştı gerekir. Bu, tür ve tür etiketi eksik bir tanımıdır. Bu tanımı tamamlanması bir tür tanımı, daha sonra aynı kapsam içinde yer almalıdır.  
  
 *Yapı bildirim listesi* yapı üyelerinin adları ve türlerini belirtir. A *yapı bildirim listesi* bağımsız değişken içeren bir veya daha fazla değişken veya bit alanı bildirimleri.  
  
 Bildirilen her bir değişken *yapı bildirim listesi* yapı türünün bir üyesi olarak tanımlanır. Değişken bildirimlerinde *yapı bildirim listesi* bildirimleri depolama sınıfı tanımlayıcıları veya başlatıcılar bulunamaz dışında bu bölümde ele alınan diğer değişken bildirimleri aynı biçime sahip. Yapı üyeleri türü dışındaki herhangi bir değişken türü olabilir `void`, tamamlanmamış bir türü veya bir işlev türü.  
  
 Bir üye türünü göründüğü yapısı bildirilemez. Ancak, bir üye yapı türüne sahip bir etiket sürece göründüğü yapı türü işaretçisi olarak bildirilebilir. Bu, bağlı yapıların listesini oluşturmanıza olanak sağlar.  
  
 Yapılar, diğer tanımlayıcıları aynı kapsam izleyin. Yapı tanımlayıcıları, diğer yapı, birleşim ve numaralandırma etiketleri aynı görünürlüğü farklı olmalıdır.  
  
 Her *yapı bildirimi* içinde bir *yapı bildirim listesi* liste içinde benzersiz olmalıdır. Ancak, tanımlayıcı adları bir *yapı bildirim listesi* sıradan değişken adları veya diğer yapı bildirimi listelerinde tanımlayıcıları benzersiz olması gerekmez.  
  
 Bunlar dosya kapsamı düzeyinde bildirilen gibi sorgulamanıza iç içe geçmiş yapılar da erişilebilir. Örneğin, bu bildirim verilen:  
  
```  
struct a  
{  
    int x;  
    struct b  
    {  
      int y;  
    } var2;  
} var1;  
```  
  
 Bu bildirimler, her ikisi de yasal şunlardır:  
  
```  
struct a var3;  
struct b var4;  
```  
  
## <a name="examples"></a>Örnekler  
 Bu örneklerde, yapı bildirimleri gösterilmektedir:  
  
```  
struct employee   /* Defines a structure variable named temp */  
{  
    char name[20];  
    int id;  
    long class;  
} temp;  
```  
  
 `employee` Yapısının üç üye: `name`, `id`, ve `class`. `name` 20 öğeli bir dizi üyesidir ve `id` ve `class` ile basit üyeleridir `int` ve **uzun** sırasıyla yazın. Tanımlayıcı `employee` yapısı tanımlayıcısıdır.  
  
```  
struct employee student, faculty, staff;  
```  
  
 Bu örnek, üç yapı değişkenleri tanımlar: `student`, `faculty`, ve `staff`. Her yapı, üç üye aynı listesine sahiptir. Yapı türü için bildirilen üyeler `employee`, önceki örnekte tanımlı.  
  
```  
struct           /* Defines an anonymous struct and a */  
{                /* structure variable named complex  */  
    float x, y;  
} complex;  
```  
  
 `complex` Yapıya sahip iki üyeleriyle **float** türü `x` ve `y`. Yapı türü etiketi yok ve bu nedenle adlandırılmamış ya da anonim.  
  
```  
struct sample   /* Defines a structure named x */  
{  
    char c;  
    float *pf;  
    struct sample *next;  
} x;  
```  
  
 Yapı ilk iki üyesi olan bir `char` değişkeni ve işaretçi bir **float** değeri. Üçüncü üye `next`, tanımlanan yapı türü işaretçisi olarak bildirilebilir (`sample`).  
  
 Anonim yapılar, adlı etiket gerekmediğinde yararlı olabilir. Bir bildirim yapısı hepsinin tanımladığında durum budur. Örneğin:  
  
```  
struct  
{  
    int x;  
    int y;  
} mystruct;  
```  
  
 Katıştırılmış yapılar, genellikle anonim olacaktır.  
  
```  
struct somestruct  
{  
    struct    /* Anonymous structure */  
    {  
        int x, y;  
    } point;  
    int type;  
} w;  
```  
  
 **Microsoft'a özgü**  
  
 Derleyicinin, boyutsuz veya sıfır boyutlu dizi bir yapının son üye olarak sağlar. Bu, sabit bir dizinin boyutu çeşitli durumlarda kullanıldığında farklıysa yararlı olabilir. Böyle bir yapının bildirimi şöyle görünür:  
  
**Yapı** *tanımlayıcı* **{** *bildirimleri kümesi* *türü* <em>dizi adı</em> **\[]; };**  
  
 Boyutsuz diziler yalnızca bir yapının son üyesi olarak görünür. Daha fazla üye kapsayan tüm yapıları, bildirilen sürece boyutsuz bir dizi bildirimleri içeren yapıları diğer yapıları yuvalanabilir. Bu tür bir yapı dizileri izin verilmez. `sizeof` Türün kendisine veya bu türden bir değişkene uygulandığında işleç, dizinin boyutu 0 varsayar.  
  
 Başka bir yapı veya birleşim üyesi olduklarında, yapı bildirimleri bir bildirimcide de belirtilebilir. Alan adları, kapsayan yapısına yükseltilir. Örneğin, bir adsız yapı şöyle görünür:  
  
```  
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
  
 Bkz: [yapı ve birleşim üyeleri](../c-language/structure-and-union-members.md) yapısı başvuruları hakkında daha fazla bilgi için.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve Değişken Bildirimleri](../c-language/declarators-and-variable-declarations.md)