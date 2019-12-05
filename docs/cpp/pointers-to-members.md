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
ms.openlocfilehash: 14b5c12715d1c4c27d9ef8e262170acb2f85e526
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857352"
---
# <a name="pointers-to-members"></a>Üye İşaretçileri

Üye işaretçilerin bildirimleri, işaretçi bildirimlerinin özel çalışmalardır.  Aşağıdaki dizi kullanılarak bildirilirler:

```
[storage-class-specifiers] [cv-qualifiers] type-specifiers [ms-modifier]qualified-name ::* [cv-qualifiers] identifier
[= & qualified-name :: member-name];
```

1. Bildirim belirticisi:

   - İsteğe bağlı bir depolama sınıfı belirleyicisi.

   - İsteğe bağlı **const** ve/veya **volatile** belirticileri.

   - Tür belirleyicisi: bir türün adı.  Bu, sınıfa değil, işaret edilecek üyenin türüdür.

1. Bildirimci:

   - İsteğe bağlı Microsoft'a özgü bir değiştirici. Daha fazla bilgi için bkz. [Microsoft 'A özgü değiştiriciler](../cpp/microsoft-specific-modifiers.md).

   - İşaret edilecek üyeleri içeren sınıfın tam adı.

   - __::__ İşleci.

   - __\*__ işleci.

   - İsteğe bağlı **const** ve/veya **volatile** belirticileri.

   - Tanıtıcı, üyeye olan işaretçiyi adlandırma.

1. İsteğe bağlı Başlatıcı:

   - **=** işleci.

   - **&** işleci.

   - Sınıfın tam adı.

   - __::__ İşleci.

   - Uygun türdeki sınıfının statik olmayan bir üyesinin adı.

Her zaman olduğu gibi, tek bir bildirimde birden çok bildirimciye (ve ilişkili başlatıcılara) izin verilir.

Bir sınıfın bir işaretçisi, üyenin türü ve üyenin ait olduğu sınıf için tür bilgilerine sahip olduğundan normal işaretçiden farklıdır. Normal bir işaretçi yalnızca bellekte tek bir nesne (adresini içerir) tanımlar. Bir sınıfın bir işaretçisi, bu üyeyi sınıfın herhangi bir örneğinde tanımlar. Aşağıdaki örnek bir sınıf, `Window`ve bazı üye verilerine işaretçiler bildirir.

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

Yukarıdaki örnekte `pwCaption`, tür `char*`olan `Window` sınıfının herhangi bir üyesine yönelik bir işaretçidir. `pwCaption` türü `char * Window::* `. Sonraki kod parçası `SetCaption` ve `GetCaption` üye işlevlerine işaretçiler bildirir.

```cpp
const char * (Window::*pfnwGC)() = &Window::GetCaption;
bool (Window::*pfnwSC)( const char * ) = &Window::SetCaption;
```

İşaretçiler `pfnwGC` ve `pfnwSC`, sırasıyla `Window` sınıfının `GetCaption` ve `SetCaption`. Kod, üye `pwCaption`işaretçisini kullanarak bilgileri pencere açıklamalı yazısına doğrudan kopyalar:

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

Arasındaki fark **.** <strong>\*</strong> ve **->** <strong>\*</strong> işleçler (üye işaretçisi işleçleri) **.** <strong>\*</strong> işleci bir nesne veya nesne başvurusu verilen üyeleri seçer, ancak **->** <strong>\*</strong> işleci üyeleri bir işaretçi aracılığıyla seçer. (Bu işleçler hakkında daha fazla bilgi için bkz. [üye Işaretçisi işleçleri olan ifadeler](../cpp/pointer-to-member-operators-dot-star-and-star.md).)

Üye işaretçisi işleçlerinin sonucu üyenin türüdür — bu durumda `char *`.

Aşağıdaki kod parçası `GetCaption` üye işlevlerini çağırır ve üyelere işaretçiler kullanarak `SetCaption`:

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

Statik bir üyenin adresi, üye işaretçisi değildir. Statik üyenin bir örneğinin normal bir işaretçisidir. Belirli bir sınıfın tüm nesneleri için bir statik üyenin yalnızca bir örneği bulunduğundan, normal adres ( **&** ) ve başvuru (<strong>\*</strong>) işleçleri kullanılabilir.

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