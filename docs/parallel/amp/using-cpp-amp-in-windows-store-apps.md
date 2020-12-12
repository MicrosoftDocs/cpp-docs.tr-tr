---
description: 'Hakkında daha fazla bilgi edinin: UWP uygulamalarında C++ AMP kullanma'
title: UWP uygulamalarında C++ AMP kullanma
ms.date: 11/04/2016
ms.assetid: 85577298-2c28-4209-9470-eb21048615db
ms.openlocfilehash: 91c7b147ff89a1fe19ebe1b18e465533053542d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314483"
---
# <a name="using-c-amp-in-uwp-apps"></a>UWP uygulamalarında C++ AMP kullanma

GPU (grafik Işleme birimi) veya diğer hesaplama hızlandırıcıları üzerinde hesaplamalar gerçekleştirmek için Evrensel Windows Platformu (UWP) uygulamanızda C++ AMP (C++ Accelerated Massive Parallelism) kullanabilirsiniz. Ancak, C++ AMP doğrudan Windows Çalışma Zamanı türleriyle çalışmak için API 'Ler sağlamaz ve Windows Çalışma Zamanı C++ AMP için bir sarmalayıcı sağlamaz. Kodunuzda Windows Çalışma Zamanı türleri kullandığınızda — kendi oluşturduğunuz olanlar da dahil olmak üzere, bunları C++ AMP uyumlu türlere dönüştürmeniz gerekir.

## <a name="performance-considerations"></a>Performansla ilgili önemli noktalar

Evrensel Windows Platformu (UWP) uygulamanızı oluşturmak için Visual C++ bileşen uzantıları C++/CX kullanıyorsanız, C++ AMP ile birlikte kullanılacak veriler için, bitişik depolamayla (örneğin, `std::vector` veya C stili diziler gibi) düz eski veri (pod) türlerini kullanmanızı öneririz. Bu, herhangi bir sıralama gerçekleşmediğinden POD olmayan türler veya Windows RT kapsayıcıları kullanarak daha yüksek performans elde etmenize yardımcı olabilir.

C++ AMP çekirdekte, bu şekilde depolanan verilere erişmek için, `std::vector` veya dizi depolamayı bir `concurrency::array_view` döngüsünde sarın ve sonra dizi görünümünü bir döngüde kullanmanız gerekir `concurrency::parallel_for_each` :

```cpp
// simple vector addition example
std::vector<int> data0(1024, 1);
std::vector<int> data1(1024, 2);
std::vector<int> data_out(data0.size(), 0);

concurrency::array_view<int, 1> av0(data0.size(), data0);
concurrency::array_view<int, 1> av1(data1.size(), data1);
concurrency::array_view<int, 1> av2(data_out.size(), data2);

av2.discard_data();

concurrency::parallel_for_each(av0.extent, [=](concurrency::index<1> idx) restrict(amp)
    {
        av2[idx] = av0[idx] + av1[idx];
    });
```

## <a name="marshaling-windows-runtime-types"></a>Windows Çalışma Zamanı türlerini sıralama

Windows Çalışma Zamanı API 'Leriyle çalışırken, `Platform::Array<T>^` ya da **ref** anahtar sözcüğü veya **Value** anahtar sözcüğü kullanılarak tanımlanmış sınıflar veya yapılar gibi Windows Çalışma Zamanı kapsayıcıda depolanan veriler üzerinde C++ amp kullanmak isteyebilirsiniz. Bu durumlarda, verileri C++ AMP için kullanılabilir hale getirmek üzere bazı ek çalışmalar yapmanız gerekir.

### <a name="platformarrayt-where-t-is-a-pod-type"></a>Platform:: array \<T> ^, burada T BIR Pod türüdür

Bir `Platform::Array<T>^` ve T ile karşılaştığınızda, BIR Pod türüdür, yalnızca üye işlevini kullanarak kendi temel depolamasına erişebilirsiniz `get` :

```cpp
Platform::Array<float>^ arr; // Assume that this was returned by a Windows Runtime API
concurrency::array_view<float, 1> av(arr->Length, &arr->get(0));
```

T bir POD türü değilse, verileri C++ AMP kullanmak için aşağıdaki bölümde açıklanan tekniği kullanın.

### <a name="windows-runtime-types-ref-classes-and-value-classes"></a>Windows Çalışma Zamanı türleri: ref sınıfları ve değer sınıfları

C++ AMP karmaşık veri türlerini desteklemez. Bu, POD olmayan türler ve **ref** anahtar sözcüğü ya da **Value** anahtar sözcüğü kullanılarak tanımlanan türler içerir. Bağlam içinde desteklenmeyen bir tür kullanılırsa `restrict(amp)` , derleme zamanı hatası oluşturulur.

Desteklenmeyen bir türle karşılaştığınızda, verilerinin ilginç kısımlarını bir `concurrency::array` nesneye kopyalayabilirsiniz. Verilerin C++ AMP için kullanılabilir hale getirilmesi buna ek olarak, bu el ile kopyalama yaklaşımı, veri yerleştirmelerini en üst düzeye çıkararak performansı da iyileştirebilir ve kullanılmayacak verilerin hızlandırıcıya kopyalanmamasını sağlar. Bir *hazırlama dizisi* kullanarak performansı daha da artırabilirsiniz. Bu, bir, `concurrency::array` dizi, belirtilen hızlandırıcının aralarında ve diğer diziler arasında sık aktarım için en iyi duruma getirilmesi gereken amp çalışma zamanına yönelik bir ipucu sağlayan özel bir formdur.

```cpp
// pixel_color.h
ref class pixel_color sealed
{
public:
    pixel_color(Platform::String^ color_name, int red, int green, int blue)
    {
        name = color_name;
        r = red;
        g = green;
        b = blue;
    }

    property Platform::String^ name;
    property int r;
    property int g;
    property int b;
};

// Some other file

std::vector<pixel_color^> pixels (256);

for (pixel_color ^pixel : pixels)
{
    pixels.push_back(ref new pixel_color("blue", 0, 0, 255));
}

// Create the accelerators
auto cpuAccelerator = concurrency::accelerator(concurrency::accelerator::cpu_accelerator);
auto devAccelerator = concurrency::accelerator(concurrency::accelerator::default_accelerator);

// Create the staging arrays
concurrency::array<float, 1> red_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);
concurrency::array<float, 1>  blue_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);

// Extract data from the complex array of structs into staging arrays.
concurrency::parallel_for(0, 256, [&](int i)
    {
        red_vec[i] = pixels[i]->r;
        blue_vec[i] = pixels[i]->b;
    });

// Array views are still used to copy data to the accelerator
concurrency::array_view<float, 1> av_red(red_vec);
concurrency::array_view<float, 1> av_blue(blue_vec);

// Change all pixels from blue to red.
concurrency::parallel_for_each(av_red.extent, [=](index<1> idx) restrict(amp)
    {
        av_red[idx] = 255;
        av_blue[idx] = 0;
    });
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ kullanarak ilk UWP uygulamanızı oluşturma](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)<br/>
[C++ ' ta Windows Çalışma Zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
