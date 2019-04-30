---
title: UWP uygulamalarında C++ AMP kullanma
ms.date: 11/04/2016
ms.assetid: 85577298-2c28-4209-9470-eb21048615db
ms.openlocfilehash: 31fede0a2419e56d53cb16521b08067dac5facc6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405358"
---
# <a name="using-c-amp-in-uwp-apps"></a>UWP uygulamalarında C++ AMP kullanma

GPU (grafik işleme birimi) veya diğer bilgisayar hızlandırıcılarında üzerinde hesaplamalar gerçekleştirmek için evrensel Windows Platformu (UWP) uygulamanızda C++ AMP (C++ Accelerated Massive Parallelism) kullanabilirsiniz. Bununla birlikte, C++ AMP, doğrudan Windows çalışma zamanı türleriyle çalışmak için API'lar sağlamaz ve Windows çalışma zamanı C++ AMP için bir sarmalayıcı sağlamaz. Windows çalışma zamanı türlerini kullandığınızda, kodunuzda — oluşturduğunuz kendiniz de dahil olmak üzere — bunları C++ AMP ile uyumlu türlere dönüştürmeniz gerekir.

## <a name="performance-considerations"></a>Performans değerlendirmeleri

Visual C++ bileşen uzantıları C + kullanıyorsanız +/ CX, Evrensel Windows Platformu (UWP) uygulaması oluşturmak için düz eski veri (POD) türlerini bitişik depolamayla kullanmanızı öneririz — Örneğin, `std::vector` veya C stili diziler — olacak veriler için C++ AMP ile kullanılır. Bu, herhangi bir sıralama sahip POD harici türler veya Windows RT kapsayıcıları kullanarak daha fazla performans elde etmenize yardımcı olabilir.

Bir C++ AMP Çekirdekte bu şekilde, depolanan verilere yalnızca kaydırma `std::vector` veya dizi deposunu bir `concurrency::array_view` ve ardından dizi görünümünü bir `concurrency::parallel_for_each` döngü:

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

Windows çalışma zamanı API'lar ile çalışırken, aşağıdaki gibi bir Windows çalışma zamanı kapsayıcısında depolanan veriler üzerinde C++ AMP kullanmak isteyebilirsiniz bir `Platform::Array<T>^` veya yapılar kullanarak bildirilen sınıflar veya yapılar gibi karmaşık veri türlerinde **ref** anahtar sözcüğü veya **değer** anahtar sözcüğü. Bu durumlarda verilerin to C++ AMP tarafından kullanılabilir hale getirmek ek iş yapması gerekir.

### <a name="platformarrayt-where-t-is-a-pod-type"></a>Platform::Array\<T > ^, burada T bir POD türü.

Ne zaman karşılaştığınız bir `Platform::Array<T>^` ve T bir POD türü, yalnızca kullanarak temel depoya erişebilirsiniz `get` üye işlevi:

```cpp
Platform::Array<float>^ arr; // Assume that this was returned by a Windows Runtime API
concurrency::array_view<float, 1> av(arr->Length, &arr->get(0));
```

Açıklanan tekniği aşağıdaki bölümde T bir POD türü değilse, verileri C++ AMP ile kullanmak için kullanın.

### <a name="windows-runtime-types-ref-classes-and-value-classes"></a>Windows Çalışma Zamanı türleri: ref sınıfları ve değer sınıfları

C++ AMP karmaşık veri türlerini desteklemez. Bu POD harici türleri ve kullanılarak bildirilen tüm türleri içerir **ref** anahtar sözcüğü veya **değer** anahtar sözcüğü. Desteklenmeyen tür kullanılırsa bir `restrict(amp)` bağlam, bir derleme zamanı hatası oluşturulur.

Desteklenmeyen bir tür karşılaştığınızda verinin ilginç bölümlerini kopyalayıp bir `concurrency::array` nesne. Verileri C++ AMP'ı kullanmak için kullanılabilir hale getirmenin yanı sıra, bu el ile kopyalama yaklaşımı da yerel veri konumu en üst düzeye ve kullanılmayacak veri hızlandırıcıya sağlayarak performansı artırabilir. Kullanarak performansı artırabilirsiniz bir *yapıcı dizi*, özel olduğu `concurrency::array` dizisi ve diğer diziler arasında sık aktarım için üzerinde optimize edilmesini AMP çalışma zamanı bir ipucu sağlar Belirtilen Hızlandırıcı.

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

[C++ kullanarak ilk UWP uygulamanızı oluşturun](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)<br/>
[C++'ta Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
