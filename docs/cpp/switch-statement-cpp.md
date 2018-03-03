---
title: "Deyimi (C++) geçiş | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- default_cpp
- switch_cpp
- case_cpp
dev_langs:
- C++
helpviewer_keywords:
- switch keyword [C++]
- case keyword [C++], in switch statements
- default keyword [C++]
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e668756e8cabafbdef522d6754487efe452f96de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="switch-statement-c"></a>switch Deyimi (C++)
Tam sayı ifadenin değerine bağlı olarak kod birden çok bölüm arasında seçim sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
   switch ( init; expression )  
   case constant-expression : statement  
   [default  : statement]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 *İfade* tamsayı türü veya var olduğu anlaşılır bir tam sayı türüne dönüştürme sınıf türü olması gerekir. Tam sayı yükseltme açıklandığı gibi gerçekleştirilir [standart dönüşümler](standard-conversions.md).  
  
 `switch` Deyimi gövde oluşan bir dizi **durum** etiketleri ve isteğe bağlı bir **varsayılan** etiketi. Hiçbir iki sabit ifadeler **durumda** deyimleri aynı değere değerlendirin. **Varsayılan** etiketi yalnızca bir kez görünebilir. Etiketli deyimler söz dizimi gereksinimler değildir ancak `switch` açıklamadır onlar olmadan anlamsız.   Varsayılan deyimini sonunda gelen değil; herhangi bir yere switch deyimi gövdesinde yer alabilir. Servis talebi veya varsayılan bir etiket yalnızca switch deyimi içinde bulunabilir.  
  
 *Sabit ifadesi* her **durum** etiket türüne dönüştürülüp *ifade* ve ile karşılaştırıldığında *ifade* için Eşitlik. Denetim geçirir ifadesine özelliği **durum** *sabit ifadesi* değeri ile eşleşen *ifade*. Bunun sonucunda oluşan davranışı aşağıdaki tabloda gösterilmiştir.  
  
### <a name="switch-statement-behavior"></a>Switch deyimi davranışı  
  
|Koşul|Eylem|  
|---------------|------------|  
|Dönüştürülen değeri, yükseltilen denetleme ifade ile eşleşir.|Denetimin etiket aşağıdaki deyimi aktarılır.|  
|Sabitler hiçbiri sabitler eşleşen **durum** etiketler; bir **varsayılan** etiketi mevcut.|Denetim için aktarılır **varsayılan** etiketi.|  
|Sabitler hiçbiri sabitler eşleşen **durumda** etiketler; **varsayılan** etiketi mevcut değil.|Denetim sonraki deyime aktarılır `switch` deyimi.|  
  
 Eşleşen bir ifade bulunursa, denetim tarafından sonraki engelleniyor değil **durum** veya **varsayılan** etiketler. [Sonu](../cpp/break-statement-cpp.md) deyimi yürütme durdurun ve sonra deyimi denetim aktarmak için kullanılan `switch` deyimi. Olmadan bir **sonu** deyimi, eşleşen her deyiminden **durum** etiket sonuna `switch`dahil **varsayılan**, yürütülür. Örneğin:  
  
```  
// switch_statement1.cpp  
#include <stdio.h>  
  
int main() {  
   char *buffer = "Any character stream";  
   int capa, lettera, nota;  
   char c;  
   capa = lettera = nota = 0;  
  
   while ( c = *buffer++ )   // Walks buffer until NULL  
   {  
      switch ( c )  
      {  
         case 'A':  
            capa++;  
            break;  
         case 'a':  
            lettera++;  
            break;  
         default:  
            nota++;  
      }  
   }  
   printf_s( "\nUppercase a: %d\nLowercase a: %d\nTotal: %d\n",  
      capa, lettera, (capa + lettera + nota) );  
}  
```  
  
 Yukarıdaki örnekte, `capa` olmazsa artırılır `c` bir büyük `A`. `break` Sonra deyimi `capa++` yürütülmesi sonlandırır `switch` deyimi gövde ve denetim geçtiği `while` döngü. Olmadan `break` deyimi, yürütme "geçiş" sonraki etiketli deyim için böylece `lettera` ve `nota` da artar. Benzer bir amaçla tarafından sunulan `break` bildirimi `case 'a'`. Varsa `c` küçük harf olduğundan `a`, `lettera` artırılır ve `break` açıklamayı sonlandıran `switch` deyimi gövdesi. Varsa `c` değil bir `a` veya `A`, `default` deyimi gerçekleştirilir.  

 **Visual Studio 2017 ve üzeri:** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)) `[[fallthrough]]` özniteliği, C ++ 17 standardında belirtilir. İçinde kullanılabilir bir `switch` deyimi bu başarısızlığı davranışı derleyici (veya kod okuyan herkes için) bir ipucu olarak tasarlanmıştır. Bu öznitelik hiçbir etkisi derleyici davranışı nedenle Visual C++ Derleyici fallthrough davranışı üzerinde şu anda uyarmaz. Etiketli deyim içinde boş bir deyimi öznitelik uygulanan unutmayın; diğer bir deyişle noktalı virgül gereklidir.

```cpp
int main()
{
    int n = 5;
    switch (n)
    {

    case 1:
        a();
        break;
    case 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    case 3:
        c();
        break;
    default:
        d();
        break;
    }

    return 0;
}
```

 **Visual Studio 2017 15.3 ve sonraki sürümleri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): switch deyimi getirir ve kapsamını switch deyimi bloğuna sınırlı bir değişken başlatılamadı:

```cpp
 switch (Gadget gadget(args); auto s = gadget.get_status())
        {
        case status::good:
            gadget.zip();
            break;
        case status::bad:
            throw BadGadget();
        };
```

 Bir iç bloğunu bir `switch` deyimi, başlatmaları tanımlarla içerebilir, erişilebilir olduğu sürece — tüm olası yürütme yollarla diğer bir deyişle, atlanacağı değil. Bu bildirimler kullanarak sunulan adları yerel kapsama sahip. Örneğin:  
  
```cpp  
// switch_statement2.cpp  
// C2360 expected  
#include <iostream>  
using namespace std;  
int main(int argc, char *argv[])  
{  
   switch( tolower( *argv[1] ) )  
   {  
       // Error. Unreachable declaration.  
       char szChEntered[] = "Character entered was: ";  
  
   case 'a' :  
       {  
       // Declaration of szChEntered OK. Local scope.  
       char szChEntered[] = "Character entered was: ";  
       cout << szChEntered << "a\n";  
       }  
       break;  
  
   case 'b' :  
       // Value of szChEntered undefined.  
       cout << szChEntered << "b\n";  
       break;  
  
   default:  
       // Value of szChEntered undefined.  
       cout << szChEntered << "neither a nor b\n";  
       break;  
   }  
}  
```  
  
 A `switch` deyimi iç içe geçirilemez. Böyle durumlarda, **durum** veya **varsayılan** etiketlerle ilişkilendirmek en yakın `switch` bunları barındırır deyimi.  

 
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Microsoft C case değerlerini sayısını sınırlamaz bir `switch` deyimi. Yalnızca kullanılabilir bellek ile sınırlıdır. ANSI C gerektiren en az 257 durum etiketi içinde izin verilmeyecek bir `switch` deyimi.  
  
 Microsoft C için Microsoft uzantıları etkinleştirildiğini varsayılandır. Kullanım [/Za](../build/reference/za-ze-disable-language-extensions.md) bu uzantıları devre dışı bırakma derleyici seçeneği.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seçim deyimleri](../cpp/selection-statements-cpp.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)   
 