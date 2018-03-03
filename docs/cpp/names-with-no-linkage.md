---
title: "Bağlantısı olmayan adlar | Microsoft Docs"
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
- functions [C++], parameters
- typedef names, linkage
- enumerators [C++], linkage
- names [C++], with no linkage
- function parameters [C++]
ms.assetid: 7174c500-12d2-4572-8c16-63c27c758fb1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13acb94022caf7ad9ddbf2fe94ad2fa95a70dc80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="names-with-no-linkage"></a>Bağlantısı Olmayan Adlar
Hiçbir bağlantıya sahip olmayan adlar şunlardır:  
  
-   İşlev parametreleri.  
  
-   Blok kapsamlı adları bildirilmemiş olarak `extern` veya **statik**.  
  
-   Numaralandırıcılar.  
  
-   Bir `typedef` deyiminde bildirilen adlar. Özel durum, adlandırılmamış bir sınıf türü için ad sağlamak üzere `typedef` ifadesi kullanıldığında olur. Daha sonra, sınıfın dış bağlantısı varsa adın da dış bağlantısı olabilir. Aşağıdaki örnekte, bir `typedef` adının dış bağlantıya sahip olduğu bir durum gösterilmektedir:  
  
    ```  
    // names_with_no_linkage.cpp  
    typedef struct  
    {  
       short x;  
       short y;  
    } POINT;  
  
    extern int MoveTo( POINT pt );  
  
    int main()  
    {  
    }  
    ```  
  
     `typedef` adı, `POINT`, adlandırılmamış yapı için sınıf adı olur. Daha sonra dış bağlantısı olan bir işlevi bildirmek için kullanılır.  
  
 `typedef` adlarında hiçbir bağlantı olmadığından, bunların tanımları çeviri birimleri arasında farklı olabilir. Derlemeler ayrı ayrı yer tuttuğundan, derleyicinin bu farklılıkları algılamasının bir yolu yoktur. Sonuç olarak, bu tür hatalar bağlantı zamanına kadar algılanmaz. Aşağıdaki örneği inceleyin:  
  
```  
// Translation unit 1  
typedef int INT  
  
INT myInt;  
...  
  
// Translation unit 2  
typedef short INT  
  
extern INT myInt;  
...  
```  
  
 Önceki kod bağlantı zamanında bir "çözülmemiş dış öğe" hatası üretir.  
  
## <a name="example"></a>Örnek  
 C++ işlevleri yalnızca dosya veya sınıf kapsamı içinde tanımlanabilir. Aşağıdaki örnekte, işlevlerin nasıl tanımlanacağı anlatılmakta ve hatalı bir işlev tanımı gösterilmektedir:  
  
```  
// function_definitions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
void ShowChar( char ch );    // Declare function ShowChar.  
  
void ShowChar( char ch )     // Define function ShowChar.  
{                            // Function has file scope.  
   cout << ch;  
}  
  
struct Char                  // Define class Char.  
{  
    char Show();             // Declare Show function.  
    char Get();              // Declare Get function.  
    char ch;  
};  
  
char Char::Show()            // Define Show function  
{                            //  with class scope.  
    cout << ch;  
    return ch;  
}  
  
void GoodFuncDef( char ch )  // Define GoodFuncDef  
{                            //  with file scope.  
    int BadFuncDef( int i )  // C2601, Erroneous attempt to  
    {                        //  nest functions.  
        return i * 7;  
    }  
    for( int i = 0; i < BadFuncDef( 2 ); ++i )  
        cout << ch;  
    cout << "\n";  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program ve bağlantı](../cpp/program-and-linkage-cpp.md)