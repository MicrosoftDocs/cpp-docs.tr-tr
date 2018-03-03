---
title: "İşaretçi bildirimleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- pointer declarations
- declarations, pointers
- const keyword [C]
- pointers, declarations
ms.assetid: 8b3b7fc7-f44d-480d-b6f9-cebe4e5462a6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ac15c18ce3277e8268b6b4582de4046f5f74d64
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="pointer-declarations"></a>İşaretçi Bildirimleri
"İşaretçi bildirimi" işaretçi değişken adları ve değişken işaret ettiği nesne türünü belirtir. İşaretçi olarak bildirilen bir değişken bellek adresini tutar.  
  
## <a name="syntax"></a>Sözdizimi  
 *bildirimcisi*:  
 &nbsp;&nbsp;*İşaretçi*<sub>kabul</sub> *doğrudan bildirimcisi*  
  
 *doğrudan bildirimcisi*:  
 &nbsp;&nbsp;*tanımlayıcı*  
  
 &nbsp;&nbsp;**(** *bildirimcisi* **)**  
  
 &nbsp;&nbsp;*doğrudan bildirimcisi* **[** *sabit ifadesi*<sub>kabul</sub> **]**  
  
 &nbsp;&nbsp;*doğrudan bildirimcisi* **(** *parametre türü listesi* **)**  
  
 &nbsp;&nbsp;*doğrudan bildirimcisi* **(** *tanımlayıcı listesi*<sub>kabul</sub> **)**  
  
 *İşaretçi*:  
 &nbsp;&nbsp;**\****tür niteleyicisi listesi*<sub>iptal et</sub>  
  
 &nbsp;&nbsp;**\****tür niteleyicisi listesi*<sub>kabul</sub> *işaretçi*  
  
 *tür niteleyicisi listesi*:  
 &nbsp;&nbsp;*tür niteleyicisi*  
  
 &nbsp;&nbsp;*tür niteleyicisi listesi* *tür niteleyicisi*  
  
 *Tür belirteci* herhangi temel nesneyi, yapı veya birleşim türü türü sağlar. İşaretçi değişkenler, İşlevler, dizileri ve diğer işaretçileri da işaret edebilir. (Bildirme ve daha karmaşık işaretçi türleri yorumlama hakkında daha fazla bilgi için bkz [daha fazla karmaşık Bildirimcileri yorumlama](../c-language/interpreting-more-complex-declarators.md).)  
  
 Yaparak *tür belirteci* **void**, işaretçi başvurduğu türü belirtimi geciktirebilir. Bu tür bir öğe olarak adlandırılır bir "işaretçi **void**" ve olarak yazılmış `void *`. Bir değişken bildirilen bir işaretçi olarak *void* herhangi bir türde bir nesneye işaret etmek için kullanılabilir. Ancak, işaretçinin veya işaret ettiği nesne çoğu işlemler gerçekleştirmek üzere işaret ettiği türü açıkça her işlem için belirtilmelidir. (Türündeki değişkenler **char \***  ve türü **void \***  olan atama uyumlu bir tür cast.) Bu tür dönüştürme cast türü ile gerçekleştirilebilir (bkz [tür atama dönüşümleri](../c-language/type-cast-conversions.md) daha fazla bilgi için).  
  
 *Tür niteleyicisi* birini kullanabilir **const** veya **volatile**, veya her ikisini de. Bunlar, sırasıyla işaretçinin program tarafından değiştirilmiş belirtir (**const**), ya da işaretçiyi yasal denetimin programının ötesinde bazı işlemler tarafından değiştirilebilecek (**geçici**). (Bkz [tür niteleyicileri](../c-language/type-qualifiers.md) hakkında daha fazla bilgi için **const** ve **volatile**.)  
  
 *Bildirimcisi* can ve değişken adlarında bir tür değiştiricisi. Örneğin, varsa *bildirimcisi* bir dizi için bir işaretçi olarak bir dizi, işaretçi türü temsil değiştirdi.  
  
 Yapısı, UNION veya numaralandırma türü tanımlamadan önce yapısı, UNION veya numaralandırma türü için bir işaretçi bildirebilirsiniz. Aşağıdaki örneklerde gösterildiği gibi yapı veya birlik etiketini kullanarak işaretçiyi bildirin. Derleyici yapısı veya işaretçi değişkeni alan ayırmak için UNION boyutu bilmeniz gerek yoktur çünkü bu bildirimler izin verilir.  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki örneklerde işaretçi bildirimleri gösterilmektedir.  
  
```  
char *message; /* Declares a pointer variable named message */  
```  
  
 *İleti* işaretçi işaret sahip bir değişken **char** türü.  
  
```  
int *pointers[10];  /* Declares an array of pointers */  
```  
  
 *İşaretçileri* sahip 10 öğeleri dizisi; her öğeye sahip bir değişken için bir işaretçi **int** türü.  
  
```  
int (*pointer)[10]; /* Declares a pointer to an array of 10 elements */  
```  
  
 *İşaretçi* 10 öğeleri olan bir dizi değişkeni işaret eder. Dizideki her öğeye sahip **int** türü.  
  
```  
int const *x;      /* Declares a pointer variable, x,  
                      to a constant value */   
```  
  
 İşaretçinin *x* farklı bir işaret edecek şekilde değiştirilebilir **int** değeri, ancak hangi BT noktaları değiştirilemez değeri.  
  
```  
const int some_object = 5 ;  
int other_object = 37;  
int *const y = &fixed_object;  
int volatile *const z = &some_object;  
int *const volatile w = &some_object;  
```  
  
 Değişkeni *y* bu bildirimleri için sabit bir işaretçi olarak bildirilmiş bir **int** değeri. İşaret için değer değiştirilebilir, ancak işaretçi her zaman aynı konuma işaret etmelidir: adresini *fixed_object*. Benzer şekilde, *z* sabit işaretçi, ancak aynı zamanda işaret edecek şekilde bildirilmiş bir **int** değeri program tarafından değiştirilemez. Ek belirleyici **volatile** rağmen belirten değeri **const Int** gösterdiği *z* değiştirilemez program tarafından yasal olabilir programın eşzamanlı olarak çalışan bir işlem tarafından değiştirildi. Bildirimi *w* programı işaret değeri değiştiremez ve program işaretçinin değiştirilemiyor belirtir.  
  
```  
struct list *next, *previous; /* Uses the tag for list */  
```  
  
 Bu örnek iki işaretçi değişkenler bildirilmektedir *sonraki* ve *önceki*, bir yapı türüne noktası *listesi*. Bu bildirim tanımı önce görünebilir *listesi* yapısı yazın (sonraki örneğe bakın), sürece *listesi* tür tanımı bildirimiyle aynı görünürlük sahiptir.  
  
```  
struct list   
{  
    char *token;  
    int count;  
    struct list *next;  
} line;  
```  
  
 Değişkeni *satır* adlı bir yapı türüne sahip *listesi*. *Listesi* bir yapı türüne sahip üç üye: ilk üye gösteren bir işaretçidir bir **char** değerdir, ikinci bir **int** değeri ve üçüncü bir işaretçidir başka bir *listesi* yapısı.  
  
```  
struct id   
{  
    unsigned int id_no;  
    struct name *pname;  
} record;  
```  
  
 Değişkeni *kaydı* bir yapı türüne sahip *kimliği*. Unutmayın *sağlayıcı adı* adlı başka bir yapı türü için bir işaretçi olarak bildirilen *adı*. Bu bildirim önce görünebilir *adı* türü tanımlanmıştır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve Değişken Bildirimleri](../c-language/declarators-and-variable-declarations.md)