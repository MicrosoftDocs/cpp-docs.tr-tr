---
title: Ham işaretçiler (C++)
description: İçinde ham işaretçiler kullanmaC++
ms.date: 11/19/2019
helpviewer_keywords:
- pointers [C++]
ms.openlocfilehash: 2dbb4f11fc0c08578e82371e8df77e9643313879
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077143"
---
# <a name="raw-pointers-c"></a>Ham işaretçiler (C++)

İşaretçi, bellekteki bir nesnenin adresini depolayan ve bu nesneye erişmek için kullanılan bir değişken türüdür. *Ham işaretçi* , yaşam süresi [akıllı bir işaretçi](smart-pointers-modern-cpp.md)gibi bir Kapsülleyici nesne tarafından denetlenmeyen bir işaretçisidir. Bir ham işaretçiye başka bir işaretçi olmayan değişkenin adresi atanabilir veya bir [nullptr](nullptr.md)değeri atanabilir. Değer atanmamış bir işaretçi rastgele veri içeriyor.

Ayrıca, işaret ettiği nesnenin değerini almak için bir işaretçiye de *başvurulmalıdır* . *Üye erişim işleci* , bir nesnenin üyelerine erişim sağlar.

```cpp
    int* p = nullptr; // declare pointer and initialize it
                      // so that it doesn't store a random address
    int i = 5;
    p = &i; // assign pointer to address of object
    int j = *p; // dereference p to retrieve the value at its address

```

Bir işaretçi, yazılan bir nesneyi işaret edebilir veya **void**. Bir program, bellekte [yığında](https://wikipedia.org/wiki/Heap) yeni bir nesne ayırdığında, bu nesnenin adresini işaretçi biçiminde alır. Bu tür işaretçiler *sahip işaretçiler*olarak adlandırılır; artık gerekli olmadığında yığın tarafından ayrılan nesneyi açıkça silmek için, sahip olan bir işaretçinin (veya bir kopyasının) kullanılması gerekir. Bellek *sızıntısına* neden olan belleği silme hatası ve bu bellek konumunu makinedeki diğer herhangi bir program için kullanılamaz hale göre işler. Daha fazla bilgi için bkz. [New ve delete işleçleri](new-and-delete-operators.md).

```cpp

    MyClass* mc = new MyClass(); // allocate object on the heap
    mc->print(); // access class member
    delete mc; // delete object (please don't forget!)
```

Bir işaretçi ( **const**olarak bildirilmemiş), bellekteki yeni bir konuma işaret etmek için arttırılır veya azaltılır. Bu, *işaretçi aritmetiği* olarak adlandırılır ve diziler ya da diğer veri yapılarında öğeleri yinelemek için C stili programlamada kullanılır. Bir **const** işaretçisi, farklı bir bellek konumunu işaret etmek için yapılamaz ve bu anlamlı bir [başvuruya](references-cpp.md)çok benzer. Daha fazla bilgi için bkz. [const ve volatile işaretçileri](const-and-volatile-pointers.md).

```cpp
    // declare a C-style string. Compiler adds terminating '\0'.
    const char* str = "Hello world";

    const int c = 1;
    const int* pconst = &c; // declare a non-const pointer to const int
    const int c2 = 2;
    pconst = &c2;  // OK pconst itself isn't const
    const int* const pconst2 = &c;
    // pconst2 = &c2; // Error! pconst2 is const.
```

64 bit işletim sistemlerinde, bir işaretçinin boyutu 64 bittir; sistemin işaretçi boyutu, ne kadar adreslenebilir bellek olduğunu belirler. Bir işaretçinin tüm kopyaları aynı bellek konumuna işaret noktasıdır. İşaretçiler (başvurularla birlikte), bir nesnenin 64 C++ bitlik adresini kopyalamak için bir nesnenin tamamını kopyalamaya kıyasla büyük nesneleri çok daha verimli bir şekilde geçirmek için kapsamlı olarak kullanılır. Bir işlevi tanımlarken, işlevin nesneyi değiştirmesini istemediğiniz sürece işaretçi parametrelerini **const** olarak belirtin. Genel olarak, **const** başvuruları, nesne değeri muhtemelen **nullptr**değilse, nesneleri işlevlere geçirmek için tercih edilen yoldur.

[Işlevlerin işaretçileri](#pointers_to_functions) , işlevlerin diğer işlevlere geçirilmesini sağlar ve C stili programlamada "geri aramalar" için kullanılır. Modern C++ , bu amaçla [lambda ifadeleri](lambda-expressions-in-cpp.md) kullanır.

## <a name="initialization-and-member-access"></a>Başlatma ve üye erişimi

Aşağıdaki örnek, bir ham işaretçinin nasıl bildirilemeyeceğini ve yığın üzerinde ayrılmış bir nesneyle nasıl başlatılacağını ve ardından nasıl kullanılacağını gösterir. Ayrıca, ham işaretçilerle ilişkili bazı tehlikeler de gösterilmektedir. (Bu, C stili bir programlama ve modern C++değil!)

```cpp
#include <iostream>
#include <string>

class MyClass
{
public:
    int num;
    std::string name;
    void print() { std::cout << name << ":" << num << std::endl; }
};

// Accepts a MyClass pointer
void func_A(MyClass* mc)
{
    // Modify the object that mc points to.
    // All copies of the pointer will point to
    // the same modified object.
    mc->num = 3;
}

// Accepts a MyClass object
void func_B(MyClass mc)
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
    // Use new to allocate and initialize memory
    MyClass* pmc = new MyClass{ 108, "Nick" };

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
    func_A(mc);
    pmc->print(); // "Erika, 3"
    pmc2->print(); // "Erika, 3"

    // Dereference the pointer and pass a copy
    // of the pointed-to object to a function
    func_B(*mc);
    pmc->print(); // "Erika, 3" (original not modified by function)

    delete(pmc); // don't forget to give memory back to operating system!
   // delete(pmc2); //crash! memory location was already deleted
}
```

## <a name="pointer-arithmetic-and-arrays"></a>İşaretçi aritmetik ve dizileri

İşaretçiler ve diziler yakından ilgilidir. Bir dizi değere göre bir işleve geçirildiğinde, ilk öğeye işaretçi olarak geçirilir. Aşağıdaki örnek, işaretçilerin ve dizilerin aşağıdaki önemli özelliklerini gösterir:

- `sizeof` işleci, bir dizinin bayt cinsinden toplam boyutunu döndürür
- öğelerin sayısını öğrenmek için, toplam baytları bir öğe boyutuna bölün
- bir dizi bir işleve geçirildiğinde bir işaretçi *türü olur*
- bir işaretçiye uygulandığında `sizeof` işleci, x64 üzerinde 5 bayt veya 8 bayt üzerinde işaretçi boyutunu döndürür

```cpp
#include <iostream>

void func(int arr[], int length)
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

Belirli aritmetik işlemler, yeni bir bellek konumuna işaret etmek üzere const olmayan işaretçilerde gerçekleştirilebilir. **++** , **+=** , **-=** ve **--** işleçlerini kullanarak bir işaretçi arttırılır ve azaltılır. Bu teknik diziler için kullanılabilir ve özellikle türsüz verilerin arabelleklerinde faydalıdır. **Void\*** bir **char** (1 baytlık) boyutuna göre artar. Yazılı bir işaretçi, işaret ettiği türün boyutuna göre artar.

Aşağıdaki örnek, Windows üzerindeki bir bit eşlemdeki tek tek piksellere erişmek için işaretçi aritmetiğinin nasıl kullanılabileceğini gösterir. **Yeni** ve **Sil**'in kullanımını ve başvuru işlecinin olduğunu aklınızda edin.

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

    constexpr int bufferSize = 30000;
    unsigned char* buffer = new unsigned char[bufferSize];

    BITMAPFILEHEADER bf;
    bf.bfType = 0x4D42;
    bf.bfSize = header.biSize + 14 + bufferSize;
    bf.bfReserved1 = 0;
    bf.bfReserved2 = 0;
    bf.bfOffBits = sizeof(BITMAPFILEHEADER) + sizeof(BITMAPINFOHEADER); //54

    // Create a gray square with a 2-pixel wide outline.
    unsigned char* begin = &buffer[0];
    unsigned char* end = &buffer[0] + bufferSize;
    unsigned char* p = begin;
    constexpr int pixelWidth = 3;
    constexpr int borderWidth = 2;

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
        p++; // Increment one byte sizeof(unsigned char).
    }

    ofstream wf(R"(box.bmp)", ios::out | ios::binary);

    wf.write(reinterpret_cast<char*>(&bf), sizeof(bf));
    wf.write(reinterpret_cast<char*>(&header), sizeof(header));
    wf.write(reinterpret_cast<char*>(begin), bufferSize);

    delete[] buffer; // Return memory to the OS.
    wf.close();
}
```

## <a name="void-pointers"></a>void * işaretçileri

**Void** işaretçisi, ham bellek konumunu işaret eder. Bazen kod ve C işlevleri arasında C++ geçiş yaparken **void\*** işaretçilerinin kullanılması gerekir.

Yazılı bir işaretçi void işaretçiye ayarlandığında, bellek konumunun içeriği değiştirilmez, ancak artış veya azaltma işlemlerini gerçekleştirebilmek için tür bilgileri kaybedilir. Bir bellek konumu, örneğin MyClass * öğesinden void * ve yeniden MyClass * öğesine dönüşebilir. Bu gibi işlemler, doğal olarak hataya açıktır ve hataları önlemek için harika bir fikir gerektirir. Modern C++ etkilenmeden, kesin bir şekilde gerekmedikçe void işaretçilerinin kullanımını kullanır.

```cpp

//func.c
void func(void* data, int length)
{
    char* c = (char*)(data);

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
    void func(void* data, int length);
}

class MyClass
{
public:
    int num;
    std::string name;
    void print() { std::cout << name << ":" << num << std::endl; }
};

int main()
{
    MyClass* mc = new MyClass{10, "Marian"};
    void* p = static_cast<void*>(mc);
    MyClass* mc2 = static_cast<MyClass*>(p);
    std::cout << mc2->name << std::endl; // "Marian"

    // use operator new to allocate untyped memory block
    void* pvoid = operator new(1000);
    for(char* c = static_cast<char*>(pvoid); pvoid < &pvoid + 1000; ++c)
    {
        *c = 0x00;
    }
    func(pvoid, 1000);
    char ch = static_cast<char*>(pvoid)[0];
    std::cout << ch << std::endl; // 'A'
    operator delete(p);
}
```

## <a name="pointers-to-functions"></a><a name="pointers_to_functions"></a>İşlevlere işaretçiler

C stili programlamada, işlev işaretçileri birincil olarak işlevleri diğer işlevlere geçirmek için kullanılır. Bu senaryoda, çağıran bir işlevin davranışını değiştirmeden özelleştirebilir. Modern C++bir deyişle, [lambda ifadeleri](lambda-expressions-in-cpp.md) daha fazla güvenlik ve diğer avantajlar ile aynı özelliği sağlar.

Bir işlev işaretçisi bildirimi, işaret eden işlevin sahip olması gereken imzayı belirtir:

```cpp
// Declare pointer to any function that...

// ...accepts a string and returns a string
string (*g)(string a);

// has no return value and no parameters
void (*x)();

// ...returns an int and takes three parameters
// of the specified types
int (*i)(int i, string s, double d);
```

Aşağıdaki örnek, bir `std::string` kabul eden ve bir `std::string`döndüren işlev olarak bir parametre olarak alan bir işlev `combine` gösterir. `combine` geçirilen işleve bağlı olarak, bir dize önüne veya sonuna bir dize eklenir.

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
[yöneltme işleci: *](indirection-operator-star.md)<br/>
[Address-of İşleci: &](address-of-operator-amp.md)</br>
[Uygulamasına geri hoş geldinizC++](welcome-back-to-cpp-modern-cpp.md)
