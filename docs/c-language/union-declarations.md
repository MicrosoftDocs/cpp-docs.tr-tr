---
title: Birleşim bildirimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- unions
- union keyword [C], declarations
- variant records
ms.assetid: 978c6165-e0ae-4196-afa7-6d94e24f62f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d8c52752c1e05cb3c9f2b18a827fb493ba503ad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="union-declarations"></a>Birleşim Bildirimleri
"Birleşim bildirim" bir dizi değişken değerleri ve isteğe bağlı olarak, UNION adlandırma etiket belirtir. Değişken değerleri UNION "üye" olarak adlandırılır ve farklı olabilir. Birleşimler, diğer dillerde "değişken kayıtlar" benzerdir.  
  
## <a name="syntax"></a>Sözdizimi  
 *yapı veya birleşim belirleyici*:  
 *struct veya union tanımlayıcı* kabul **{** *yapısı bildirimi listesi* **}**  
  
 *struct veya union tanımlayıcısı*  
  
 *struct veya union*:  
 **struct**  
  
 **birleşim**  
  
 *Yapı bildirimi listesi*:  
 *Yapı bildirimi*  
  
 *Yapı bildirimi listesi yapısı-bildirimi*  
  
 Birleşim içerik olarak tanımlanır  
  
 *Yapı bildirimi*:  
 *belirleyici niteleyici listesinde yapısı bildirimcisi listesi***;**  
  
 *belirleyici niteleyici listesinde*:  
 *tür belirteci belirleyici niteleyicisi listesi* iptal et  
  
 *tür niteleyicisi belirleyici niteleyicisi listesi* iptal et  
  
 *Yapı bildirimcisi listesi*:  
 *Yapı bildirimcisi*  
  
 *Yapı bildirimcisi listesi***,***yapısı bildirimcisi*   
  
 Sahip bir değişken **UNION** türü bu türü tarafından tanımlanan değerlerden biri depolar. Aynı kurallar yapı ve birleşim bildirimleri kapsar. Birleşimler alanları bit.  
  
 Birleşimler üyeleri yazın, tamamlanmamış bir türü olamaz `void`, veya işlev türü. Bu nedenle üyeleri UNION örneği olamaz, ancak bildirilen birleşim türü işaretçileri olabilir.  
  
 Bir birleşim türü bildirimi yalnızca bir şablon. Değişkeni bildirilmiş kadar bellek ayrılmış değil.  
  
> [!NOTE]
>  İki tür birleşimi bildirilmiş ve bir değer depolanır, ancak birleşimi bir türü ile erişilen, sonuçları güvenilir değil. Örneğin, bir birleşimi **float** ve `int` bildirilmedi. A **float** değeri depolanır, ancak programı daha sonra değeri olarak erişen bir `int`. Böyle bir durumda, iç depolaması ve değeri değişir **float** değerleri. Tamsayı değeri güvenilir olmaz.  
  
## <a name="examples"></a>Örnekler  
 Birleşimler örnekleri verilmiştir:  
  
```  
union sign   /* A definition and a declaration */  
{  
    int svar;  
    unsigned uvar;  
} number;  
```  
  
 Bu örnek bir birleşim değişkeniyle tanımlar `sign` yazın ve adlı bir değişken bildiren `number` iki üyesi olan: `svar`, imzalı bir tamsayı ve `uvar`, imzalanmamış tamsayı. Bu bildirim geçerli değeri verir `number` işaretli veya işaretsiz bir değer depolanmasını. Bu birleşim türü ile ilişkili etiket `sign`.  
  
```  
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
  
 `screen` Dizi 2.000 öğeleri içerir. Her dizi iki üye tek tek bir birleşim öğesidir: `window1` ve `screenval`. `window1` Üyesidir yapısı iki bit alanı üyeleriyle `icon` ve `color`. `screenval` Üye olduğu bir `int`. Belirli bir zamanda, her birleşim öğesi ya da tutan `int` tarafından temsil edilen `screenval` veya tarafından temsil edilen yapısı `window1`.  
  
 **Microsoft özel**  
  
 Başka bir yapı veya birleşim üyeleri olduklarında iç içe geçmiş birleşimler anonim olarak bildirilebilir. Bu, adsız UNION örneğidir:  
  
```  
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
  
 Birleşimler, genellikle belirli bir zamanda birleşim içinde bulunan veri türünü vermiş bir alan içeren bir yapı içinde yerleştirilir. Bu, bu tür bir birleşim için bir bildirim örneğidir:  
  
```  
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
  
 Bkz: [yapı ve birleşim üyeleri](../c-language/structure-and-union-members.md) birleşimler başvuran hakkında bilgi.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve Değişken Bildirimleri](../c-language/declarators-and-variable-declarations.md)