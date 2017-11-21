---
title: "Anonim sınıf türleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- class types [C++], anonymous
- anonymous class types
ms.assetid: 9ba667b2-8c2a-4c29-82a6-fa120b9233c8
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 854f15dcc597f2fc6e32f8385c1e9d27cfb37362
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="anonymous-class-types"></a>Anonim Sınıf Türleri
Sınıfları anonim olabilir — diğer bir deyişle, bunlar olmadan bildirilebilir bir *tanımlayıcısı*. Bir sınıf adı değiştirin gerektiğinde bu faydalıdır bir `typedef` aşağıdaki gibi ad:  
  
```  
typedef struct  
{  
    unsigned x;  
    unsigned y;  
} POINT;  
```  
  
> [!NOTE]
>  Önceki örnekte gösterilen anonim sınıfları kullanımını, var olan C kodu ile koruma uyumluluk için kullanışlıdır. Bazı C kodda, kullanımını `typedef` anonim yapılar birlikte yaygın olduğu.  
  
 Anonim sınıfları ayrıca değil içerdiği şekilde aşağıdaki gibi ayrı bir sınıf görünür için bir sınıf üyesine bir başvuru istediğinizde kullanışlıdır:  
  
```  
struct PTValue  
{  
    POINT ptLoc;  
    union  
    {  
        int  iValue;  
        long lValue;  
    };  
};  
  
PTValue ptv;  
```  
  
 Önceki kod `iValue` nesne üye seçimi işleci kullanılarak erişilebilir (**.**) gibi:  
  
```  
int i = ptv.iValue;  
```  
  
 Anonim sınıflardır belirli sınırlamalara tabidir. (Anonim birleşimler hakkında daha fazla bilgi için bkz: [birleşimler](../cpp/unions.md).) Anonim sınıflar:  
  
-   Oluşturucunun ya da yıkıcı sahip olamaz.  
  
-   (Tür denetlemesi üç nokta kullanarak engellenmediğinden olmadığı sürece) işleve bağımsız değişken olarak geçirilemez.  
  
-   Olarak dönüş değerleri işlevlerden iade edilemez.  
  
## <a name="anonymous-structs"></a>Anonim yapılar  
  
### <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Microsoft C uzantısı, bir ad verip olmadan başka bir yapı içinde bir yapı değişken bildirme olanak sağlar. Bu iç içe geçmiş yapılar anonim yapılar denir. C++ anonim yapılar izin vermiyor.  
  
 Üyeleri içeren yapısındaki değilmiş gibi anonim bir yapı üyeleri erişebilir.  
  
```  
// anonymous_structures.c  
#include <stdio.h>  
  
struct phone  
{  
    int  areacode;  
    long number;  
};  
  
struct person  
{  
    char   name[30];  
    char   gender;  
    int    age;  
    int    weight;  
    struct phone;    // Anonymous structure; no name needed  
} Jim;  
  
int main()  
{  
    Jim.number = 1234567;  
    printf_s("%d\n", Jim.number);     
}  
//Output: 1234567  
```  
  
**SON Microsoft özel**  
  
