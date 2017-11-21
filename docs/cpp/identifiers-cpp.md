---
title: "Tanımlayıcılar (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- decorated names
- decorated names, about decorated names
- identifiers, C++
- white space, in C++ identifiers
- identifiers [C++]
ms.assetid: 03a0dfb1-4530-4cdf-8295-5ea4dca4c1b8
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a60ce1bd87929853e57796c6ca2727fdb626e96f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="identifiers-c"></a>Tanımlayıcılar (C++)
Aşağıdakilerden birini belirtmek için kullanılan bir karakter dizisi tanımlayıcısıdır:  
  
-   Nesne veya değişken adı  
  
-   Sınıf, yapı veya birleşim adı  
  
-   Enum türü adı  
  
-   Sınıf, yapı, UNION veya numaralandırma üyesi  
  
-   İşlev veya sınıf üyesi işlevi  
  
-   TypeDef adı  
  
-   Etiket adı  
  
-   Makro adı  
  
-   Makro parametresi  
  
 Şu karakterlerden herhangi bir tanımlayıcı karakter olarak izin verilir:  
  
```  
_ a b c d e f g h i j k l m  
n o p q r s t u v w x y z  
A B C D E F G H I J K L M  
N O P Q R S T U V W X Y Z  
```  
  
 Evrensel karakter adları belirli aralıklarına tanımlayıcıda de izin verilir.  Evrensel karakter adları bir tanımlayıcıda bir denetim karakteri veya temel kaynak karakter kümesinde bir karakter belirtemezsiniz. Daha fazla bilgi için bkz: [karakter kümesi](../cpp/character-sets2.md). Bu Unicode kod noktası numarası aralıkları bir tanımlayıcı olarak evrensel karakter adları herhangi bir karakter için izin verilir:  
  
-   00A8, 00AA, 00AD, 00AF, 00B2 00B5, 00B7 00BA, 00BC-00BE, 00C 0-00 D 6, 00D 8-00F6, 00F8 00FF, 0100 02FF, 0370 167F, 1681 180D, 180F 1DBF, 1E00 1FFF, 200B - 200D, 202A 202E, 203F 2040, 2054, 2060 206F, 2070 20CF, 2100 218F, 2460 24FF, 2776-2793, 2C 00-2DFF, 2E80 2FFF 3004 3007, 3021 302F, 3031 303F, 3040-D7FF F900 FD3D, FD40 FDCF, FDF0 FE1F, FE30 FE44, FE47-FFFD 10000 1FFFD, 20000 2FFFD, 30000 3FFFD, 40000 4FFFD, 50000 5FFFD, 60000 6FFFD, 70000 7FFFD, 80000 8FFFD, 90000 9FFFD, A0000 AFFFD, B0000 BFFFD, C0000-CFFFD D0000-DFFFD, E0000 EFFFD  
  
 Şu karakterlerden bir tanımlayıcı ilk dışında herhangi bir karaktere izin verilir:  
  
```  
0 1 2 3 4 5 6 7 8 9  
```  
  
 Bu Unicode kod noktası sayısı aralıkları, ilk dışında bir tanımlayıcıda gibi evrensel karakter adları herhangi bir karakter için de izin verilir:  
  
-   0300-036F 1DC0 1DFF, 20D 0-20FF, FE20 FE2F  
  
 **Microsoft özel**  
  
 Yalnızca ilk 2048 Microsoft C++ tanımlayıcıların önemli karakterlerdir. Kullanıcı tanımlı türler için "türü bilgileri korumak için derleyici tarafından düzenlenmiş adlar". Tür bilgiler dahil olmak üzere sonuç adı 2048 karakterden uzun olamaz. (Bkz [donatılmış adları](../build/reference/decorated-names.md) daha fazla bilgi için.) Düzenlenmiş tanımlayıcısının uzunluğu etkileyen faktörler şunlardır:  
  
-   Kullanıcı tanımlı tür veya bir türün bir nesne tanımlayıcısı olup olmadığını gösterir, kullanıcı tanımlı bir türden türetilmiş.  
  
-   Bir işlev veya bir tür tanımlayıcı olup olmadığını gösterir bir işleve türetilmiş.  
  
-   Bir işleve bağımsız değişken sayısı.  
  
 Dolar işareti `$` Visual C++ içinde geçerli bir tanımlayıcı karakterdir. Visual C++ evrensel karakter adları tanımlayıcıları içinde izin verilen aralıklarını tarafından temsil edilen gerçek karakterler kullanmanızı sağlar. Bu karakterler kullanmak için bunları içeren codepage kodlama dosyasını kullanarak dosyayı kaydetmeniz gerekir.  Bu örnek, hem de genişletilmiş karakterler nasıl gösterir ve evrensel karakter adları kodunuzda birbirinin yerine kullanılabilir.  
  
```  
// extended_identifier.cpp  
// In Visual Studio, use File, Advanced Save Options to set  
// the file encoding to Unicode codepage 1200  
struct テスト         // Japanese 'test'  
{  
    void トスト() {}  // Japanese 'toast'  
};  
  
int main() {  
    テスト \u30D1\u30F3;  // Japanese パン 'bread' in UCN form  
    パン.トスト();        // compiler recognizes UCN or literal form  
}  
```  
  
 Bir tanımlayıcı izin verilen karakter aralığı daha az kısıtlayıcı olduğunda C + derleniyor +/ CLI kod. / CLR kullanarak derlenmiş kod tanımlayıcılarının izlemelidir [standart ECMA-335: ortak dil altyapısı (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
 **SON Microsoft özel**  
  
 İlk karakteri bir tanımlayıcı büyük veya küçük bir alfasayısal karakter veya alt çizgi olmalıdır ( **_** ). C++ tanımlayıcıları büyük/küçük harfe duyarlı olduğundan `fileName` farklı `FileName`.  
  
 Tanımlayıcılar tam olarak aynı yazım ve servis talebi olarak anahtar sözcükler olamaz. Anahtar sözcükler içeren yasal tanımlayıcılardır. Örneğin, `Pint` içeriyor olsa da yasal bir tanımlayıcıdır `int`, bir anahtar sözcük olduğu.  
  
 İki ardışık kısa çizgi karakteri kullanımını ( **__** ) başlangıcında bir tanımlayıcı ya da bir büyük harf tarafından izlenen tek bir başında alt çizgi, tüm kapsamlar C++ uygulamalarında için ayrılmıştır. Önde gelen alt çizgi bir küçük harf dosya kapsamı içeren adlara yönelik geçerli veya gelecek ayrılmış tanımlayıcılarına sahip olası çakışmaları nedeniyle arkasından kullanarak kaçınmalısınız.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sözcük kuralları](../cpp/lexical-conventions.md)