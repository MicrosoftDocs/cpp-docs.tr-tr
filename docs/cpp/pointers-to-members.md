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
ms.openlocfilehash: adffacc3ddc08679d7db4e17e027d8a7dbe8a92b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320327"
---
# <a name="pointers-to-members"></a>Üye İşaretçileri

Üyelere işaretçilerin bildirimleri işaretçi bildirimleri özel durumlardır.  Aşağıdaki sırayı kullanarak bildirilir:

> *depolama sınıfı belirteçleri*<sub>tercih</sub> *cv-qualifiers*<sub>opt</sub> *tip-belirtici* *ms-değiştirici*<sub>opt</sub> nitelikli *isim* **`::*`** *cv-qualifiers*<sub>opt</sub> *tanımlayıcı* *pm-initializer*<sub>opt</sub>**`;`**

1. Bildirim belirtici:

   - İsteğe bağlı depolama sınıfı belirticisi.

   - İsteğe bağlı **const** ve **uçucu** belirteciler.

   - Tür belirtici: bir türün adı. Bu işaret edilecek üyenin türü, sınıf değil.

1. Bildirimci:

   - İsteğe bağlı Microsoft'a özgü bir değiştirici. Daha fazla bilgi için [Microsoft'a Özel Değiştiriciler'e](../cpp/microsoft-specific-modifiers.md)bakın.

   - Üyelerin yer aldığı sınıfın nitelikli adı işaret edilecek.

   - Operatör. __`::`__

   - Operatör. __`*`__

   - İsteğe bağlı **const** ve **uçucu** belirteciler.

   - İşaretçiyi üyeye adlandıran tanımlayıcı.

1. İsteğe bağlı bir işaretçi-üye baş harfi:

   - Operatör. **`=`**

   - Operatör. **`&`**

   - Sınıfın nitelikli adı.

   - Operatör. __`::`__

   - Uygun türdeki sınıfın statik olmayan bir üyesinin adı.

Her zaman olduğu gibi, birden çok bildirimci (ve ilişkili başlatılması) tek bir bildirimde izin verilir. Üye işaretçisi sınıfın statik bir üyesini, başvuru türünün **`void`** bir üyesini veya .

Bir sınıfın bir üyesinin işaretçisi normal bir işaretçiden farklıdır: hem üyenin türü hem de üyenin ait olduğu sınıf için tür bilgileri vardır. Normal bir işaretçi, bellekte yalnızca tek bir nesnenin adresini tanımlar (adresine sahiptir). Bir sınıfın bir üyesiiçin bir işaretçi sınıfın herhangi bir örneğinde bu üyeyi tanımlar. Aşağıdaki örnek, `Window`bir sınıf ve üye verilere bazı işaretçiler bildirir.

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

Önceki örnekte, `pwCaption` türde `Window` `char*`herhangi bir sınıf üyesi için bir işaretçi. Türü `pwCaption` . `char * Window::*` Sonraki kod parçası işaretçileri `SetCaption` ve `GetCaption` üye işlevleri bildirir.

```cpp
const char * (Window::*pfnwGC)() = &Window::GetCaption;
bool (Window::*pfnwSC)( const char * ) = &Window::SetCaption;
```

İşaretçiler `pfnwGC` ve `pfnwSC` işaret `GetCaption` `SetCaption` ve `Window` sınıfın, sırasıyla. Kod, üyeye `pwCaption`işaretçiyi kullanarak bilgileri doğrudan pencere başlığına kopyalar:

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

Operatörler **`.*`** (işaretçiden **`->*`** üyeye işleçler) arasındaki **`.*`** fark, **`->*`** işleç bir nesne veya nesne başvurusu verilen üyeleri seçerken, işleç bir işaretçi aracılığıyla üyeleri seçer. Bu işleçler hakkında daha fazla bilgi için, [Pointer-to-Member Operatörleri ile İfadeler](../cpp/pointer-to-member-operators-dot-star-and-star.md)bakın.

İşaretçi-üye işleçlerinin sonucu üyenin türüdür. Bu durumda, `char *`bu.

Aşağıdaki kod parçası üye işlevleri `GetCaption` `SetCaption` çağırır ve üyelere işaretçileri kullanır:

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

Statik bir üyenin adresi, üyenin işaretçisi değildir. Statik üyenin tek örneğine işaretçidir. Belirli bir sınıfın tüm nesneleri için yalnızca bir statik üye örneği vardır. Bu, normal adres-of (**&**) ve dereference (<strong>\*</strong>) işleçlerini kullanabileceğiniz anlamına gelir.

## <a name="pointers-to-members-and-virtual-functions"></a>Üye ve Sanal İşlev İşaretçileri

Bir işaretçi-üye işlevi aracılığıyla sanal bir işlev çağırmak, işlev doğrudan çağrılmış gibi çalışır. Doğru işlev v tablosunda aranır ve çağrılır.

Sanal işlevlerin çalışması, her zaman olduğu gibi bir temel sınıf işaretçisiyle çağrılmalarına bağlıdır. (Sanal işlevler hakkında daha fazla bilgi için [bkz.](../cpp/virtual-functions.md)

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
