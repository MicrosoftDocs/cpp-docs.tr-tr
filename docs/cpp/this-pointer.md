---
title: :::no-loc(this):::çağrısı
description: :::no-loc(this):::İşaretçi, statik olmayan üye işlevlerinde geçerli nesneye yönelik derleyici tarafından oluşturulan bir işaretçidir.
ms.date: 01/22/2020
f1_keywords:
- :::no-loc(this):::_cpp
helpviewer_keywords:
- nonstatic member functions [C++]
- 'pointers, to :::no-loc(class)::: instance'
- ':::no-loc(this)::: pointer'
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
no-loc:
- ':::no-loc(this):::'
- ':::no-loc(class):::'
- ':::no-loc(struct):::'
- ':::no-loc(union):::'
- ':::no-loc(sizeof):::'
- ':::no-loc(const):::'
- ':::no-loc(volatile):::'
ms.openlocfilehash: c851beaba7fe1091ffd7827714f90307303058c1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225832"
---
# <a name="no-locthis-pointer"></a>:::no-loc(this):::çağrısı

**`:::no-loc(this):::`** İşaretçi yalnızca **`:::no-loc(class):::`** , veya türündeki statik olmayan üye işlevlerinde erişilebilen bir işaretçisidir **`:::no-loc(struct):::`** **`:::no-loc(union):::`** . Üye işlevinin çağrıldığı nesneye işaret eder. Statik üye işlevlerinin bir işaretçisi yok **`:::no-loc(this):::`** .

## <a name="syntax"></a>Sözdizimi

```cpp
:::no-loc(this):::
:::no-loc(this):::->member-identifier
```

## <a name="remarks"></a>Açıklamalar

Nesnenin **`:::no-loc(this):::`** işaretçisi nesnenin bir parçası değildir. Nesne üzerindeki bir deyimin sonucuna yansıtılmaz **`:::no-loc(sizeof):::`** . Statik olmayan bir üye işlevi bir nesne için çağrıldığında, derleyici nesnenin adresini bir gizli bağımsız değişken olarak işleve geçirir. Örneğin, aşağıdaki işlev çağrısı:

```cpp
myDate.setMonth( 3 );
```

şöyle yorumlanabilecek:

```cpp
setMonth( &myDate, 3 );
```

Nesnenin adresi, işaretçi olarak üye işlevin içinden kullanılabilir **`:::no-loc(this):::`** . Çoğu **`:::no-loc(this):::`** işaretçi örtülü olarak kullanılır. ' Nin üyelerine başvururken açık bir şekilde kullanılması mümkün olsa da, geçerli değildir **`:::no-loc(this):::`** :::no-loc(class)::: . Örnek:

```cpp
void Date::setMonth( int mn )
{
   month = mn;            // These three statements
   :::no-loc(this):::->month = mn;      // are equivalent
   (*:::no-loc(this):::).month = mn;
}
```

İfade, **`*:::no-loc(this):::`** bir üye işlevden geçerli nesneyi döndürmek için yaygın olarak kullanılır:

```cpp
return *:::no-loc(this):::;
```

**`:::no-loc(this):::`** İşaretçi kendi kendine başvuruya karşı koruma için de kullanılır:

```cpp
if (&Object != :::no-loc(this):::) {
// do not execute in cases of self-reference
```

> [!NOTE]
> **`:::no-loc(this):::`** İşaretçi değiştirilemeyecek olduğundan, işaretçiye yönelik atamalara **`:::no-loc(this):::`** izin verilmez. C++ için izin verilen atama öncesi uygulamalar **`:::no-loc(this):::`** .

Bazen **`:::no-loc(this):::`** işaretçi doğrudan kullanılır — Örneğin, :::no-loc(struct)::: geçerli nesnenin adresinin gerekli olduğu, kendi kendine başvuran verileri gizler.

## <a name="example"></a>Örnek

```cpp
// :::no-loc(this):::_pointer.cpp
// compile with: /EHsc

#include <iostream>
#include <string.h>

using namespace std;

:::no-loc(class)::: Buf
{
public:
    Buf( char* szBuffer, size_t sizeOfBuffer );
    Buf& operator=( :::no-loc(const)::: Buf & );
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

Buf& Buf::operator=( :::no-loc(const)::: Buf &otherbuf )
{
    if( &otherbuf != :::no-loc(this)::: )
    {
        if (buffer)
            delete [] buffer;

        sizeOfBuffer =  strlen( otherbuf.buffer ) + 1;
        buffer = new char[sizeOfBuffer];
        strcpy_s( buffer, sizeOfBuffer, otherbuf.buffer );
    }
    return *:::no-loc(this):::;
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

## <a name="type-of-the-no-locthis-pointer"></a>:::no-loc(this):::İşaretçinin türü

**`:::no-loc(this):::`** İşaretçi türü, işlev bildiriminde **`:::no-loc(const):::`** ve **`:::no-loc(volatile):::`** anahtar sözcüklere göre değiştirilebilir. Bu özniteliklerin birine sahip bir işlevi bildirmek için, işlev bağımsız değişkeni listesinden sonra anahtar sözcükleri ekleyin.

Bir örnek düşünün:

```cpp
// type_of_:::no-loc(this):::_pointer1.cpp
:::no-loc(class)::: Point
{
    unsigned X() :::no-loc(const):::;
};
int main()
{
}
```

Yukarıdaki kod, `X` **`:::no-loc(this):::`** işaretçinin bir nesnenin işaretçisi olarak kabul edildiği bir üye işlevi bildirir **`:::no-loc(const):::`** **`:::no-loc(const):::`** . *CV-mod-liste* seçeneklerinin birleşimleri kullanılabilir, ancak **`:::no-loc(this):::`** işaretçi kendisi değil işaretçi tarafından işaret edilen nesneyi her zaman işaretçiye göre değiştirir. Aşağıdaki bildirim, işaretçinin bir `X` **`:::no-loc(this):::`** nesne işaretçisi olduğu işlevi bildirir **`:::no-loc(const):::`** **`:::no-loc(const):::`** :

```cpp
// type_of_:::no-loc(this):::_pointer2.cpp
:::no-loc(class)::: Point
{
    unsigned X() :::no-loc(const):::;
};
int main()
{
}
```

**`:::no-loc(this):::`** Üye işlevindeki türü aşağıdaki sözdizimi tarafından açıklanmıştır. *CV niteleyicisi listesi* , üye işlevin bildirimci öğesinden belirlenir. **`:::no-loc(const):::`** Veya **`:::no-loc(volatile):::`** (veya her ikisi de) olabilir. * :::no-loc(class)::: -tür* , öğesinin adıdır :::no-loc(class)::: :

[*CV-niteleyici-listesi*] * :::no-loc(class)::: -tür* ** \* :::no-loc(const)::: :::no-loc(this)::: **

Diğer bir deyişle, **`:::no-loc(this):::`** işaretçi her zaman bir :::no-loc(const)::: işaretçidir. Yeniden atanamaz.  **`:::no-loc(const):::`** **`:::no-loc(volatile):::`** Üye işlevi bildiriminde kullanılan veya niteleyicileri, :::no-loc(class)::: **`:::no-loc(this):::`** Bu işlevin kapsamındaki işaretçi işaret eden örneğe uygulanır.

Aşağıdaki tabloda, bu değiştiricilerin nasıl çalıştığı hakkında daha fazla bilgi verilmektedir.

### <a name="semantics-of-no-locthis-modifiers"></a>:::no-loc(this):::Değiştiricilerin semantiği

|Değiştirici|Anlamı|
|--------------|-------------|
|**`:::no-loc(const):::`**|Üye verileri değiştirilemiyor; olmayan üye işlevleri çağrılamaz **`:::no-loc(const):::`** .|
|**`:::no-loc(volatile):::`**|Üye verileri her erişildiğinde bellekten yüklenir; belirli iyileştirmeleri devre dışı bırakır.|

Bir **`:::no-loc(const):::`** nesneyi olmayan bir üye işlevine geçirmek bir hatadır **`:::no-loc(const):::`** .

Benzer şekilde, bir **`:::no-loc(volatile):::`** nesneyi olmayan bir üye işlevine geçirmek de bir hatadır **`:::no-loc(volatile):::`** .

**`:::no-loc(const):::`** Üye verilerini değiştiremediği belirtilen üye işlevleri, bu tür işlevlerde **`:::no-loc(this):::`** işaretçi bir nesne işaretçisidir **`:::no-loc(const):::`** .

> [!NOTE]
> Dolandırıcılar :::no-loc(struct)::: ve :::no-loc(struct)::: tekörler veya olarak bildirilemez **`:::no-loc(const):::`** **`:::no-loc(volatile):::`** . Ancak, **`:::no-loc(const):::`** veya **`:::no-loc(volatile):::`** nesnelerinde çağrılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)
