---
title: TypeDef bildirimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declarations, typedef
- typedef declarations
- types [C], declarations
ms.assetid: e92a3b82-9269-4bc6-834a-6f431ccac83e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 192f7ab037362219261852cfdb0a5eac53e5df9f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391658"
---
# <a name="typedef-declarations"></a>Typedef Bildirimleri
Typedef bildirimiyle depolama sınıfı olarak typedef bildirimidir. Yeni bir tür bildirimcisi olur. Typedef bildirimleri daha kısa ya da daha anlamlı adları zaten C tarafından tanımlanan türlerin veya bildirilen türleri oluşturmak için kullanabilirsiniz. TypeDef adları değişebilir uygulama ayrıntılarını kapsülleyen olanak sağlar.  
  
 Typedef bildirimi tıpkı bir değişken olarak yorumlanır veya işlev bildirimi ancak bildirimi tarafından belirtilen tür varsayılarak yerine tanımlayıcı türü için eş anlamlı olur.  
  
## <a name="syntax"></a>Sözdizimi  
 `declaration`:  
 *bildirim tanımlayıcıları init bildirimcisi listesi* kabul **;**  
  
 *bildirim tanımlayıcıları*:  
 *depolama sınıfı tanımlayıcısı bildirim tanımlayıcıları* iptal et  
  
 *tür belirteci bildirim tanımlayıcıları* iptal et  
  
 *tür niteleyicisi bildirim tanımlayıcıları* iptal et  
  
 *depolama sınıfı tanımlayıcısı*:  
 `typedef`  
  
 *tür belirteci*:  
 **void**  
  
 **char**  
  
 **short**  
  
 **int**  
  
 **long**  
  
 **float**  
  
 **double**  
  
 **İmzalı**  
  
 **İmzasız**  
  
 *yapı veya birleşim belirticisi*  
  
 *Liste belirticisi*  
  
 *TypeDef adı*  
  
 *TypeDef adı*:  
 *Tanımlayıcı*  
  
 Typedef bildirim türleri oluşturmaz unutmayın. Mevcut türleri için eş anlamlı sözcükleri veya adları başka yollarla belirtilen türleri oluşturur. Typedef adları tür belirteci kullanıldığında, belirli tür tanımlayıcıları, ancak diğer ile birleştirilebilir. Kabul edilebilir değiştiricileri dahil **const** ve `volatile`.  
  
 TypeDef adları paylaşmak ad alanı ile sıradan tanımlayıcıları (bkz [ad alanları](../c-language/name-spaces.md) daha fazla bilgi için). Bu nedenle, bir program typedef adı ve yerel kapsamı tanımlayıcısı tarafından aynı ada sahip olabilir. Örneğin:  
  
```  
typedef char FlagType;  
  
int main()  
{  
}  
  
int myproc( int )  
{  
    int FlagType;  
}  
```  
  
 Tür belirleyici bir typedef aynı adda bir yerel kapsamı tanımlayıcısı bildirme veya bir yapının veya birleşimin aynı kapsamı veya bir iç kapsamda üyesi bildirme belirtilmesi gerekir. Bu örnekte, bu kısıtlamayı gösterilmektedir:  
  
```  
typedef char FlagType;  
const FlagType x;  
```  
  
 Yeniden `FlagType` bir tanımlayıcı, yapı üyesi veya bir bileşim üyesi, türü için ad sağlanmalıdır:  
  
```  
const int FlagType;  /* Type specifier required */  
```  
  
 Söylemek yeterli değil  
  
```  
const FlagType;      /* Incomplete specification */  
```  
  
 çünkü `FlagType` değil bildiriliyor bir tanımlayıcı türü parçası olarak alınır. Bu bildirim gibi geçersiz bir bildirim olarak alınır  
  
```  
int;  /* Illegal declaration */  
```  
  
 Typedef, işaretçi, işlevi ve dizi türleri dahil olmak üzere tüm türüyle bildirebilirsiniz. Yapı veya birleşim türü tanımlamadan önce bildirimiyle aynı görünürlük tanımına sahip olduğu sürece bir işaretçi bir yapı veya birleşim türü için bir typedef ad bildirebilirsiniz.  
  
 TypeDef adları kod okunabilirliğini artırmak için kullanılabilir. Aşağıdaki bildirimlerini üçünü `signal` ilk olmadan yapma tam olarak aynı türünü belirtin tüm typedef adlarının kullanın.  
  
```  
typedef void fv( int ), (*pfv)( int );  /* typedef declarations */  
  
void ( *signal( int, void (*) (int)) ) ( int );  
fv *signal( int, fv * );   /* Uses typedef type */  
pfv signal( int, pfv );    /* Uses typedef type */  
```  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki örneklerde typedef bildirimleri gösterilmektedir:  
  
```  
typedef int WHOLE; /* Declares WHOLE to be a synonym for int */  
```  
  
 Unutmayın `WHOLE` bir değişken bildirimi gibi kullanılabilecek şimdi `WHOLE i;` veya `const WHOLE i;`. Ancak, bildirimi `long WHOLE i;` geçersiz olacaktır.  
  
```  
typedef struct club   
{  
    char name[30];  
    int size, year;  
} GROUP;  
```  
  
 Bu ifade bildirir `GROUP` üç üyeleriyle yapısı türü olarak. Yapı etiketi itibaren `club`, ayrıca belirtilirse, typedef adı (`GROUP`) veya yapı etiketi bildirimlerinde kullanılabilir. Struct anahtar sözcüğü etiketiyle kullanmanız gerekir ve struct anahtar sözcüğü ile typedef adı kullanamazsınız.  
  
```  
typedef GROUP *PG; /* Uses the previous typedef name   
                      to declare a pointer            */  
```  
  
 Türü `PG` gösteren bir işaretçi olarak bildirilen `GROUP` sırayla yapısı tür olarak tanımlandığından türü.  
  
```  
typedef void DRAWF( int, int );  
```  
  
 Bu örnek türü sağlar `DRAWF` iki int bağımsız değişken almama ve herhangi bir değer döndüren bir işlev için. Bu, örneğin, anlamına bildirimi  
  
```  
DRAWF box;   
```  
  
 bildirimine eşdeğerdir  
  
```  
void box( int, int );  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  


