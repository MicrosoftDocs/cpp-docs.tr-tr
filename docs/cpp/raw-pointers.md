---
title: Ham işaretçiler (C++)
description: C++ ' ta ham işaretçiler kullanma
ms.date: 04/21/2020
helpviewer_keywords:
- pointers [C++]
no-loc:
- ':::no-loc(void):::'
- ':::no-loc(nullptr):::'
- ':::no-loc(const):::'
- ':::no-loc(char):::'
- ':::no-loc(new):::'
- ':::no-loc(delete):::'
ms.openlocfilehash: 53679559888191fe7f2aad7cb5a70d607974ae96
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233658"
---
# <a name="raw-pointers-c"></a>Ham işaretçiler (C++)

*İşaretçi* bir değişken türüdür. Bir nesnenin adresini bellekte depolar ve bu nesneye erişmek için kullanılır. *Ham işaretçi* , yaşam süresi [akıllı bir işaretçi](smart-pointers-modern-cpp.md)gibi bir Kapsülleyici nesne tarafından denetlenmeyen bir işaretçisidir. Bir ham işaretçiye başka bir işaretçi olmayan değişkenin adresi atanabilir veya bir değeri atanabilir [:::no-loc(nullptr):::](:::no-loc(nullptr):::.md) . Değer atanmamış bir işaretçi rastgele veri içeriyor.

Ayrıca, işaret ettiği nesnenin değerini almak için bir işaretçiye de *başvurulmalıdır* . *Üye erişim işleci* , bir nesnenin üyelerine erişim sağlar.

```cpp
    int* p = :::no-loc(nullptr):::; // declare pointer and initialize it
                      // so that it doesn't store a random address
    int i = 5;
    p = &i; // assign pointer to address of object
    int j = *p; // dereference p to retrieve the value at its address
```

Bir işaretçi, türü belirlenmiş bir nesneye veya öğesine işaret edebilir **`:::no-loc(void):::`** . Bir program bellekte [yığında](https://wikipedia.org/wiki/Heap) bir nesne ayırdığında, bu nesnenin adresini işaretçi biçiminde alır. Bu tür işaretçilere *sahip işaretçiler*denir. Artık gerekli olmadığında yığın tarafından ayrılan nesneyi açıkça serbest bırakmak için, sahip olan bir işaretçinin (veya bir kopyasının) kullanılması gerekir. Bellek *sızıntısına*neden olan belleği serbest bırakma başarısız olur ve bu bellek konumunu makinedeki başka bir program için kullanılamaz hale işler. Kullanılarak ayrılan bellek **`:::no-loc(new):::`** **`:::no-loc(delete):::`** (veya ** :::no-loc(delete)::: \[ ]**) kullanılarak serbest bırakılmalıdır. Daha fazla bilgi için bkz. [ :::no-loc(new)::: ve :::no-loc(delete)::: işleçleri](:::no-loc(new):::-and-:::no-loc(delete):::-operators.md).

```cpp
    MyClass* mc = :::no-loc(new)::: MyClass(); // allocate object on the heap
    mc->print(); // access class member
    :::no-loc(delete)::: mc; // :::no-loc(delete)::: object (please don't forget!)
```

Bir işaretçi (olarak bildirilirse **`:::no-loc(const):::`** ), bellekte başka bir konuma işaret etmek için arttırılır veya azaltılır. Bu işlem *işaretçi aritmetiği*olarak adlandırılır. Diziler veya diğer veri yapılarında öğeleri yinelemek için C stili programlamada kullanılır. **`:::no-loc(const):::`** Farklı bir bellek konumuna işaret etmek için bir işaretçi yapılamaz ve bu anlamlı bir [başvuruya](references-cpp.md)benzerdir. Daha fazla bilgi için bkz. [ :::no-loc(const)::: ve geçici işaretçiler](:::no-loc(const):::-and-volatile-pointers.md).

```cpp
    // declare a C-style string. Compiler adds terminating '\0'.
    :::no-loc(const)::: :::no-loc(char):::* str = "Hello world";

    :::no-loc(const)::: int c = 1;
    :::no-loc(const)::: int* p:::no-loc(const)::: = &c; // declare a non-:::no-loc(const)::: pointer to :::no-loc(const)::: int
    :::no-loc(const)::: int c2 = 2;
    p:::no-loc(const)::: = &c2;  // OK p:::no-loc(const)::: itself isn't :::no-loc(const):::
    :::no-loc(const)::: int* :::no-loc(const)::: p:::no-loc(const):::2 = &c;
    // p:::no-loc(const):::2 = &c2; // Error! p:::no-loc(const):::2 is :::no-loc(const):::.
```

64 bit işletim sistemlerinde, bir işaretçinin boyutu 64 bittir. Sistemin işaretçi boyutu, ne kadar adreslenebilir bellek olduğunu belirler. Bir işaretçinin tüm kopyaları aynı bellek konumuna işaret noktasıdır. İşaretçiler (başvurularla birlikte), C++ ' da daha büyük nesneler ve işlevlere daha fazla nesne geçirmek için yaygın olarak kullanılır. Bunun nedeni genellikle nesnenin adresinin tüm nesneyi kopyalamaktan daha etkili olması. Bir işlevi tanımlarken, **`:::no-loc(const):::`** nesneyi değiştirmek için işlevi belirtmediğiniz sürece işaretçi parametreleri belirtin. Genel olarak, **`:::no-loc(const):::`** nesneler, nesne değeri belki de olabilir değilse nesneleri işlevlere geçirmek için tercih edilen yoldur **`:::no-loc(nullptr):::`** .

[Işlevlerin işaretçileri](#pointers_to_functions) , işlevlerin diğer işlevlere geçirilmesini sağlar ve C stili programlamada "geri aramalar" için kullanılır. Modern C++, bu amaçla [lambda ifadeleri](lambda-expressions-in-cpp.md) kullanır.

## <a name="initialization-and-member-access"></a>Başlatma ve üye erişimi

Aşağıdaki örnek, bir ham işaretçinin nasıl bildirilemeyeceğini, başlatılacağını ve kullanılacağını gösterir. **`:::no-loc(new):::`** Yığın üzerinde ayrılmış bir nesneyi işaret etmek üzere kullanılarak başlatılır ve bu, açıkça yapmanız gerekir **`:::no-loc(delete):::`** . Örnek, ham işaretçilerle ilişkili bazı tehlikeler de gösterilmektedir. (Bu örnek C stili bir programlama, modern C++ değil!) olduğunu unutmayın!)

```cpp
#include <iostream>
#include <string>

class MyClass
{
public:
    int num;
    std::string name;
    :::no-loc(void)::: print() { std::cout << name << ":" << num << std::endl; }
};

// Accepts a MyClass pointer
:::no-loc(void)::: func_A(MyClass* mc)
{
    // Modify the object that mc points to.
    // All copies of the pointer will point to
    // the same modified object.
    mc->num = 3;
}

// Accepts a MyClass object
:::no-loc(void)::: func_B(MyClass mc)
{
    // mc here is a regular object, not a pointer.
    // Use the "." operator to access members.
    // This statement modifies only the local copy of mc.
    mc.num = 21;
    std::cout << "Local copy of mc:";
    mc.print(); // "Erika, 21"
}


int main()
{
    // Use the * operator to declare a pointer type
    // Use :::no-loc(new)::: to allocate and initialize memory
    MyClass* pmc = :::no-loc(new)::: MyClass{ 108, "Nick" };

    // Prints the memory address. Usually not what you want.
    std:: cout << pmc << std::endl;

    // Copy the pointed-to object by dereferencing the pointer
    // to access the contents of the memory location.
    // mc is a separate object, allocated here on the stack
    MyClass mc = *pmc;

    // Declare a pointer that points to mc using the addressof operator
    MyClass* pcopy = &mc;

    // Use the -> operator to access the object's public members
    pmc->print(); // "Nick, 108"

    // Copy the pointer. Now pmc and pmc2 point to same object!
    MyClass* pmc2 = pmc;

    // Use copied pointer to modify the original object
    pmc2->name = "Erika";
    pmc->print(); // "Erika, 108"
    pmc2->print(); // "Erika, 108"

    // Pass the pointer to a function.
    func_A(pmc);
    pmc->print(); // "Erika, 3"
    pmc2->print(); // "Erika, 3"

    // Dereference the pointer and pass a copy
    // of the pointed-to object to a function
    func_B(*pmc);
    pmc->print(); // "Erika, 3" (original not modified by function)

    :::no-loc(delete):::(pmc); // don't forget to give memory back to operating system!
   // :::no-loc(delete):::(pmc2); //crash! memory location was already :::no-loc(delete):::d
}
```

## <a name="pointer-arithmetic-and-arrays"></a>İşaretçi aritmetik ve dizileri

İşaretçiler ve diziler yakından ilgilidir. Bir dizi değere göre bir işleve geçirildiğinde, ilk öğeye işaretçi olarak geçirilir. Aşağıdaki örnek, işaretçilerin ve dizilerin aşağıdaki önemli özelliklerini gösterir:

- **`sizeof`** işleci, bir dizinin bayt cinsinden toplam boyutunu döndürür
- öğelerin sayısını öğrenmek için, toplam baytları bir öğe boyutuna bölün
- bir dizi bir işleve geçirildiğinde bir işaretçi *türü olur*
- **`sizeof`** bir işaretçiye uygulandığında operatör, x64 üzerinde 5 bayt veya 8 bayt üzerinde işaretçi boyutunu döndürür

```cpp
#include <iostream>

:::no-loc(void)::: func(int arr[], int length)
{
    // returns pointer size. not useful here.
    size_t test = sizeof(arr);

    for(int i = 0; i < length; ++i)
    {
        std::cout << arr[i] << " ";
    }
}

int main()
{

    int i[5]{ 1,2,3,4,5 };
    // sizeof(i) = total bytes
    int j = sizeof(i) / sizeof(i[0]);
    func(i,j);
}
```

Bazı aritmetik işlemler, :::no-loc(const)::: başka bir bellek konumuna işaret etmek için işaretçilerden farklı kullanılabilir. İşaretçiler artar ve **++** , **+=** , **-=** ve işleçleri kullanılarak azaltılır **--** . Bu teknik diziler için kullanılabilir ve özellikle türsüz verilerin arabelleklerinde faydalıdır. **:::no-loc(void):::\***, Bir **`:::no-loc(char):::`** (1 baytlık) boyutuna göre artırılır. Yazılı bir işaretçi, işaret ettiği türün boyutuyla artırılır.

Aşağıdaki örnek, Windows üzerindeki bir bit eşlemdeki tek tek piksellere erişmek için işaretçi aritmetiğinin nasıl kullanılabileceğini gösterir. **`:::no-loc(new):::`** Ve **`:::no-loc(delete):::`** ' nin ve başvuru işlecinin kullanımını dikkate alın.

```cpp
#include <Windows.h>
#include <fstream>

using namespace std;

int main()
{

    BITMAPINFOHEADER header;
    header.biHeight = 100; // Multiple of 4 for simplicity.
    header.biWidth = 100;
    header.biBitCount = 24;
    header.biPlanes = 1;
    header.biCompression = BI_RGB;
    header.biSize = sizeof(BITMAPINFOHEADER);

    :::no-loc(const):::expr int bufferSize = 30000;
    unsigned :::no-loc(char):::* buffer = :::no-loc(new)::: unsigned :::no-loc(char):::[bufferSize];

    BITMAPFILEHEADER bf;
    bf.bfType = 0x4D42;
    bf.bfSize = header.biSize + 14 + bufferSize;
    bf.bfReserved1 = 0;
    bf.bfReserved2 = 0;
    bf.bfOffBits = sizeof(BITMAPFILEHEADER) + sizeof(BITMAPINFOHEADER); //54

    // Create a gray square with a 2-pixel wide outline.
    unsigned :::no-loc(char):::* begin = &buffer[0];
    unsigned :::no-loc(char):::* end = &buffer[0] + bufferSize;
    unsigned :::no-loc(char):::* p = begin;
    :::no-loc(const):::expr int pixelWidth = 3;
    :::no-loc(const):::expr int borderWidth = 2;

    while (p < end)
    {
            // Is top or bottom edge?
        if ((p < begin + header.biWidth * pixelWidth * borderWidth)
            || (p > end - header.biWidth * pixelWidth * borderWidth)
            // Is left or right edge?
            || (p - begin) % (header.biWidth * pixelWidth) < (borderWidth * pixelWidth)
            || (p - begin) % (header.biWidth * pixelWidth) > ((header.biWidth - borderWidth) * pixelWidth))
        {
            *p = 0x0; // Black
        }
        else
        {
            *p = 0xC3; // Gray
        }
        p++; // Increment one byte sizeof(unsigned :::no-loc(char):::).
    }

    ofstream wf(R"(box.bmp)", ios::out | ios::binary);

    wf.write(reinterpret_cast<:::no-loc(char):::*>(&bf), sizeof(bf));
    wf.write(reinterpret_cast<:::no-loc(char):::*>(&header), sizeof(header));
    wf.write(reinterpret_cast<:::no-loc(char):::*>(begin), bufferSize);

    :::no-loc(delete):::[] buffer; // Return memory to the OS.
    wf.close();
}
```

## <a name="no-locvoid-pointers"></a>:::no-loc(void):::* işaretçiler

Bir işaretçi **`:::no-loc(void):::`** yalnızca ham bellek konumunu işaret eder. Bazen **:::no-loc(void):::\*** , örneğin C++ kodu ve C işlevleri arasında geçiş yaparken işaretçiler kullanılması gerekir.

Belirlenmiş bir işaretçi bir :::no-loc(void)::: işaretçiye ayarlandığında, bellek konumunun içeriği değiştirilmez. Ancak, tür bilgileri kaybedilir, böylece artırma veya azaltma işlemleri yapamazsınız. Bir bellek konumu, örneğin, ve ' den ' A kadar arasında tür oluşturulabilir `MyClass*` **`:::no-loc(void):::*`** `MyClass*` . Bu gibi işlemler, doğal olarak hataya açıktır ve hatalara yönelik harika bir sorun olması gerekir :::no-loc(void)::: . Modern C++, :::no-loc(void)::: neredeyse tüm koşullarda işaretçiler etkilenmeden.

```cpp

//func.c
:::no-loc(void)::: func(:::no-loc(void):::* data, int length)
{
    :::no-loc(char):::* c = (:::no-loc(char):::*)(data);

    // fill in the buffer with data
    for (int i = 0; i < length; ++i)
    {
        *c = 0x41;
        ++c;
    }
}

// main.cpp
#include <iostream>

extern "C"
{
    :::no-loc(void)::: func(:::no-loc(void):::* data, int length);
}

class MyClass
{
public:
    int num;
    std::string name;
    :::no-loc(void)::: print() { std::cout << name << ":" << num << std::endl; }
};

int main()
{
    MyClass* mc = :::no-loc(new)::: MyClass{10, "Marian"};
    :::no-loc(void):::* p = static_cast<:::no-loc(void):::*>(mc);
    MyClass* mc2 = static_cast<MyClass*>(p);
    std::cout << mc2->name << std::endl; // "Marian"

    // use operator :::no-loc(new)::: to allocate untyped memory block
    :::no-loc(void):::* p:::no-loc(void)::: = operator :::no-loc(new):::(1000);
    :::no-loc(char):::* p:::no-loc(char)::: = static_cast<:::no-loc(char):::*>(p:::no-loc(void):::);
    for(:::no-loc(char):::* c = p:::no-loc(char):::; c < p:::no-loc(char)::: + 1000; ++c)
    {
        *c = 0x00;
    }
    func(p:::no-loc(void):::, 1000);
    :::no-loc(char)::: ch = static_cast<:::no-loc(char):::*>(p:::no-loc(void):::)[0];
    std::cout << ch << std::endl; // 'A'
    operator :::no-loc(delete):::(p);
}
```

## <a name="pointers-to-functions"></a><a name="pointers_to_functions"></a>İşlevlere işaretçiler

C stili programlamada, işlev işaretçileri birincil olarak işlevleri diğer işlevlere geçirmek için kullanılır. Bu teknik, çağıranın, bir işlevin davranışını değiştirmeden özelleştirmesini sağlar. Modern C++ ' da, [lambda ifadeleri](lambda-expressions-in-cpp.md) daha büyük tür güvenliği ve diğer avantajlar ile aynı özelliği sağlar.

Bir işlev işaretçisi bildirimi, işaret eden işlevin sahip olması gereken imzayı belirtir:

```cpp
// Declare pointer to any function that...

// ...accepts a string and returns a string
string (*g)(string a);

// has no return value and no parameters
:::no-loc(void)::: (*x)();

// ...returns an int and takes three parameters
// of the specified types
int (*i)(int i, string s, double d);
```

Aşağıdaki örnek, `combine` bir parametresi olarak alan ve döndüren bir işlevi gösterir `std::string` `std::string` . Öğesine geçirilen işleve bağlı olarak `combine` , bu ya da bir dize ekler veya ekler.

```cpp
#include <iostream>
#include <string>

using namespace std;

string base {"hello world"};

string append(string s)
{
    return base.append(" ").append(s);
}

string prepend(string s)
{
    return s.append(" ").append(base);
}

string combine(string s, string(*g)(string a))
{
    return (*g)(s);
}

int main()
{
    cout << combine("from MSVC", append) << "\n";
    cout << combine("Good morning and", prepend) << "\n";
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Akıllı işaretçiler](smart-pointers-modern-cpp.md) 
 [Yöneltme işleci: *](indirection-operator-star.md)<br/>
[Address-of İşleci: &](address-of-operator-amp.md)</br>
[C++ ' a geri hoş geldiniz](welcome-back-to-cpp-modern-cpp.md)
