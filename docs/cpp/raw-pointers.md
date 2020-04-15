---
title: Ham işaretçiler (C++)
description: C++'da ham işaretçiler nasıl kullanılır?
ms.date: 11/19/2019
helpviewer_keywords:
- pointers [C++]
ms.openlocfilehash: 919447fcab123ce6b838391d3cc295fb8a8fe95e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374673"
---
# <a name="raw-pointers-c"></a>Ham işaretçiler (C++)

İşaretçi, bellekte bir nesnenin adresini depolayan ve bu nesneye erişmek için kullanılan bir değişken türüdür. *Ham işaretçi,* kullanım ömrü akıllı işaretçi gibi kapsülleme nesnesi tarafından denetlenmeyen bir [işaretçidir.](smart-pointers-modern-cpp.md) Ham işaretçiye işaretçi olmayan başka bir değişkenin adresi atanabilir veya [nullptr](nullptr.md)değeri atanabilir. Değer atanmamış bir işaretçi rasgele veri içerir.

Bir işaretçi, işaret ettiği nesnenin değerini almak için de *başvurudan* ayrılabilir. *Üye erişim işleci,* bir nesnenin üyelerine erişim sağlar.

```cpp
    int* p = nullptr; // declare pointer and initialize it
                      // so that it doesn't store a random address
    int i = 5;
    p = &i; // assign pointer to address of object
    int j = *p; // dereference p to retrieve the value at its address

```

Bir işaretçi, yazılan bir nesneyi işaret edebilir veya **geçersiz kılınabilir.** Bir program [bellekteki yığına](https://wikipedia.org/wiki/Heap) yeni bir nesne ayırdığında, işaretçi biçiminde o nesnenin adresini alır. Bu tür *işaretçilere sahip olmak*denir; sahip olunan bir işaretçi (veya bir kopyası) artık gerekli olmadığında yığın ayrılan nesneyi açıkça silmek için kullanılmalıdır. Bellek lerin silinmemesi *bellek sızıntısına* neden oluyor ve bu bellek konumunu makinedeki başka bir program için kullanılamaz hale getirir. Daha fazla bilgi için [yeni ve silme işleçleri](new-and-delete-operators.md)görün.

```cpp

    MyClass* mc = new MyClass(); // allocate object on the heap
    mc->print(); // access class member
    delete mc; // delete object (please don't forget!)
```

Bir işaretçi **(const**olarak bildirilmemişse) bellekte yeni bir konuma işaret etmek için artımlı veya decremented olabilir. Bu *işaretçi aritmetik* denir ve c stili programlama da diziler veya diğer veri yapıları öğeleri üzerinde tekrarlamak için kullanılır. Bir **const** işaretçisi farklı bir bellek konumuna işaret etmek için yapılamaz ve bu anlamda bir [başvuruya](references-cpp.md)çok benzer. Daha fazla bilgi için [const ve uçucu işaretçilere](const-and-volatile-pointers.md)bakın.

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

64 bit işletim sistemlerinde, bir işaretçinin boyutu 64 bitdir; bir sistemin işaretçi boyutu ne kadar adreslenebilir belleğe sahip olabileceğini belirler. Bir işaretçinin tüm kopyaları aynı bellek konumuna işaret eder. İşaretçiler (referanslarla birlikte) c++'da daha büyük nesneleri işlevlere ve işlevlerden geçirmek için yaygın olarak kullanılır, çünkü bir nesnenin 64 bit lik adresini kopyalamak tüm nesneyi kopyalamaktan çok daha verimlidir. Bir işlev tanımlarken, işlevin nesneyi değiştirmesini istemiyorsanız işaretçi parametrelerini **const** olarak belirtin. Genel olarak, **const** başvurular nesnenin değeri muhtemelen **nullptr**olabilir sürece işlevlere nesneleri geçmek için tercih edilen yoludur.

[İşlevlere işaretçiler](#pointers_to_functions) işlevlerin diğer işlevlere geçirilmesini sağlar ve C stili programlamada "geri arama" için kullanılır. Modern C++, bu amaçla [lambda ifadelerini](lambda-expressions-in-cpp.md) kullanır.

## <a name="initialization-and-member-access"></a>Başlatma ve üye erişimi

Aşağıdaki örnek, ham işaretçiyi nasıl bildireceğiniz ve yığında ayrılmış bir nesneyle nasıl başlağlaştırılanın ve sonra nasıl kullanılacağını gösterir. Ayrıca ham işaretçiler ile ilgili tehlikelerin birkaçgösterir. (Unutmayın, bu C tarzı programlama değil, modern C++!)

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

## <a name="pointer-arithmetic-and-arrays"></a>İşaretçi aritmetik ve diziler

İşaretçiler ve diziler yakından ilişkilidir. Bir dizi bir işleve göre geçirildiğinde, ilk öğeye işaretçi olarak geçirilir. Aşağıdaki örnek, işaretçilerin ve dizilerin aşağıdaki önemli özelliklerini gösterir:

- `sizeof` işleci, bir dizinin baytlarının toplam boyutunu döndürür
- eleman sayısını belirlemek için, toplam baytları bir öğenin boyutuna bölmek
- bir dizi bir işleve geçirildiğinde, işaretçi *türüne*
- bir `sizeof` işaretçiye uygulandığında işleç işaretçi boyutunu, x86'da 4 bayt veya x64'te 8 bayt döndürür

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

Bazı aritmetik işlemler, yeni bir bellek konumuna işaret etmelerini sağlamak için const olmayan işaretçiler üzerinde gerçekleştirilebilir. Bir işaretçi, **++**, **+=** **-=** ve işleçler kullanılarak artımlı ve **--** kararnameye edilebilir. Bu teknik diziler halinde kullanılabilir ve özellikle yazılmamış veri arabelleklerinde yararlıdır. Bir **char** (1 bayt) boyutuna göre bir **boşluk\* ** artışlar. Bir yazılan işaretçi, işaret ettiği türün boyutuna göre artışlar.

Aşağıdaki örnek, işaretçi aritmetik Windows'da bir bitmap tek tek piksel erişmek için nasıl kullanılabileceğini gösterir. **Yeni** ve **silme**ve dereference işlecinin kullanımına dikkat edin.

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

## <a name="void-pointers"></a>void* işaretçileri

**Geçersiz kılınacak** bir işaretçi yalnızca ham bir bellek konumuna işaret eder. Bazen, örneğin C++ kodu ve C işlevleri arasında geçerken **geçersiz\* ** işaretçiler kullanmak gerekir.

Bir yazılı işaretçi geçersiz bir işaretçiye atıldığında, bellek konumunun içeriği değiştirilmez, ancak tür bilgileri kaybolur, böylece artış veya decrement işlemleri gerçekleştiremezsiniz. Bir bellek konumu, örneğin, MyClass*'tan geçersiz kılmaya* ve tekrar MyClass*'a döküm lenebilir. Bu tür işlemler doğal olarak hataya açıktır ve hatalardan kaçınmak için büyük özen gerektirir. Modern C++ kesinlikle gerekli olmadıkça geçersiz işaretçilerin kullanılmasını engeller.

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
    char* pchar = static_cast<char*>(pvoid);
    for(char* c = pchar; c < pchar + 1000; ++c)
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

C stili programlamada, işlev işaretçileri öncelikle işlevleri diğer işlevlere geçirmek için kullanılır. Bu senaryoda, arayan bir işlevin davranışını değiştirmeden özelleştirebilir. Modern C++'da [lambda ifadeleri](lambda-expressions-in-cpp.md) daha fazla tür güvenliği ve diğer avantajlarla aynı yeteneği sağlar.

İşlev işaretçisi bildirimi, işaretli işlevin sahip olması gereken imzayı belirtir:

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

Aşağıdaki örnekte, `combine` parametre olarak a `std::string` kabul eden ve bir `std::string`. döndüren herhangi bir işlevi alan bir işlev gösterilmektedir. Geçirilen `combine` işleve bağlı olarak ya prepend veya bir dize ekleyecek.

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
[Indirection Operatör: *](indirection-operator-star.md)<br/>
[Address-of İşleci: &](address-of-operator-amp.md)</br>
[C++'a tekrar hoş geldiniz](welcome-back-to-cpp-modern-cpp.md)
