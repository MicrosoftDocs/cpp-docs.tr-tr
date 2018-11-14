---
title: Üye İşaretçileri
ms.date: 11/04/2016
helpviewer_keywords:
- declarations, pointers
- class members [C++], pointers to
- pointers, to members
- members [C++], pointers to
- pointers, declarations
ms.assetid: f42ddb79-9721-4e39-95b1-c56b55591f68
ms.openlocfilehash: a15e519be14d9a05cb30a8c9282baccc87a5f35e
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326972"
---
# <a name="pointers-to-members"></a>Üye İşaretçileri

İşaretçi bildirimleri, özel durumlar bildirimlerdir üye işaretçileri.  Aşağıdaki dizi kullanılarak bildirilirler:

```
[storage-class-specifiers] [cv-qualifiers] type-specifiers [ms-modifier]qualified-name ::* [cv-qualifiers] identifier
[= & qualified-name :: member-name];
```

1. Bildirim belirticisi:

   - İsteğe bağlı bir depolama sınıfı tanımlayıcısı.

   - İsteğe bağlı **const** ve/veya **geçici** tanımlayıcıları.

   - Tür belirticisi: bir tür adı.  Bu üye için işaret türüdür sınıfı değil.

1. Bildirimci:

   - Bir isteğe bağlı Microsoft'a özgü değiştirici. Daha fazla bilgi için [Microsoft'a özel değiştiriciler](../cpp/microsoft-specific-modifiers.md).

   - İşaret için üyeleri içeren sınıfın tam adı.

   - __::__ İşleci.

   - __\*__ İşleci.

   - İsteğe bağlı **const** ve/veya **geçici** tanımlayıcıları.

   - Üye işaretçisi adlandırma tanımlayıcısı.

1. İsteğe bağlı bir başlatıcı:

   - **=** İşleci.

   - **&** İşleci.

   - Sınıfın tam adı.

   - __::__ İşleci.

   - Bir statik olmayan üye uygun bir tür sınıfının adı.

Her zaman olduğu gibi birden çok bildirimcisi (ve ilişkili tüm başlatıcıları) tek bir bildirimde izin verilir.

Üye ait olduğu sınıfın ve üye türü için tür bilgilerini içerdiğinden bir sınıfın bir üye işaretçisi normal bir işaretçiyle farklıdır. Normal bir işaretçi tanımlar (adresini sahiptir) yalnızca tek bir nesne bellekte. Bir sınıfın üyesinin işaretçisi sınıfın örneklerini bu üye tanımlar. Aşağıdaki örnek, bir sınıfı bildirir `Window`ve üye verilerine bazı işaretçiler.

```cpp
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

Önceki örnekte `pwCaption` sınıf herhangi bir üyenin bir işaretçisidir `Window` türü olan `char*`. Türünü `pwCaption` olduğu `char * Window::* `. Sonraki kod parçasını işaretçileri bildirir `SetCaption` ve `GetCaption` üye işlevleri.

```cpp
const char * (Window::*pfnwGC)() = &Window::GetCaption;
bool (Window::*pfnwSC)( const char * ) = &Window::SetCaption;
```

İşaretçileri `pfnwGC` ve `pfnwSC` işaret `GetCaption` ve `SetCaption` , `Window` sınıfı, sırasıyla. Kod kullanarak doğrudan üye işaretçisinin pencere başlığı için bilgi kopyalar `pwCaption`:

```cpp
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

Arasındaki fark **.** <strong>\*</strong> ve **->** <strong>\*</strong> is işleçlerini (işaretçi-üye işleçleri) **.** <strong>\*</strong> seçen üyeleri bir nesne veya nesne başvurusu göz önünde bulundurulduğunda, while **->** <strong>\*</strong> işleci üye işaretçisi aracılığıyla seçer. (Bu işleçler hakkında daha fazla bilgi için bkz. [işaretçi-üye işleçli ifadeler](../cpp/pointer-to-member-operators-dot-star-and-star.md).)

İşaretçi-üye işleçleri üyenin türü sonucudur — bu durumda, `char *`.

Aşağıdaki kod parçası, üye işlevleri çağırır `GetCaption` ve `SetCaption` üyeleri için işaretçiler kullanma:

```cpp
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

Statik bir üyenin adresi, üye işaretçisi değildir. Statik üyenin bir örneğinin normal bir işaretçisidir. Statik bir üyenin yalnızca bir örneği sıradan address-of belirli bir sınıfın tüm nesneleri için mevcut olduğundan (**&**) ve başvuru (<strong>\*</strong>) işleçleri kullanılabilir.

## <a name="pointers-to-members-and-virtual-functions"></a>Üye ve Sanal İşlev İşaretçileri

Üye işaretçisi işlevi aracılığıyla sanal bir işlevin çağrılması, işlev doğrudan çağrılmış gibi çalışır; doğru işlev v tablosunda aranır ve çağrılır.

Sanal işlevlerin çalışması, her zaman olduğu gibi bir temel sınıf işaretçisiyle çağrılmalarına bağlıdır. (Sanal işlevler hakkında daha fazla bilgi için bkz. [sanal işlevler](../cpp/virtual-functions.md).)

Aşağıdaki kodda, üye işaretçisi işleviyle sanal bir işlevin nasıl çağrılacağı gösterilmektedir:

```cpp
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