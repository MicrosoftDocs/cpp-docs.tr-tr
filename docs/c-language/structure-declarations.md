---
title: "Yapı bildirimleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- structure declarations
- anonymous structures
- types [C], declarations
- structure members
- embedded structures
ms.assetid: 5be3be77-a236-4153-b574-7aa77675df7f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c91c3834b5a4647f7c9cd41820dc04e5597277f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="structure-declarations"></a>Yapı Bildirimleri
Bir "yapı bildirimi" bir tür adları ve bir dizi farklı olabilir ("üye" veya "alanlar" yapısı denir) değişken değerleri belirtir. Bir "etiketi," isteğe bağlı bir tanımlayıcısından yapısı türünün adı sağlar ve bir yapı türüne sonraki başvurular kullanılabilir. Bu yapı türünde bir değişken, türü tarafından tanımlanan tüm dizisi içerir. C yapılarda diğer dillerde "kayıtlar" olarak bilinen türleri benzerdir.  
  
## <a name="syntax"></a>Sözdizimi  
 *yapı veya birleşim belirleyici*:  
 *struct veya union tanımlayıcı* kabul**{** *yapısı bildirimi listesi* **}**  
  
 *struct veya union tanımlayıcısı*  
  
 *struct veya union*:  
 **yapısı**  
  
 **birleşim**  
  
 *Yapı bildirimi listesi*:  
 *Yapı bildirimi*  
  
 *Yapı bildirimi listesi yapısı-bildirimi*  
  
 Yapı içerik olarak tanımlanır  
  
 *Yapı bildirimi*:  
 *belirleyici niteleyici listesinde yapısı bildirimcisi listesi***;**   
  
 *belirleyici niteleyici listesinde*:  
 *tür belirteci belirleyici niteleyicisi listesi* iptal et  
  
 *tür niteleyicisi belirleyici niteleyicisi listesi* iptal et  
  
 *Yapı bildirimcisi listesi*:  
 *Yapı bildirimcisi*  
  
 *Yapı bildirimcisi listesi***,***yapısı bildirimcisi*   
  
 *Yapı bildirimcisi*:  
 `declarator`  
  
 Yapı türü bildirimi bir yapı için alanı kenara ayarlı değil. Bu yalnızca bir sonraki bildirimleri yapısı değişkenlerin şablonudur.  
  
 Önceden tanımlı bir *tanımlayıcısı* (etiketi), başka bir yerde tanımlanmış bir yapı türüne başvurmak için kullanılabilir. Bu durumda, *yapısı bildirimi listesi* tanımı görünür olduğu sürece yinelenemez. Bir yapı türüne tanımlanmadan önce yapılar ve yapı türleri için tür tanımları işaretçileri bildirimlerini yapısı etiketi kullanabilirsiniz. Ancak, yapı tanımı alanların boyutu gerçek kullanımı önce karşılaştı gerekir. Bu, tür ve tür etiketi eksik bir tanımıdır. Bu tanım tamamlanması bir tür tanımı daha sonra aynı kapsam içinde yer almalıdır.  
  
 *Yapısı bildirimi listesi* yapısı üyelerinin adlarını ve türlerini belirtir. A *yapısı bildirimi listesi* bağımsız değişkeni, bir veya daha fazla değişken ya da bit alanı bildirimleri içerir.  
  
 Bildirilen her bir değişken *yapısı bildirimi listesi* yapısı türünün bir üyesi tanımlanır. Değişken bildirimleri içinde *yapısı bildirimi listesi* bildirimleri depolama sınıfı tanımlayıcıları veya başlatıcıları içeremez dışında bu bölümde ele alınan diğer değişken bildirimleri olarak aynı biçime sahip. Yapı üyeleri türü dışında herhangi bir değişken türünün olabilir `void`, tamamlanmamış bir tür veya işlev türü.  
  
 Üye göründüğü yapısı türün bildirilemez. Ancak, bir üye bir etiket bir yapı türüne sahip sürece göründüğü yapısı türü için bir işaretçi olarak bildirilebilir. Bu bağlantılı yapıları listesi oluşturmanıza olanak sağlar.  
  
 Yapılar, diğer tanımlayıcıları aynı kapsamı izleyin. Yapı tanımlayıcıları diğer yapısı, union ve numaralandırma etiketleri aynı görünürlük ile farklı olması gerekir.  
  
 Her *yapısı bildirimi* içinde bir *yapısı bildirimi listesi* listenin içinde benzersiz olmalıdır. Tanımlayıcı ancak adları bir *yapısı bildirimi listesi* sıradan değişken adları veya diğer yapı bildirimi listelerinde tanımlayıcıları farklı olması gerekmez.  
  
 Dosya kapsam düzeyinde olarak bildirilen gibi sorgulamanıza iç içe geçmiş yapılar da erişilebilir. Örneğin, bu bildirim verilen:  
  
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
  
 Bu bildirimler her ikisi de yasal şunlardır:  
  
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
  
 `employee` Yapısının üç üye: `name`, `id`, ve `class`. `name` Üyesidir 20 öğeli bir dizi ve `id` ve `class` basit üyeleriyle olan `int` ve **uzun** sırasıyla yazın. Tanımlayıcı `employee` yapısı tanımlayıcısıdır.  
  
```  
struct employee student, faculty, staff;  
```  
  
 Bu örnekte, üç yapı değişkenleri tanımlanır: `student`, `faculty`, ve `staff`. Her yapısı üç üyeleri aynı listesine sahiptir. Üyeleri bir yapı türüne sahip bildirilen `employee`, önceki örnekte tanımlı.  
  
```  
struct           /* Defines an anonymous struct and a */  
{                /* structure variable named complex  */  
    float x, y;  
} complex;  
```  
  
 `complex` Yapısının iki üyeleriyle **float** türü, `x` ve `y`. Bir yapı türüne hiçbir etiketi vardır ve bu nedenle adlandırılmamış veya anonim olur.  
  
```  
struct sample   /* Defines a structure named x */  
{  
    char c;  
    float *pf;  
    struct sample *next;  
} x;  
```  
  
 İlk iki yapı üyesi olan bir `char` değişkeni ve bir işaretçi bir **float** değeri. Üçüncü üye `next`, tanımlanmakta yapısı türü için bir işaretçi olarak bildirilen (`sample`).  
  
 Adlı etiketi gerekmediğinde anonim yapılar yararlı olabilir. Bir bildirim yapısı hepsinin tanımladığında bu durumdur. Örneğin:  
  
```  
struct  
{  
    int x;  
    int y;  
} mystruct;  
```  
  
 Katıştırılmış yapılar genellikle anonim.  
  
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
  
 **Microsoft özel**  
  
 Derleyici boyutsuz veya sıfır boyutlu dizi bir yapı son üyesi olarak sağlar. Bu, sabit bir dizi boyutu çeşitli durumlarda kullanıldığında farklıysa yararlı olabilir. Böyle bir yapı bildirimi şöyle görünür:  
  
 `struct`*tanımlayıcısı***{** *bildirimleri kümesi* *türü dizi adı***[];};**  
  
 Boyutsuz dizileri yalnızca bir yapı son üyesi olarak görünebilir. Daha fazla üye herhangi kapsayan yapılarda bildirilir sürece boyutsuz dizi bildirimleri içeren yapıları diğer yapıları içinde iç içe. Bu tür yapıları dizileri izin verilmiyor. `sizeof` Bu türde bir değişken veya türünde kendisini uygulandığında işleci dizinin boyutu 0 varsayar.  
  
 Başka bir yapı veya birleşim üyeleri olduklarında yapı bildirimleri bildirimcisi de belirtilebilir. Alan adları kendilerini kapsayan yapısına öne çıkar. Örneğin, adsız yapısı şuna benzer:  
  
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
  
 Bkz: [yapı ve birleşim üyeleri](../c-language/structure-and-union-members.md) yapısı başvurular hakkında bilgi için.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve değişken bildirimleri](../c-language/declarators-and-variable-declarations.md)