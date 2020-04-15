---
title: İç İçe Geçmiş Sınıf Bildirimleri
ms.date: 11/04/2016
helpviewer_keywords:
- classes [C++], declaring
- declarations, class
- nested classes [C++]
- nested classes [C++], declaring
- declaring classes [C++]
- declarations, nested classes
ms.assetid: c02e471d-b7f9-41b8-8ef6-2323f006dbd5
ms.openlocfilehash: 8ace21e3c8ced72b34898a716eae882a3750c8ef
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367899"
---
# <a name="nested-class-declarations"></a>İç İçe Geçmiş Sınıf Bildirimleri

Bir sınıf başka bir sınıf kapsamında bildirilebilir. Böyle bir sınıfa "iç içe sınıf" denir. İç içe sınıflar, çevreleyen sınıfın kapsamı içinde kabul edilir ve bu kapsamda kullanılabilir. İç içe geçen bir sınıfa hemen çevreleyen kapsam dışında bir kapsamdan başvurmak için tam nitelikli bir ad kullanmanız gerekir.

Aşağıdaki örnek, iç içe sınıfların nasıl bildirilen gösterir:

```cpp
// nested_class_declarations.cpp
class BufferedIO
{
public:
   enum IOError { None, Access, General };

   // Declare nested class BufferedInput.
   class BufferedInput
   {
   public:
      int read();
      int good()
      {
         return _inputerror == None;
      }
   private:
       IOError _inputerror;
   };

   // Declare nested class BufferedOutput.
   class BufferedOutput
   {
      // Member list
   };
};

int main()
{
}
```

`BufferedIO::BufferedInput`ve `BufferedIO::BufferedOutput` içinde `BufferedIO`ilan edilir. Bu sınıf adları sınıf `BufferedIO`kapsamı dışında görünmez. Ancak, tür `BufferedIO` bir nesne türleri `BufferedInput` veya `BufferedOutput`herhangi bir nesne içermez.

İç içe geçmiş sınıflar doğrudan adları, tür adlarını, statik üyelerin adlarını ve sayısalatörleri yalnızca çevreleyen sınıftan kullanabilir. Diğer sınıf üyelerinin adlarını kullanmak için işaretçileri, başvuruları veya nesne adlarını kullanmanız gerekir.

`BufferedIO` Önceki örnekte, numaralandırma `IOError` ya `BufferedIO::BufferedInput` da `BufferedIO::BufferedOutput`işlevde `good`gösterildiği gibi iç içe sınıflarda üye işlevler tarafından doğrudan erişilebilir.

> [!NOTE]
> İç içe sınıflar yalnızca sınıf kapsamı içinde türleri bildirir. İç içe olan sınıfın içerdiği nesnelerin oluşturulmasına neden olmazlar. Önceki örnek, iç içe iki sınıf bildirir, ancak bu sınıf türlerinin herhangi bir nesnesini bildirmez.

İç içe geçen sınıf bildiriminin kapsam görünürlüğünün bir istisnası, bir tür adının bir forward bildirimiyle birlikte bildirilmesidir.  Bu durumda, iletme bildirimi tarafından bildirilen sınıf adı, kapsamı sınıf dışı en küçük kapsam olarak tanımlanan, çevreleyen sınıfın dışında görünür.  Örneğin:

```cpp
// nested_class_declarations_2.cpp
class C
{
public:
    typedef class U u_t; // class U visible outside class C scope
    typedef class V {} v_t; // class V not visible outside class C
};

int main()
{
    // okay, forward declaration used above so file scope is used
    U* pu;

    // error, type name only exists in class C scope
    u_t* pu2; // C2065

    // error, class defined above so class C scope
    V* pv; // C2065

    // okay, fully qualified name
    C::V* pv2;
}
```

## <a name="access-privilege-in-nested-classes"></a>İç içe sınıflarda ayrıcalığa erişin

Bir sınıfı başka bir sınıf içinde iç içe geçirmek, iç içe geçmiş sınıfın üye işlevlerine özel erişim ayrıcalıkları vermez. Benzer şekilde, çevreleyen sınıfın üye işlevlerinin iç içe geçmiş sınıf üyeleri için özel erişimi yoktur.

## <a name="member-functions-in-nested-classes"></a>İç içe sınıflarda üye işlevler

İç içe geçen sınıflarda bildirilen üye işlevler dosya kapsamında tanımlanabilir. Önceki örnek yazılmış olabilir:

```cpp
// member_functions_in_nested_classes.cpp
class BufferedIO
{
public:
    enum IOError { None, Access, General };
    class BufferedInput
    {
    public:
        int read(); // Declare but do not define member
        int good(); //  functions read and good.
    private:
        IOError _inputerror;
    };

    class BufferedOutput
    {
        // Member list.
    };
};
// Define member functions read and good in
//  file scope.
int BufferedIO::BufferedInput::read()
{
   return(1);
}

int BufferedIO::BufferedInput::good()
{
    return _inputerror == None;
}
int main()
{
}
```

Önceki örnekte, işlev adını bildirmek için *nitelikli tür adı* sözdizimi kullanılır. Bildirge:

```cpp
BufferedIO::BufferedInput::read()
```

"sınıfın `read` bir üyesi olan işlev" anlamına gelir. `BufferedInput` `BufferedIO` Bu bildirim *de yolduma türü adı* sözdizimini kullandığından, aşağıdaki formun yapıları mümkündür:

```cpp
typedef BufferedIO::BufferedInput BIO_INPUT;

int BIO_INPUT::read()
```

Önceki bildirim öncekine eşdeğerdir, ancak sınıf adlarının yerine **bir typedef** adı kullanır.

## <a name="friend-functions-in-nested-classes"></a>İç içe sınıflarda arkadaş işlevleri

İç içe geçen bir sınıfta bildirilen arkadaş işlevleri, çevreleyen sınıfın değil, iç içe geçen sınıfın kapsamına girer. Bu nedenle, arkadaş işlevleri, çevreleyen sınıfın üyelerine veya üye işlevlerine özel erişim ayrıcalıkları elde etmez. Bir arkadaş işlevinde iç içe geçen bir sınıfta bildirilen bir ad kullanmak istiyorsanız ve arkadaş işlevi dosya kapsamında tanımlanırsa, nitelikli tür adlarını aşağıdaki gibi kullanın:

```cpp
// friend_functions_and_nested_classes.cpp

#include <string.h>

enum
{
    sizeOfMessage = 255
};

char *rgszMessage[sizeOfMessage];

class BufferedIO
{
public:
    class BufferedInput
    {
    public:
        friend int GetExtendedErrorStatus();
        static char *message;
        static int  messageSize;
        int iMsgNo;
   };
};

char *BufferedIO::BufferedInput::message;
int BufferedIO::BufferedInput::messageSize;

int GetExtendedErrorStatus()
{
    int iMsgNo = 1; // assign arbitrary value as message number

    strcpy_s( BufferedIO::BufferedInput::message,
              BufferedIO::BufferedInput::messageSize,
              rgszMessage[iMsgNo] );

    return iMsgNo;
}

int main()
{
}
```

Aşağıdaki kod, arkadaş `GetExtendedErrorStatus` işlevi olarak bildirilen işlevi gösterir. Dosya kapsamında tanımlanan işlevde, ileti statik bir diziden sınıf üyesine kopyalanır. Daha iyi bir `GetExtendedErrorStatus` uygulama olarak ilan etmek olduğunu unutmayın:

```cpp
int GetExtendedErrorStatus( char *message )
```

Önceki arabirimde, birkaç sınıf hata iletisinin kopyalanmasını istedikleri bir bellek konumu geçirerek bu işlevin hizmetlerini kullanabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)
