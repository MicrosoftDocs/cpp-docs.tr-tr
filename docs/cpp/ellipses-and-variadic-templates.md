---
title: "Üç nokta ve Variadic şablonları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: f20967d9-c967-4fd2-b902-2bb1d5ed87e3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b6d3d0fa1dc4e2e4d817280fa83b26c56732cb2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ellipses-and-variadic-templates"></a>Üç Nokta ve Variadic Şablonları
Bu makalede üç nokta kullanmayı gösterir (`...`) ile C++ variadic şablonları. Üç nokta C ve C++ birçok kullanımı oluşturdu. Bu işlevler için değişken bağımsız değişken listeleri içerir. `printf()` C çalışma zamanı kitaplığı işlevinden en iyi bilinen örnekler biridir.  
  
 A *variadic şablonu* rastgele sayıda bağımsız değişken destekleyen sınıfı veya işlevi bir şablondur. Sınıf şablonları hem işlev şablonları uygulamak ve böylece çok çeşitli tür kullanımı uyumlu ve önemsiz olmayan işlevsellik ve esneklik sağlamak için bu düzenek C++ Kitaplık geliştiricileri için özellikle yararlıdır.  
  
## <a name="syntax"></a>Sözdizimi  
 Üç nokta iki yolla variadic şablonları tarafından kullanılır. Parametre adı soluna onu güveninin bir *parametresi paketi*, ve sağa parametre adının parametre paketleri ayrı adlarına genişletir.  
  
 Temel bir örneği burada verilmiştir *variadic Şablon sınıfı* tanımı sözdizimi:  
  
```cpp  
template<typename... Arguments> class classname;  
```  
  
 Parametre paketleri ve genişletmeleri için boşluk Bu örneklerde gösterildiği gibi tercihinize bağlı üç nokta çevresinde ekleyebilirsiniz:  
  
```cpp  
template<typename ...Arguments> class classname;  
```  
  
 Veya bu:  
  
```cpp  
template<typename ... Arguments> class classname;  
```  
  
 Bu makalede ilk örnekte gösterilen kuralı kullandığından emin olun (üç nokta bağlı `typename`).  
  
 Yukarıdaki örneklerde, `Arguments` bir parametre paketidir. Sınıf `classname` değişken sayıda bağımsız değişken, aşağıdaki örneklerde olduğu gibi kabul edebilir:  
  
```cpp  
template<typename... Arguments> class vtclass;  
  
vtclass< > vtinstance1;  
vtclass<int> vtinstance2;  
vtclass<float, bool> vtinstance3;  
vtclass<long, std::vector<int>, std::string> vtinstance4;  
  
```  
  
 Variadic şablon sınıf tanımını kullanarak, ayrıca en az bir parametre gerekebilir:  
  
```cpp  
template <typename First, typename... Rest> class classname;  
  
```  
  
 Temel bir örneği burada verilmiştir *variadic şablon işlevi* sözdizimi:  
  
```cpp  
template <typename... Arguments> returntype functionname(Arguments... args);  
```  
  
 `Arguments` Sonraki bölümde gösterildiği gibi parametre paketi kullanmak için ardından Genişletilmiş **variadic şablonları anlama**.  
  
 Diğer tür variadic şablon işlevi sözdizimi olası —, ancak bunlarla sınırlı olmamak, bu örnekler de dahil olmak üzere:  
  
```cpp  
template <typename... Arguments> returntype functionname(Arguments&... args);   
template <typename... Arguments> returntype functionname(Arguments&&... args);  
template <typename... Arguments> returntype functionname(Arguments*... args);  
```  
  
 Tanımlayıcıları ister `const` de izin verilir:  
  
```cpp  
template <typename... Arguments> returntype functionname(const Arguments&... args);  
  
```  
  
 Olarak variadic şablon sınıf tanımları ile en az bir parametre gerekli işlevleri yapabilirsiniz:  
  
```cpp  
template <typename First, typename... Rest> returntype functionname(const First& first, const Rest&... args);  
  
```  
  
 Variadic şablonları kullanın `sizeof...()` işleci (eski ilgisiz `sizeof()` işleci):  
  
```cpp  
template<typename... Arguments>  
void tfunc(const Arguments&... args)  
{  
    constexpr auto numargs{ sizeof...(Arguments) };  
  
    X xobj[numargs]; // array of some previously defined type X  
  
    helper_func(xobj, args...);  
}  
  
```  
  
## <a name="more-about-ellipsis-placement"></a>Üç nokta yerleri hakkında daha fazla bilgi  
 Bu makalede parametre paketleri ve genişletmeleri olarak tanımlayan üç nokta yerleştirme daha önce açıklanan "isteğe bağlı olarak parametre adı solunda bir parametre paketi güveninin ve sağa parametre adının parametre paketleri ayrı adlarına genişletir". Bu teknik olarak doğru ancak kod çevirisi kafa karışıklığına neden olabilir. Göz önünde bulundurun:  
  
-   Bir şablon parametresi-listesinde (`template <parameter-list>`), `typename...` bir şablon parametresi paketi sunar.  
  
-   Bir parametre-bildirimi-yan tümcesinde (`func(parameter-list)`), bir işlev parametresi paketi "üst düzey" üç nokta tanıtır ve üç nokta konumlandırma önemlidir:  
  
    ```cpp  
    // v1 is NOT a function parameter pack:  
    template <typename... Types> void func1(std::vector<Types...> v1);   
  
    // v2 IS a function parameter pack:  
    template <typename... Types> void func2(std::vector<Types>... v2);   
    ```  
  
-   Üç nokta hemen sonra bir parametre adı görünür olduğunda, bir parametre paketi genişletme sahip.  
  
## <a name="example"></a>Örnek  
 Variadic şablon işlevi mekanizması göstermek için en iyi yolu bir yeniden yazma bazı işlevlerini kullanmak için olan `printf`:  
  
```cpp  
#include <iostream>  
  
using namespace std;  
  
void print() {  
    cout << endl;  
}  
  
template <typename T> void print(const T& t) {  
    cout << t << endl;  
}  
  
template <typename First, typename... Rest> void print(const First& first, const Rest&... rest) {  
    cout << first << ", ";  
    print(rest...); // recursive call using pack expansion syntax  
}  
  
int main()  
{  
    print(); // calls first overload, outputting only a newline  
    print(1); // calls second overload  
  
    // these call the third overload, the variadic template,   
    // which uses recursion as needed.  
    print(10, 20);  
    print(100, 200, 300);  
    print("first", 2, "third", 3.14159);  
}  
  
```  
  
## <a name="output"></a>Çıkış  
  
```  
  
1  
10, 20  
100, 200, 300  
first, 2, third, 3.14159  
```  
  
> [!NOTE]
>  Özyineleme bazı formunun variadic şablon işlevleri dahil birçok uygulamaları kullanır, ancak geleneksel özyinelemeyle biraz farklıdır.  Geleneksel özyineleme aynı imza kullanarak kendisini çağıran bir işlev içerir. (Bu aşırı yüklenmiş veya şablonlu olabilir, ancak her zaman aynı imza seçilir.) Variadic özyineleme variadic işlevi şablon çağırma farklı (neredeyse her zaman Azalan) sayıda bağımsız değişken kullanarak ve böylece farklı bir imza her zaman damgası içerir. Bir "temel çalışması" yine de gereklidir, ancak özyineleme yapısını farklıdır.  
  
