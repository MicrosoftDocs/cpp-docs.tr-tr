---
title: Kaynak kodu organizasyonu (C++ şablonları)
ms.date: 04/22/2019
ms.assetid: 50569c5d-0219-4966-9bcf-a8689074ad1d
ms.openlocfilehash: ecd682056f27200ae31c27295c1aabaf72c74a18
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87186119"
---
# <a name="source-code-organization-c-templates"></a>Kaynak kodu organizasyonu (C++ şablonları)

Bir sınıf şablonu tanımlarken, kaynak kodu üye tanımlarının ihtiyaç duyduğunda derleyicinin görebilmesi için bu şekilde düzenlemeniz gerekir. *Ekleme modelini* veya *açık örnek oluşturma* modelini kullanma seçeneğiniz vardır. Ekleme modelinde, bir şablon kullanan her dosyaya üye tanımlarını dahil edersiniz. Bu yaklaşım en basit olanıdır ve şablonlarınızda somut türlerin kullanılabileceği koşullarda maksimum esneklik sağlar. Bunun olumsuz yanı, derleme sürelerini arttırabilirler. Bir proje ve/veya dahil edilen dosyaların kendisi büyükse etki önemli olabilir. Açık örnek oluşturma yaklaşımıyla, şablon belirli türler için somut sınıflar veya sınıf üyeleri başlatır.  Bu yaklaşım, derleme sürelerini hızlandırmaya devam edebilir, ancak kullanımı yalnızca şablon uygulayıcının etkin olduğu sınıflarla sınırlandırır. Genel olarak, derleme süreleri bir sorun haline gelmediği takdirde ekleme modelini kullanmanızı öneririz.

## <a name="background"></a>Arka Plan

Şablonlar, derleyicinin bir şablon ya da üyesi için nesne kodu oluşturmadığını anlamda sıradan sınıflar gibi değildir. Şablon somut türlerle örneklenene kadar oluşturulacak bir şey yok. Derleyici gibi bir şablon örneği ile karşılaştığında `MyClass<int> mc;` ve bu imzaya sahip hiçbir sınıf henüz mevcut değilse, yeni bir sınıf oluşturur. Ayrıca, kullanılan herhangi bir üye işlevi için kod oluşturmaya çalışır. Bu tanımlar doğrudan veya dolaylı olarak, Derlenmekte olan. cpp dosyasında #included olmayan bir dosyada yer alıyorsa, derleyici bunları göremez.  Derleyicinin görünüm noktasından bu bir hata değildir, çünkü işlevler başka bir çeviri biriminde tanımlanabileceğinden, bu durumda bağlayıcı onları bulacaktır.  Bağlayıcı bu kodu bulamazsa, *çözümlenmemiş bir dış* hata oluşturur.

## <a name="the-inclusion-model"></a>İçerme modeli

Şablon tanımlarının bir çeviri birimi boyunca görünür hale getirmenin en basit ve en yaygın yolu, tanımları başlık dosyasına yerleştirmesidir.  Şablonu kullanan tüm. cpp dosyalarının üst bilgiyi #include olması yeterlidir. Bu, standart kitaplıkta kullanılan yaklaşımdır.

```cpp
#ifndef MYARRAY
#define MYARRAY
#include <iostream>

template<typename T, size_t N>
class MyArray
{
    T arr[N];
public:
    // Full definitions:
    MyArray(){}
    void Print()
    {
        for (const auto v : arr)
        {
            std::cout << v << " , ";
        }
    }

    T& operator[](int i)
   {
       return arr[i];
   }
};
#endif
```

Bu yaklaşımda derleyicinin tam şablon tanımına erişimi vardır ve herhangi bir tür için isteğe bağlı olarak şablonları örnekleyebilirsiniz. Basit ve daha kolay bir şekilde korunur. Ancak, ekleme modelinin, derleme süreleriyle bir maliyeti vardır. Bu maliyet, özellikle de şablon üstbilgisinin başka üstbilgiler #includes, büyük programlar için önemli olabilir. *`.cpp`* Üst bilgiyi #includes her dosya, işlev şablonlarının ve tüm tanımlarının kendi kopyasını alır. Bağlayıcı genellikle, bir işlev için birden çok tanımla bitmeyecek şekilde sıralama yapar, ancak bu işi yapmak için zaman alır. Daha küçük programlarda, ek derleme süresi büyük olasılıkla önemli değildir.

## <a name="the-explicit-instantiation-model"></a>Açık örnek oluşturma modeli

Ekleme modeli projeniz için uygun değilse ve bir şablon örneği oluşturmak için kullanılacak tür kümesini ayrıntılı bir şekilde biliyorsanız, şablon kodunu bir *`.h`* ve *`.cpp`* dosyasına ayırabilirsiniz ve *`.cpp`* dosyada açıkça şablon örneğini oluşturabilirsiniz. Bu, derleyicinin Kullanıcı örneklemelerinden karşılaştığında göreceği nesne kodu oluşturulmasına neden olur.

Anahtar sözcük şablonunu ve ardından örneklemek istediğiniz varlığın imzasını kullanarak açık bir örnek oluşturma oluşturursunuz. Bu bir tür veya üye olabilir. Açıkça bir tür örneği oluşturursanız, tüm Üyeler oluşturulur.

```cpp
template MyArray<double, 5>;
```

```cpp
//MyArray.h
#ifndef MYARRAY
#define MYARRAY

template<typename T, size_t N>
class MyArray
{
    T arr[N];
public:
    MyArray();
    void Print();
    T& operator[](int i);
};
#endif

//MyArray.cpp
#include <iostream>
#include "MyArray.h"

using namespace std;

template<typename T, size_t N>
MyArray<T,N>::MyArray(){}

template<typename T, size_t N>
void MyArray<T,N>::Print()
{
    for (const auto v : arr)
    {
        cout << v << "'";
    }
    cout << endl;
}

template MyArray<double, 5>;template MyArray<string, 5>;
```

Önceki örnekte, açık örneklemeler. cpp dosyasının en altında bulunur. `MyArray`Yalnızca **`double`** veya türleri için kullanılabilir `String` .

> [!NOTE]
> C++ 11 ' de **`export`** anahtar sözcüğü şablon tanımları bağlamında kullanımdan kaldırılmıştır. Pratik koşullarda, çoğu derleyicilerin hiç desteklemediği için bu çok az etkiye sahiptir.
