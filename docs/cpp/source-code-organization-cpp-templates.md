---
title: Kaynak kodu kuruluşu (C++ Şablonları)
ms.date: 04/22/2019
ms.assetid: 50569c5d-0219-4966-9bcf-a8689074ad1d
ms.openlocfilehash: 1933758e47f2fcc0b63f0d16809591b932501854
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611396"
---
# <a name="source-code-organization-c-templates"></a>Kaynak kodu kuruluşu (C++ Şablonları)

Bir sınıf şablonunun tanımlarken, kaynak kodunu yeniden gerektiğinde üye tanımları için derleyici görünür olduğunu şekilde düzenlemeniz gerekir.   Kullanma seçeneğiniz *ekleme modeli* veya *açık örnek oluşturma* modeli. Ekleme modelinde, bir şablon kullanan her dosyasında üye tanımları içerir. Bu yaklaşım basit ve hangi somut türleri şablonunuzla birlikte kullanılabilir bakımından en üst düzeyde esneklik sağlar. Kendi dezavantajı, derleme sürelerini artırabilir ' dir. Etkisi önemli bir proje varsa olabilir ve/veya eklenen dosyalar yüksektir. Açık örnek oluşturma yaklaşımıyla somut sınıflar veya sınıf üyeleri için özel tür şablon örneği oluşturur.  Bu yaklaşım, derleme sürelerini hızlandırmanın, ancak kullanım, şablonu uygulayan önceden etkinleştirilmiş sınıfları için sınırlar. Genel olarak, derleme sürelerini bir sorun haline sürece dahil etme modeli kullanmanızı öneririz.

## <a name="background"></a>Arka Plan

Şablonlar, derleyici şablon veya diğer üyelerinin nesne kodu oluşturmaz anlamında sıradan sınıflar gibi değildir. Somut türleri ile şablon örneği oluşturulana dek oluşturulacak bir şey yok. Derleyici karşılaştığında bir şablon örneklemesinde gibi `MyClass<int> mc;` ve bu imzaya sahip hiçbir sınıf henüz var, yeni bir sınıf oluşturur. Kullanılan tüm üye işlevleri için kod oluşturmak üzere de çalışır. Bu tanımları olmayan bir dosyada olup olmadığını #, doğrudan veya dolaylı olarak derleniyor, .cpp dosyası içinde included derleyici bunları göremez.  İşlevler durumu bağlayıcı bulabilirsiniz bunları başka bir çeviri birimindeki tanımlanabileceği için derleyicinin açısından bakıldığında, bu mutlaka bir hata değildir.  Bağlayıcı bu kodu bulamazsa bilmemektedir bir **çözülmemiş dış** hata.

## <a name="the-inclusion-model"></a>Model ekleme

Şablon tanımlarında bir çeviri birimi içinde görünür hale getirmek için basit ve en yaygın yoludur tanımları üstbilgi dosyasının kendisinde yerleştirmek için.  Gereken yeterlidir şablonu kullanan herhangi bir .cpp dosyasını # include. Standart Kitaplığı'nda kullanılan yaklaşım budur.

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

Bu yaklaşımla, derleyici tam şablon tanımı erişebilir ve şablonları isteğe bağlı olarak herhangi bir tür örneği oluşturabilir. Bu basit ve korumak daha kolay olur. Ancak, ekleme model derleme sürelerini açısından maliyeti sahip.   Bu maliyet büyük programlarda, önemli özellikle şablon başlığı # diğer üst bilgilerini includes. Her .cpp dosyasının #includes üstbilgi işlev şablonları ve tüm tanımları kendine ait kopyasını alır. Bağlayıcı genel olarak şey, bir işlev için birden çok tanım ile bitmeyen, ancak bu işi yapabilmek için zaman alır olacak şekilde Sırala mümkün olacaktır. Ek derleme süresi önemli olduğunu büyük olasılıkla daha küçük programlarda.

## <a name="the-explicit-instantiation-model"></a>Açık örnek oluşturma modeli

Ekleme modeli projeniz için uygun değil ve bir şablon oluşturmak için kullanılan türleri kesin bir şekilde biliyorsanız, bir .h ve .cpp dosyası şablon kodunu ayrı sonra .cpp dosyasında açıkça şablonları örneği. Bu kullanıcı örneklemeleri karşılaştığında derleyici görürsünüz nesne kodu oluşturulmasına neden olur.

Bir açık örnek oluşturma, oluşturmak istediğiniz varlığı imzası tarafından izlenen anahtar sözcüğü şablonu kullanarak oluşturun. Bu, bir tür veya üye olabilir. Bir tür açıkça örneği, tüm üyeleri örneği oluşturulur.

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
    for(const auto v : arr)
    {
        cout << v << "'";
    }
    cout << endl;
}

template MyArray<double, 5>;template MyArray<string, 5>;
```

Önceki örnekte, açık örnek oluşturma işlemleri .cpp dosyasının sonunda ' dir. A `MyArray` yalnızca kullanılabilir **çift** veya `String` türleri.

> [!NOTE]
> C ++ 11'de **dışarı** anahtar sözcüğü, şablon tanımlarında bağlamında kullanım. Derleyicilerin çoğu hiçbir zaman desteklemediği için pratikte bunun çok az etkisi vardır.