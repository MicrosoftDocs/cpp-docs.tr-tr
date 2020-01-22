---
title: this işaretçisi
description: this işaretçi, statik olmayan üye işlevlerinde geçerli nesneye yönelik derleyici tarafından oluşturulan bir işaretçidir.
ms.date: 01/22/2020
f1_keywords:
- this_cpp
helpviewer_keywords:
- nonstatic member functions [C++]
- pointers, to class instance
- this pointer
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
no-loc:
- this
- class
- struct
- union
- sizeof
- const
- volatile
ms.openlocfilehash: 58bba2edd7a457c624b747b5a65d209995852848
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518341"
---
# <a name="opno-locthis-pointer"></a>this işaretçisi

**this** işaretçi, yalnızca bir **class** , **struct** veya **union** türünün statik olmayan üye işlevlerinde erişilebilen bir işaretçisidir. Üye işlevinin çağrıldığı nesneye işaret eder. Statik üye işlevleri **this** işaretçisine sahip değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
this
this->member-identifier
```

## <a name="remarks"></a>Açıklamalar

Nesnenin **this** işaretçisi nesnenin kendisinin bir parçası değildir. Nesne üzerindeki bir **sizeof** deyimin sonucuna yansıtılmaz. Statik olmayan bir üye işlevi bir nesne için çağrıldığında, derleyici nesnenin adresini bir gizli bağımsız değişken olarak işleve geçirir. Örneğin, aşağıdaki işlev çağrısı:

```cpp
myDate.setMonth( 3 );
```

şöyle yorumlanabilecek:

```cpp
setMonth( &myDate, 3 );
```

Nesnenin adresi, **this** işaretçisi olarak üye işlevin içinden kullanılabilir. Çoğu **this** işaretçisi kullanımları örtük. classüyelerine başvuru yaparken açık bir **this** kullanmak da gereksizdir. Örneğin:

```cpp
void Date::setMonth( int mn )
{
   month = mn;            // These three statements
   this->month = mn;      // are equivalent
   (*this).month = mn;
}
```

`*this` ifadesi bir üye işlevinden geçerli nesneyi döndürmek için yaygın olarak kullanılır:

```cpp
return *this;
```

**this** işaretçi kendi kendine başvuruya karşı koruma için de kullanılır:

```cpp
if (&Object != this) {
// do not execute in cases of self-reference
```

> [!NOTE]
> **this** işaretçi değiştirilemeyecek olduğundan, **this** işaretçisine yönelik atamalara izin verilmez. C++ **this** için izin verilen atama öncesi uygulamalar.

Bazen **this** işaretçi doğrudan kullanılır — Örneğin, geçerli nesnenin adresinin gerekli olduğu kendi kendine başvuran veri yapılarını değiştirmek için.

## <a name="example"></a>Örnek

```cpp
// this_pointer.cpp
// compile with: /EHsc

#include <iostream>
#include <string.h>

using namespace std;

class Buf
{
public:
    Buf( char* szBuffer, size_t sizeOfBuffer );
    Buf& operator=( const Buf & );
    void Display() { cout << buffer << endl; }

private:
    char*   buffer;
    size_t  sizeOfBuffer;
};

Buf::Buf( char* szBuffer, size_t sizeOfBuffer )
{
    sizeOfBuffer++; // account for a NULL terminator

    buffer = new char[ sizeOfBuffer ];
    if (buffer)
    {
        strcpy_s( buffer, sizeOfBuffer, szBuffer );
        sizeOfBuffer = sizeOfBuffer;
    }
}

Buf& Buf::operator=( const Buf &otherbuf )
{
    if( &otherbuf != this )
    {
        if (buffer)
            delete [] buffer;

        sizeOfBuffer =  strlen( otherbuf.buffer ) + 1;
        buffer = new char[sizeOfBuffer];
        strcpy_s( buffer, sizeOfBuffer, otherbuf.buffer );
    }
    return *this;
}

int main()
{
    Buf myBuf( "my buffer", 10 );
    Buf yourBuf( "your buffer", 12 );

    // Display 'my buffer'
    myBuf.Display();

    // assignment operator
    myBuf = yourBuf;

    // Display 'your buffer'
    myBuf.Display();
}
```

```Output
my buffer
your buffer
```

## <a name="type-of-the-opno-locthis-pointer"></a>this işaretçisinin türü

**this** işaretçisinin türü, işlev bildiriminde **const** ve **volatile** anahtar sözcükleriyle değiştirilebilir. Bu özniteliklerin birine sahip bir işlevi bildirmek için, işlev bağımsız değişkeni listesinden sonra anahtar sözcükleri ekleyin.

Bir örnek düşünün:

```cpp
// type_of_this_pointer1.cpp
class Point
{
    unsigned X() const;
};
int main()
{
}
```

Yukarıdaki kod, **this** işaretçisinin **const** nesnesine **const** işaretçi olarak kabul edildiği `X`bir üye işlevi bildirir. *CV-mod-liste* seçeneklerinin birleşimleri kullanılabilir, ancak işaretçi kendisini değil **this** işaretçisi tarafından işaret edilen nesneyi her zaman değiştirir. Aşağıdaki bildirim, **this** işaretçisinin bir **const** nesnesine **const** işaretçisi olduğu işlev `X`bildirir:

```cpp
// type_of_this_pointer2.cpp
class Point
{
    unsigned X() const;
};
int main()
{
}
```

Bir üye işlevindeki **this** türü aşağıdaki sözdizimi tarafından açıklanmıştır. *CV niteleyicisi listesi* , üye işlevin bildirimci öğesinden belirlenir. **const** veya **volatile** (ya da her ikisi) olabilir. *classtürü* classadıdır:

[*CV-niteleyici-listesi*] *classtürü* **\* const this**

Diğer bir deyişle **this** işaretçisi her zaman bir const işaretçidir. Yeniden atanamaz.  Üye işlevi bildiriminde kullanılan **const** veya **volatile** niteleyicileri, bu işlevin kapsamındaki **this** işaretçi noktaları class örneğine uygulanır.

Aşağıdaki tabloda, bu değiştiricilerin nasıl çalıştığı hakkında daha fazla bilgi verilmektedir.

### <a name="semantics-of-opno-locthis-modifiers"></a>this değiştiricilerin semantiği

|Değiştirici|Açıklama|
|--------------|-------------|
|**const**|Üye verileri değiştirilemiyor; **const** olmayan üye işlevleri çağrılamaz.|
|**volatile**|Üye verileri her erişildiğinde bellekten yüklenir; belirli iyileştirmeleri devre dışı bırakır.|

**const** nesnesini **const** olmayan bir üye işlevine geçirmek hatadır.

Benzer şekilde, bir **volatile** nesnesini **volatile** olmayan bir üye işlevine geçirmek da hatadır.

**const** olarak belirtilen üye işlevleri üye verilerini değiştirememelidir — bu tür işlevlerde **this** işaretçisi **const** nesnesine yönelik bir işaretçidir.

> [!NOTE]
> Oluşturucular ve Yıkıcılar **const** veya **volatile** olarak bildirilemez. Ancak, **const** veya **volatile** nesnelerinde çağrılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)
