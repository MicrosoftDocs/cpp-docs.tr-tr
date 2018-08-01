---
title: Tanımlayıcılar (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- decorated names
- decorated names, about decorated names
- identifiers, C++
- white space, in C++ identifiers
- identifiers [C++]
ms.assetid: 03a0dfb1-4530-4cdf-8295-5ea4dca4c1b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d112e7ca192e56ede21d06e7ff17a775d661d01
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405236"
---
# <a name="identifiers-c"></a>Tanımlayıcılar (C++)
Bir tanımlayıcı, aşağıdakilerden birini belirtmek için kullanılan karakter dizisidir:  
  
-   Nesne veya değişken adı  
  
-   Sınıf, yapı veya birleşim adı  
  
-   Numaralandırma türü adı  
  
-   Sınıfı, yapı, birleşim veya numaralandırma üyesi  
  
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
  
 Evrensel karakter adları belirli aralıklarının bir tanımlayıcıda de izin verilir.  Evrensel karakter adı bir tanımlayıcıda bir denetim karakteri veya temel kaynak karakter kümesindeki karakter belirtemezsiniz. Daha fazla bilgi için [karakter kümesi](../cpp/character-sets.md). Bu Unicode kod noktası numarası aralıkları gibi evrensel karakter adları için herhangi bir karakter bir tanımlayıcıda izin verilir:  
  
-   00A8, 00AA, 00AD, 00AF, 00B2 00B5, 00B7 00BA 00BC 00BE, 00C 0-00 D 6, 8-00F6 00D, 00F8 00FF 0100 02FF, 0370 167F, 1681 180D, 180F 1DBF, 1E00 1FFF, 200B 200-D, 202A 202E, 203F 2040, 2054, 2060 206F, 2070 20CF, 2100 218F, 2460 24FF, 2776-2793 2C 00-2DFF, 2E80 2FFF, 3004 3007, 3021 302F, 3031 303F, 3040-D7FF F900 FD3D, FD40 FDCF, FDF0 FE1F, FE30 FE44 FE47 FFFD 10000 1FFFD, 20000 2FFFD, 30000 3FFFD, 40000 4FFFD, 50000 5FFFD, 60000 6FFFD, 70000 7FFFD, 80000 8FFFD, 90000 9FFFD, A0000 AFFFD, B0000 BFFFD, C0000-CFFFD D0000 DFFFD, E0000 EFFFD  
  
 Bir tanımlayıcının ilki hariç herhangi bir karakter olarak şu karakterlere izin:  
  
```  
0 1 2 3 4 5 6 7 8 9  
```  
  
 Bu Unicode kod noktası numara aralığı, bir tanımlayıcının ilki hariç, herhangi bir karakteri olarak evrensel karakter adları de izin verilir:  
  
-   0300-036F 1DC0 1DFF, 0-20FF 20D, FE20 FE2F  
  
 **Microsoft'a özgü**  
  
 Microsoft C++ tanıtıcılarının yalnızca ilk 2048 karakteri önemlidir. Kullanıcı tanımlı türler için adları "tür bilgilerinin korunabilmesi için derleyici tarafından"decorated". Tür bilgileri de dahil olmak üzere sonuçta elde edilen ad 2048 karakterden uzun olamaz. (Bkz [düzenlenmiş adlar](../build/reference/decorated-names.md) daha fazla bilgi için.) Düzenlenmiş bir tanımlayıcının uzunluğunu etkileyen faktörler şunlardır:  
  
-   Tanımlayıcı bir nesne kullanıcı tanımlı tür veya tür olup olmadığını belirtir, kullanıcı tanımlı bir türden türetilmiş.  
  
-   Bir işlevden türetilmiş bir işlev veya tür tanımlayıcı olup olmadığını gösterme durumu.  
  
-   Bir işlev için bağımsız değişken sayısı.  
  
 Dolar işareti `$` Visual C++'ta geçerli tanımlayıcı karakterdir. Visual C++ tarafından izin verilen evrensel karakter adları tanımlayıcıları aralıklarını temsil karakterlerini kullanmanızı sağlar. Bu karakterler kullanmak için bunları içeren kod sayfası kodlama bir dosyasını kullanarak dosyayı kaydetmeniz gerekir.  Bu örnek, hem de genişletilmiş karakterler nasıl gösterir ve evrensel karakter adları kodunuzda birbirlerinin yerine kullanılabilir.  
  
```cpp  
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
  
 Bir tanımlayıcı izin verilen karakter aralığı daha az kısıtlayıcı olduğunda C + derleniyor +/ CLI kodu. / CLR ile derlenmiş kodda tanımlayıcıları izlemelidir [ECMA-335 standart: ortak dil altyapısı (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
 **END Microsoft özgü**  
  
 Bir tanımlayıcının ilk karakteri alfabetik bir karakter, büyük veya küçük veya alt çizgi olmalıdır ( **_** ). C++ tanımlayıcıları büyük/küçük harfe duyarlı olduğu için `fileName` farklıdır `FileName`.  
  
 Tanımlayıcılar tam olarak aynı yazım ve çalışması olarak anahtar sözcükler olamaz. Anahtar sözcük içeren tanımlayıcılar kullanılabilir. Örneğin, `Pint` içerse yasal bir tanımlayıcısı olan **int**, bir anahtar sözcük olduğu.  
  
 İki ardışık alt çizgi karakterleri kullanımını ( **__** ) bir tanımlayıcı veya büyük harf ve ardından tek bir başındaki altçizgiyi başında, tüm kapsamlarda C++ uygulamaları için ayrılmıştır. Bir alt çizgi bir küçük harf dosya kapsamına sahip adlar için geçerli veya gelecek ayrılmış tanımlayıcılarla olası çakışmaları ardından kullanarak kaçınmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Sözcük Temelli Kurallar](../cpp/lexical-conventions.md)