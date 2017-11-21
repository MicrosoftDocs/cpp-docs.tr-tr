---
title: "Windows mağazası uygulamalarında C++ AMP kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 85577298-2c28-4209-9470-eb21048615db
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 71e912d5043c1b908d875dca50af12e38fd05f64
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-c-amp-in-windows-store-apps"></a>Windows Mağazası Uygulamalarında C++ AMP Kullanma
C++ AMP (C++ hızlandırılmış yoğun paralellik) kullanabileceğiniz, [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] (grafik işlem birimi) GPU veya diğer hesaplama Hızlandırıcıları hesaplamalar için uygulama. Ancak, C++ AMP API'lerini doğrudan Windows çalışma zamanı türleri ile çalışmak için sağlamaz ve Windows çalışma zamanı C++ AMP için sarmalayıcı sağlamaz. Windows çalışma zamanı türleri kodunuzda kullandığınızda — oluşturduğunuz kendiniz de dahil olmak üzere — bunları C++ AMP ile uyumlu türlerine dönüştürmeniz gerekir.  
  
## <a name="performance-considerations"></a>Performans değerlendirmeleri  
 Kullanıyorsanız, [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]) oluşturmak için [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamasını öneririz düz eski veri (POD) türleri bitişik depolama ile birlikte kullanmak — Örneğin, `std::vector` veya C tarzı dizileri — C++ AMP ile kullanılacak veri. Bu, hiçbir hazırlama oluşmasına olduğundan POD olmayan türleri veya Windows RT kapsayıcıları kullanarak daha yüksek performans elde yardımcı olabilir.  
  
 Bu şekilde, depolanan verilere erişmek için bir C++ AMP Çekirdeği'nde yalnızca kaydırma `std::vector` veya depolama dizisi bir `concurrency::array_view` ve dizi görünümünde kullanmak bir `concurrency::parallel_for_each` döngü:  
  
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
 Windows çalışma zamanı API'leri ile çalışırken, bir Windows çalışma zamanı kapsayıcısında gibi depolanan veriler üzerinde C++ AMP kullanmak isteyebileceği bir `Platform::Array<T>^` veya sınıf ya da kullanarak bildirilen yapının gibi karmaşık veri türlerini `ref` anahtar sözcüğü veya `value`</C4>anahtarsözcüğü. Bu durumlarda, C++ AMP verileri kullanılabilir duruma getirmek için bazı ek çalışmalar yapmanız gerekir.  
  
### <a name="platformarrayt-where-t-is-a-pod-type"></a>Platform::Array\<T > ^, burada T POD türü.  
 Ne zaman karşılaştığınız bir `Platform::Array<T>^` ve T POD türü, temel alınan depolama alanı yalnızca kullanarak erişebilirsiniz `get` üye fonksiyonu:  
  
```cpp  
Platform::Array<float>^ arr; // Assume that this was returned by a Windows Runtime API  
concurrency::array_view<float, 1> av(arr->Length, &arr->get(0));
```  
  
 T POD türü değilse, açıklanan teknikleri aşağıdaki bölümdeki verileri C++ AMP ile kullanmak için kullanın.  
  
### <a name="windows-runtime-types-ref-classes-and-value-classes"></a>Windows Çalışma Zamanı türleri: ref sınıfları ve değer sınıfları  
 C++ AMP karmaşık veri türlerini desteklemez. Bu POD olmayan türleri ve kullanarak bildirilen türleri içerir `ref` anahtar sözcüğü veya `value` anahtar sözcüğü. Desteklenmeyen bir tür kullanılıyorsa bir `restrict(amp)` bağlamı, derleme zamanı hatası oluşturulur.  
  
 Desteklenmeyen bir tür karşılaştığınızda, kendi veri ilginç bölümleri kopyalayabilirsiniz bir `concurrency::array` nesnesi. Verileri kullanmak C++ AMP için kullanıma ek olarak, bu el ile kopyalama yaklaşım ayrıca veri yere göre en üst düzeye çıkarma tarafından ve Hızlandırıcı kopyalanan kullanılmayacak verileri değil sağlayarak performansı artırabilir. Kullanarak daha fazla performansını iyileştirebilir bir *dizi hazırlama*, özel bir tür olduğu `concurrency::array` dizi ve diğer diziler arasındaki sık aktarım için üzerinde hale getirilmiştir AMP çalışma zamanı bir ipucu sağlar Belirtilen Hızlandırıcı.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ kullanarak ilk Windows mağazası uygulamanızı oluşturma](http://go.microsoft.com/fwlink/p/linkid=249073)   
 [C++'ta Windows çalışma zamanı bileşenleri oluşturma](http://go.microsoft.com/fwlink/p/linkid=249076)



