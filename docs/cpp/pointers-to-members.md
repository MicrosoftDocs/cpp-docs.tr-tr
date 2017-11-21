---
title: "Üye işaretçileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- declarations, pointers
- class members [C++], pointers to
- pointers, to members
- members [C++], pointers to
- pointers, declarations
ms.assetid: f42ddb79-9721-4e39-95b1-c56b55591f68
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d8a8a8c4d88f0ccd7c879eb361643ea22e2ec41b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="pointers-to-members"></a>Üye İşaretçileri
Üye işaretçileri bildirimlerini işaretçi bildirimleri özel örnekleridir.  Aşağıdaki dizi kullanılarak bildirilirler:  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers [ms-modifier]qualified-name ::* [cv-qualifiers] identifier  
[= & qualified-name :: member-name];  
```  
  
1.  Bildirim tanımlayıcısı:  
  
    -   İsteğe bağlı bir depolama sınıfı tanımlayıcısı.  
  
    -   İsteğe bağlı **const** ve/veya `volatile` tanımlayıcıları.  
  
    -   Tür tanımlayıcısı: bir türünün adı.  İçin işaret için üye türünde sınıfı.  
  
2.  Bildirimcisi:  
  
    -   Bir isteğe bağlı Microsoft belirli değiştiricisi. Daha fazla bilgi için bkz: [Microsoft'a özgü değiştiriciler](../cpp/microsoft-specific-modifiers.md).  
  
    -   İçin işaret için üye içeren sınıf tam adı.   
  
    -   :: İşleci.  
  
    -   **\***  İşleci.  
  
    -   İsteğe bağlı **const** ve/veya `volatile` tanımlayıcıları.  
  
    -   İşaretçiden üyeye adlandırma tanımlayıcısı.  
  
    -   İsteğe bağlı bir başlatıcı:  
  
 **=**  İşleci.  
  
 **&**  İşleci.  
  
 Sınıfın tam adı.  
  
 `::` işleci.  
  
 Statik olmayan üye uygun bir tür sınıfının adı.  
  
 Her zaman olduğu gibi birden çok bildirimler (ve ilişkili tüm başlatıcıları) tek bir bildirimde izin verilir.  
  
 Tür bilgilerini üye tür ve üye ait olduğu sınıf için sahip olduğu bir sınıf üyesi için bir işaretçi normal işaretçi farklıdır. Normal bir işaretçi tanımlar (adresini sahiptir) bellek yalnızca tek bir nesnede. Bir sınıf üyesi için bir işaretçi bu üye sınıfının bir örneğini tanımlar. Aşağıdaki örnek, bir sınıf bildirir `Window`ve bazı işaretçiler üye verileri.  
  
```  
// pointers_to_members1.cpp  
class Window  
{  
public:  
   Window();                               // Default constructor.  
   Window( int x1, int y1,                 // Constructor specifying  
   int x2, int y2 );                       //  window size.  
bool SetCaption( const char *szTitle ); // Set window caption.  
   const char *GetCaption();               // Get window caption.  
   char *szWinCaption;                     // Window caption.  
};  
  
// Declare a pointer to the data member szWinCaption.  
char * Window::* pwCaption = &Window::szWinCaption;  
int main()  
{  
}  
```  
  
 Önceki örnekte `pwCaption` gösteren bir işaretçidir sınıfı herhangi bir üyenin `Window` türü olan **char\***. Türü `pwCaption` olan `char * Window::*`. Sonraki kod parçası işaretçileri bildirir `SetCaption` ve `GetCaption` üye işlevleri.  
  
```  
const char * (Window::*pfnwGC)() = &Window::GetCaption;  
bool (Window::*pfnwSC)( const char * ) = &Window::SetCaption;  
```  
  
 İşaretçileri `pfnwGC` ve `pfnwSC` işaret `GetCaption` ve `SetCaption` , `Window` sınıfı, sırasıyla. Kod kullanarak doğrudan işaretçiden üyeye pencere resim yazısı için bilgi kopyalar `pwCaption`:  
  
```  
Window wMainWindow;  
Window *pwChildWindow = new Window;  
char   *szUntitled    = "Untitled -  ";  
int    cUntitledLen   = strlen( szUntitled );  
  
strcpy_s( wMainWindow.*pwCaption, cUntitledLen, szUntitled );  
(wMainWindow.*pwCaption)[cUntitledLen - 1] = '1';     //same as  
//wMainWindow.SzWinCaption [cUntitledLen - 1] = '1';  
strcpy_s( pwChildWindow->*pwCaption, cUntitledLen, szUntitled );   
(pwChildWindow->*pwCaption)[cUntitledLen - 1] = '2'; //same as //pwChildWindow->szWinCaption[cUntitledLen - 1] = '2';  
```  
  
 Arasındaki farkı **.\***  ve  **-> \***  bulunan işleç (işaretçi-üye işleçleri) **.\***  seçen üyeleri bir nesneye veya nesne başvurusu verilen, while  **-> \***  işleci işaretçi üzerinden üyeleri seçer. (Bu işleçler hakkında daha fazla bilgi için bkz: [işaretçi-üye işleçli ifadeler](../cpp/pointer-to-member-operators-dot-star-and-star.md).)  
  
 İşaretçi-üye işleçleri sonucu üye türüdür — bu durumda, **char \*** .  
  
 Aşağıdaki kod parçası üye işlevleri çağırır `GetCaption` ve `SetCaption` üyeleri işaretçileri kullanarak:  
  
```  
// Allocate a buffer.  
enum {  
    sizeOfBuffer = 100  
};  
char szCaptionBase[sizeOfBuffer];  
  
// Copy the main window caption into the buffer  
//  and append " [View 1]".  
strcpy_s( szCaptionBase, sizeOfBuffer, (wMainWindow.*pfnwGC)() );  
strcat_s( szCaptionBase, sizeOfBuffer, " [View 1]" );  
// Set the child window's caption.  
(pwChildWindow->*pfnwSC)( szCaptionBase );  
```  
  
## <a name="restrictions-on-pointers-to-members"></a>Üye İşaretçileri Kısıtlamaları  
 Statik bir üyenin adresi, üye işaretçisi değildir. Statik üyenin bir örneğinin normal bir işaretçisidir. Sıradan adres-, belirli bir sınıfın tüm nesneleri için statik bir üyenin yalnızca bir örneği var olduğundan **(&)** ve dereference **(\*)** işleçleri kullanılabilir.  
  
## <a name="pointers-to-members-and-virtual-functions"></a>Üye ve Sanal İşlev İşaretçileri  
 Üye işaretçisi işlevi aracılığıyla sanal bir işlevin çağrılması, işlev doğrudan çağrılmış gibi çalışır; doğru işlev v tablosunda aranır ve çağrılır.  
  
 Sanal işlevlerin çalışması, her zaman olduğu gibi bir temel sınıf işaretçisiyle çağrılmalarına bağlıdır. (Sanal işlevler hakkında daha fazla bilgi için bkz: [sanal işlevler](../cpp/virtual-functions.md).)  
  
 Aşağıdaki kodda, üye işaretçisi işleviyle sanal bir işlevin nasıl çağrılacağı gösterilmektedir:  
  
```  
// virtual_functions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
class Base  
{  
public:  
virtual void Print();  
};  
void (Base ::* bfnPrint)() = &Base :: Print;  
void Base :: Print()  
{  
cout << "Print function for class Base\n";  
}  
  
class Derived : public Base  
{  
public:  
void Print();  // Print is still a virtual function.  
};  
  
void Derived :: Print()  
{  
cout << "Print function for class Derived\n";  
}  
  
int main()  
{  
    Base   *bPtr;  
    Base    bObject;  
Derived dObject;  
bPtr = &bObject;    // Set pointer to address of bObject.  
(bPtr->*bfnPrint)();  
bPtr = &dObject;    // Set pointer to address of dObject.  
(bPtr->*bfnPrint)();  
}  
  
//Output: Print function for class Base  
Print function for class Derived  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 