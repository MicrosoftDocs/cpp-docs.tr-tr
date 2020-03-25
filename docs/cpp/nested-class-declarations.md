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
ms.openlocfilehash: a1464ce9ca8349550160c768265c1c4eada93209
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161171"
---
# <a name="nested-class-declarations"></a>İç İçe Geçmiş Sınıf Bildirimleri

Bir sınıf, başka bir sınıfın kapsamı içinde bildirilebilecek. Böyle bir sınıfa "Nested Class" adı verilir. İç içe geçmiş sınıflar kapsayan sınıfın kapsamı içinde olduğu kabul edilir ve bu kapsam içinde kullanılabilir. Kendi kendine kapsayan kapsamı dışında bir kapsamdaki iç içe bir sınıfa başvurmak için, tam nitelikli bir ad kullanmanız gerekir.

Aşağıdaki örnek, iç içe sınıfların nasıl bildirilemeyeceğini göstermektedir:

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

`BufferedIO::BufferedInput` ve `BufferedIO::BufferedOutput` `BufferedIO`içinde bildirilmiştir. Bu sınıf adları, `BufferedIO`sınıfının kapsamı dışında görünür değildir. Ancak, `BufferedIO` türünde bir nesne `BufferedInput` veya `BufferedOutput`türde herhangi bir nesne içermez.

İç içe geçmiş sınıflar adları, tür adlarını, statik üyelerin adlarını ve yalnızca kapsayan sınıftan bulunan numaralandırıcıları doğrudan kullanabilir. Diğer sınıf üyelerinin adlarını kullanmak için işaretçiler, başvurular veya nesne adları kullanmanız gerekir.

Önceki `BufferedIO` örneğinde, numaralandırma `IOError` doğrudan iç içe sınıflarda, `BufferedIO::BufferedInput` veya `BufferedIO::BufferedOutput`işlev `good`gösterildiği gibi üye işlevlerle erişilebilir.

> [!NOTE]
>  İç içe sınıflar yalnızca sınıf kapsamı içindeki türleri bildirir. İç içe yerleştirilmiş sınıfın içerilen nesnelerinin oluşturulmasına neden olmaz. Yukarıdaki örnek, iki iç içe sınıf bildirir ancak bu sınıf türlerindeki herhangi bir nesne bildirmiyor.

Bir iç içe sınıf bildiriminin kapsam görünürlüğü için bir özel durum, bir tür adının bir iletme bildirimiyle birlikte bildirildiği durumdur.  Bu durumda, iletme bildirimi tarafından belirtilen sınıf adı kapsayan sınıfın dışında görünür ve kapsamı, en küçük kapsayan sınıf olmayan kapsam olarak tanımlanır.  Örneğin:

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

## <a name="access-privilege-in-nested-classes"></a>İç içe sınıflarda erişim ayrıcalığı

Bir sınıfı başka bir sınıf içinde iç içe geçirmek, iç içe geçmiş sınıfın üye işlevlerine özel erişim ayrıcalıkları vermez. Benzer şekilde, çevreleyen sınıfın üye işlevlerinin iç içe geçmiş sınıf üyeleri için özel erişimi yoktur.

## <a name="member-functions-in-nested-classes"></a>İç içe sınıflarda üye işlevleri

İç içe sınıflarda belirtilen üye işlevleri, dosya kapsamında tanımlanabilir. Yukarıdaki örnek yazılmış olabilir:

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

Önceki örnekte, *tam tür adı* sözdizimi işlev adını bildirmek için kullanılır. Bildirim:

```cpp
BufferedIO::BufferedInput::read()
```

, `BufferedIO` sınıfının kapsamındaki `BufferedInput` sınıfının bir üyesi olan `read` işlevi anlamına gelir. " Bu bildirim *tam tür adı* sözdizimini kullandığından, aşağıdaki formun yapıları olasıdır:

```cpp
typedef BufferedIO::BufferedInput BIO_INPUT;

int BIO_INPUT::read()
```

Önceki bildirim öncekiyle eşdeğerdir, ancak sınıf adlarının yerine bir **typedef** adı kullanır.

## <a name="friend-functions-in-nested-classes"></a>İç içe sınıflarda arkadaş işlevleri

İç içe yerleştirilmiş bir sınıfta belirtilen arkadaş işlevleri, kapsayan sınıfın değil, iç içe yerleştirilmiş sınıfın kapsamında olduğu kabul edilir. Bu nedenle arkadaş işlevleri, kapsayan sınıfın üyeleri veya üye işlevleri için özel erişim ayrıcalıklarına sahip olmaz. Bir Friend işlevindeki iç içe yerleştirilmiş bir sınıfta belirtilen bir ad kullanmak istiyorsanız ve arkadaş işlevi dosya kapsamında tanımlanmışsa, tam tür adlarını aşağıdaki gibi kullanın:

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

Aşağıdaki kod, bir Friend işlevi olarak bildirildiği `GetExtendedErrorStatus` işlevi gösterir. Dosya kapsamında tanımlanan işlevde bir ileti bir statik diziden sınıf üyesine kopyalanır. `GetExtendedErrorStatus` daha iyi bir uygulamanın bunu şöyle bildirdiğine unutmayın:

```cpp
int GetExtendedErrorStatus( char *message )
```

Önceki arabirim ile, birkaç sınıf, hata iletisinin kopyalanmasını istedikleri bir bellek konumunu geçirerek bu işlevin hizmetlerini kullanabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)
