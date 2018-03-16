---
title: "Bildiricilere genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declarators, about declarators
ms.assetid: 0f2e2312-80bd-4154-8345-718bd9ed2173
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18a3f12ac87f0165c74aaa487913f679f1a9941e
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2018
---
# <a name="overview-of-declarators"></a>Bildiricilere Genel Bakış
Bildirimciler, nesne veya işlev adlarını belirten bir bildirimin bileşenleridir. Bildirimciler, adlandırılmış nesnelerin bir nesne, işaretçi, başvuru veya dizi olduğunu da belirtir.  Bildirimciler temel türü belirtmese de, işaretçiler, başvurular ve diziler gibi türetilmiş türleri belirtmek için temel türdeki tür bilgilerini değiştirir.  İşlevlere uygulanan bildirimci, bir işlevin dönüş türünü nesne, işaretçi veya başvuru olarak belirtmek için tür tanımlayıcısı ile birlikte çalışır. (Ele tanımlayıcıları [bildirimler ve tanımlar](declarations-and-definitions-cpp.md), türü ve depolama sınıfı gibi özellikler taşır. Bu bölüm hem de ele alınan değiştiricileri [Microsoft'a özgü değiştiriciler](../cpp/microsoft-specific-modifiers.md), Bildirimciler değiştirin.) Aşağıdaki şekilde, tam bir `MyFunction` bildirimi gösterilmekte ve bildirimin bileşenleri çağrılmaktadır.  
  
 ![Değiştiriciler, tanımlayıcıları ve Bildirimciler](../cpp/media/vc38qy1.gif "vc38QY1")  
Tanımlayıcılar, Değiştiriciler ve Bildirimciler  
  
 **Microsoft Specific**  
  
 Microsoft'un genişletilmiş çoğu anahtar sözcüğü, türetilmiş türler oluşturmak için değiştiriciler olarak kullanılabilir; tanımlayıcı veya bildirimci değildirler. (Bkz [Microsoft'a özgü değiştiriciler](../cpp/microsoft-specific-modifiers.md).)  
  
 **SON Microsoft özel**  
  
 Bildirimciler, isteğe bağlı bir tanımlayıcılar listesinden sonra bildirim sözdiziminde görünür. Bu tanımlayıcıları ele alınmıştır [bildirimleri.](declarations-and-definitions-cpp.md) Bir bildirim, birden fazla bildirimci içerebilir, ancak her bildirimci yalnızca bir ad bildirir.  
  
 Aşağıdaki örnek bildirimde, tanımlayıcıların ve bildirimcilerin tam bir bildirim oluşturmak için nasıl birleştirildiği gösterilmektedir:  
  
```  
const char *pch, ch;  
```  
  
 Anahtar sözcükler önceki bildiriminde **const** ve `char` tanımlayıcıları listeyi oluşturan. İki bildirimci listelenmiştir: `*pch` ve `ch`.  Birden fazla varlığı bildiren bir bildirim, sırasıyla bir tür tanımlayıcısı, virgülle ayrılmış bir bildirimciler listesi ve bir noktalı virgülden oluşur.  
  
 **Basit nesneler için Bildirimciler**  
  
 int veya double gibi basit bir nesnenin bildirimcisi, isteğe bağlı parantezlerle birlikte kendi adından oluşur.  
  
 `int i; // declarator is i`  
  
 `int (i); // declarator is (i)`  
  
 **Bildirimciler işaretçileri, başvuruları ve diziler**  
  
 Adın önüne yerleştirilen işaretçi işleçleri, nesnenin bir işaretçi veya başvuru olmasına neden olur.   **\***  İşleci bildiren bir işaretçi; adıyla  **&**  işleci, bir başvuru olarak bildirir.  
  
```  
int *i; // declarator is *i  
int **i; // declarator is **i;  
int &i = x; // declaratory is &i  
```  
  
 `const` veya `volatile`'ın eklenmesi, işaretçiye bu özel özellikleri sağlar.  Bir tanımlayıcıların bir bildirimcide (tür tanımlayıcısına karşılık olarak) kullanılması, işaret edilen nesnenin değil, işaretçinin özelliklerini değiştirir:  
  
```  
char *const cpc; // const pointer to char   
const char *pcc; // pointer to const char   
const char *const cpcc; // const pointer to const char  
```  
  
 Daha fazla bilgi bulunabilir [const ve volatile işaretçiler](../cpp/const-and-volatile-pointers.md).  
  
 Bir sınıf veya yapı üyesinin işaretçisi, uygun iç içe geçmiş ad tanımlayıcısı ile bildirilir:  
  
```  
int X::* pIntMember;   
int ::X::* pIntMember; // the initial :: specifies X is in global scope  
char Outer::Inner::* pIntMember; // pointer to char in a nested class  
```  
  
 Addan sonra isteğe bağlı bir sabit ifadeyi çevreleyen köşeli parantezler, nesnenin bir dizi olmasına neden olur.  Art arda gelen köşeli parantezler, diziye ek boyutlar bildirir.  
  
```  
int i[5]; // array with five elements of type int numbered from 0 to 4  
int i[]; // array of unknown size  
char *s[4]; // array of pointers to char  
int i[2][2]; // two dimensional array  
```  
  
 **İşlev bildirimleri**  
  
 Bağımsız değişken listesini içeren parantezler, bir işlev bildirmek için addan sonra kullanılır.  Aşağıdakiler `int` türünde bir dönüş işlevi ve `int` türünde üç bağımsız değişken bildirir.  
  
```  
int f(int a, int b, int c);  
```  
  
 İşlevlerin işaretçileri ve başvuruları, işaretçi veya başvuru işleci aşağıda gösterildiği gibi işlev adının önüne eklenerek bildirilir.  Bir işlev işaretçisini bir işaretçi döndüren bir işlevden ayırmak için normalde isteğe bağlı olan parantezlerin kullanılması gerekir:  
  
```  
int (*pf)(int); // pointer to function returning int  
int *f(int i); // function returning pointer to int  
int (&pf)(int); // reference to function   
```  
  
 Üye işlevlerinin işaretçileri, iç içe geçmiş ad tanımlayıcıları ile ayırt edilir:  
  
```  
int (X::* pmf)(); // pointer to member function of X returning int  
int* (X::* pmf)(); // pointer to member function returning pointer to int  
```  
  
 Ayrıca bkz. [üyeleri işaretçileri](../cpp/pointers-to-members.md).  
  
 **Aynı bildirim alanındaki işlevler ve nesneler**  
  
 İşlevler ve nesneler aşağıdaki gibi aynı bildirimde bildirilebilir:  
  
```  
int i, *j, f(int k);  // int, pointer to int, function returning int  
```  
  
 Sözdizimi, bazı durumlarda yanıltıcı olabilir.  Aşağıdaki bildirim  
  
```  
int* i, f(int k);  // pointer to int, function returning int (not int*)  
```  
  
 `int` işaretçisinin ve `int*` döndüren bir işlevin bildirimi olarak görünebilir, ancak böyle değildir.  Çünkü * işareti, `i` bildirimcisinin değil, `f` bildirimcisinin bir parçasıdır.  
  
 **Bildirimci sözdizimi typedef ile basitleştirme**  
  
 Bununla birlikte, `typedef` ya da bir parantez ve `typedef` anahtar sözcüğü birleşiminin kullanılması daha iyi bir tekniktir. İşlevler için bir dizi işaretçi bildirmeyi göz önünde bulundurun:  
  
```  
//  Function returning type int that takes one   
//   argument of type char *.  
typedef int (*PIFN)( char * );  
//  Declare an array of 7 pointers to functions   
//   returning int and taking one argument of type   
//   char *.  
PIFN pifnDispatchArray[7];  
```  
  
 Eşdeğer bildirim `typedef` bildirimi olmadan yazılabilir, ancak o kadar karmaşıktır ki hata oluşma potansiyeli sunabileceği avantajların üzerindedir:  
  
```  
int ( *pifnDispatchArray[7] )( char * );  
```  
  
 Typedef hakkında daha fazla bilgi için bkz: [diğer adlar ve tür tanımları](aliases-and-typedefs-cpp.md).  
  
 İşaretçiler, başvurular, tek bir temel türün dizileri tek bir bildirimde şu şekilde birleştirilebilir (virgüllerle ayrılarak)  
  
```  
int a, *b, c[5], **d, &e=a;  
```  
  
 **Daha karmaşık bildirimci sözdizimi**  
  
-   İşaretçi, başvuru, dizi ve işlev bildirimcileri, böyle nesneleri işlev işaretçilerinin dizileri, dizi işaretçileri, vb. olarak belirtecek şekilde birleştirilemez.  
  
-   Aşağıdaki özyinelemeli dilbilgisi, işaretçi bildirimcisi sözdizimini tam olarak açıklar.  
  
-   Bir `declarator` şunlardan biri olarak tanımlanır:  
  
```  
1. identifier   
2. qualified-name   
3. declarator ( argument-list ) [cv-qualfiers] [exception-spec]  
4. declarator [ [ constant-expression ] ]   
  
5. pointer-operatordeclarator   
6. ( declarator )  
```  
  
-   ve *işaretçi işleci* biridir:  
  
```  
  
      * [cv-qualifiers]  
& [cv-qualifiers]  
::nested-name-specifier * [cv-qualfiers]  
```  
  
 Bir bildirimci bildirimciler içerebileceği için yukarıdaki kurallar kullanılarak işaretçi dizileri, işlev işaretçilerinin dizilerini döndüren işlevler gibi daha karmaşık türetilmiş türler oluşturulabilir.  Oluşturma işleminin her adımı için temel veri türünü temsil eden tanımlayıcı ile işe başlayın ve önceki ifadeyle birlikte `declarator` olarak yukarıdaki sözdizimi kuralını uygulayın.  Sözdizimi kurallarını uyguladığınız sıra, ifadenin İngilizce olarak belirtildiği yönün tersi olmalıdır.  Uygulama, *işaretçi işleci* bir dizi veya işlev ifadesi sözdizimi kural dizi veya aşağıdaki tablodaki son satır olduğu gibi işlev işaretçisi istiyorsanız parantez kullanın.  
  
 Aşağıdaki örnekte, "10 int işaretçi dizisinin işaretçisi" oluşturulmuştur.  
  
|Sözlü ifade|Bildirimciler|Uygulanan Sözdizimi Kuralı|  
|-----------------------|----------------|-------------------------|  
||`i`|1.|  
|işaretçileri|`*i`|5|  
|10 dizisi|`(*i)[10]`|4|  
|işaretçisi|`*((*i)[10])`|6 ve sonra 5|  
  
 Birden fazla işaretçi, başvuru, dizi veya işlev değiştiricisi kullanıldığında, bildiriciler çok karmaşık hale gelebilir.  Konu [daha fazla karmaşık Bildirimcileri yorumlama](../c-language/interpreting-more-complex-declarators.md) daha karmaşık bildirimci sözdizimi okuma açıklar.  C++'ta olsa da, herhangi bir yere konu C ve C++ için uygulanabilir * bir işaretçi bir tam ad MyClass gibi göstermek için kullanılan::\* bir sınıf üyesi için bir işaretçi belirtmek üzere kullanılabilir.