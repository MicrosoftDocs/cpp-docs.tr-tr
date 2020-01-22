---
title: İçindeki özniteliklerC++
ms.date: 05/06/2019
ms.assetid: 748340d9-8abf-4940-b0a0-91b6156a3ff8
ms.openlocfilehash: 5967974d419299778e4aadaa235ee21c62e16d34
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518302"
---
# <a name="attributes-in-c"></a>İçindeki özniteliklerC++

C++ Standart bir öznitelik kümesi tanımlar ve ayrıca derleyici satıcılarının kendi özniteliklerini (satıcıya özgü bir ad alanı içinde) tanımlamasına olanak tanır, ancak derleyicilerin yalnızca standart olarak tanımlanmış öznitelikleri tanıması gerekir.

Bazı durumlarda, standart öznitelikler derleyiciye özgü declspec parametreleriyle örtüşüyor. Görselde C++, `declspec(deprecated)` kullanmak yerine `[[deprecated]]` özniteliğini kullanabilirsiniz ve özniteliği uyumlu herhangi bir derleyici tarafından tanınacaktır. Dllimport ve dllexport gibi diğer tüm declspec parametreleri için, declspec sözdizimini kullanmaya devam etmeniz gereken hiçbir öznitelik eşdeğeri yoktur. Öznitelikler tür sistemini etkilemez ve bir programın anlamını değiştirmez. Derleyiciler tanımadığı öznitelik değerlerini yoksayar.

**Visual Studio 2017 sürüm 15,3 ve üzeri** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir): bir öznitelik listesi kapsamında, tek bir **using** tanıtıcı adına sahip tüm adlar için ad alanını belirtebilirsiniz:

```cpp
void g() {
    [[using rpr: kernel, target(cpu,gpu)]] // equivalent to [[ rpr::kernel, rpr::target(cpu,gpu) ]]
    do task();
}
```

## <a name="c-standard-attributes"></a>C++Standart öznitelikler

C++ 11 ' de öznitelikler, satıcıya özgü olabilecek veya olmayan C++ ek bilgilerle yapıları (sınıflar, işlevler, değişkenler ve bloklar dahil ancak bunlarla sınırlı olmamak üzere) açıklama eklemek için standartlaştırılmış bir yol sağlar. Derleyici, bu bilgileri bilgilendirici iletiler oluşturmak veya öznitelikli kodu derlerken özel mantık uygulamak için kullanabilir. Derleyici, tanımadığı tüm öznitelikleri yoksayar, yani bu söz dizimini kullanarak kendi özel öznitelerinizi tanımlayamazsınız. Öznitelikler çift köşeli ayraç içine alınır:

```cpp
[[deprecated]]
void Foo(int);
```

Öznitelikler, satıcıya özgü uzantılara yönelik #pragma yönergeleri, __declspec () C++(görsel) veya &#95; &#95;öznitelik&#95; &#95; (GNU) gibi standartlaştırılmış bir alternatifi temsil eder. Ancak, yine de satıcıya özgü yapıları, çoğu amaçla kullanmanız gerekecektir. Standart Şu anda uygun bir derleyicinin tanıması gereken aşağıdaki öznitelikleri belirtiyor:

- `[[noreturn]]` bir işlevin hiçbir şekilde döndüğünü belirtir; diğer bir deyişle, her zaman bir özel durum oluşturur. Derleyici, `[[noreturn]]` varlıkların derleme kurallarını ayarlayabilir.

- `[[carries_dependency]]`, işlevin iş parçacığı eşitlemesine göre veri bağımlılığı sıralamasını yaymayacağını belirtir. Özniteliği bir veya daha fazla parametreye uygulanabilir, bu da geçirilen bağımsız değişkenin işlev gövdesine bir bağımlılık taşıdığının belirtilmesi olabilir. Dönüş değerinin işlevin bir bağımlılığını taşıdığının belirtilmesi için özniteliği işlevin kendisini uygulanabilir. Derleyici bu bilgileri daha verimli kod oluşturmak için kullanabilir.

- `[[deprecated]]` **Visual Studio 2015 ve üzeri:** bir işlevin kullanılması amaçlanmadığını belirtir ve bir kitaplık arabiriminin gelecek sürümlerinde bulunmayabilir. Derleyici bunu, istemci kodu işlevi çağırmaya çalıştığında bir bilgi iletisi oluşturmak için kullanabilir. Bir sınıfın bildirimine, bir typedef adına, değişkene, statik olmayan veri üyesine, işleve, bir ad alanına, bir numaralandırma, bir Numaralandırıcı veya bir şablon özelleştirmesine uygulanabilir.

- `[[fallthrough]]` **Visual Studio 2017 ve üzeri:** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir) `[[fallthrough]]` özniteliği, bir derleyici için bir ipucu olarak ( [](switch-statement-cpp.md) veya kodu okuyan herhangi bir kişi), fallthrough davranışın amaçlandığı bir ipucu olarak kullanılabilir. Microsoft C++ derleyicisi Şu anda fallthrough davranışa göre uyarı vermiyor, bu nedenle bu özniteliğin hiçbir etkisi derleyici davranışı yoktur.

- `[[nodiscard]]` **Visual Studio 2017 sürüm 15,3 ve üzeri:** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir) bir işlevin dönüş değerinin atılmak üzere amaçlanmadığını belirtir. Aşağıdaki örnekte gösterildiği gibi, uyarı C4834 başlatır:

    ```cpp
    [[nodiscard]]
    int foo(int i) { return i * i; }

    int main()
    {
        foo(42); //warning C4834: discarding return value of function with 'nodiscard' attribute
        return 0;
    }
    ```

- `[[maybe_unused]]` **Visual Studio 2017 sürüm 15,3 ve üzeri:** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir) bir değişken, işlev, sınıf, typedef, statik olmayan veri üyesi, Enum veya şablon uzmanlığın kasıtlı olarak kullanılamayacağını belirtir. `[[maybe_unused]]` işaretli bir varlık kullanılmazsa derleyici uyarma. Özniteliği olmadan tanımlanmış bir varlık daha sonra özniteliğiyle yeniden bildirilemez ve bunun tersini yapabilir. Bir varlık, işaretlenmiş ilk bildirimi çözümlendikten sonra işaretlenmiş olarak değerlendirilir ve geçerli çeviri biriminin çevirisinin geri kalanı için işaretlenir.

## <a name="microsoft-specific-attributes"></a>Microsoft 'a özgü öznitelikler

- `[[gsl::suppress(rules)]]`, Microsoft 'a özgü bu öznitelik, koddaki [yönergeler destek kitaplığı (GSL)](https://github.com/Microsoft/GSL) kurallarını zorlayan dama uyarılarını gizleme için kullanılır. Örneğin, şu kod parçacığını göz önünde bulundurun:

    ```cpp
    int main()
    {
        int arr[10]; // GSL warning 26494 will be fired
        int* p = arr; // GSL warning 26485 will be fired
        [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1
        {
            int* q = p + 1; // GSL warning 26481 suppressed
            p = q--; // GSL warning 26481 suppressed
        }
    }
    ```

  Örnek şu uyarıları oluşturur:

  - 26494 (tür kuralı 5: her zaman bir nesne başlatın.)

  - 26485 (sınır kuralı 3: işaretçiden işaretçiye hiçbir dizi yok.)

  - 26481 (sınır kuralı 1: işaretçi aritmetiği kullanmayın. Bunun yerine span kullanın.)

  Bu kodu, CppCoreCheck Kod Analizi Aracı yüklü ve etkinleştirilmiş olarak derlerken ilk iki uyarı ateşlenir. Ancak, üçüncü uyarı öznitelik nedeniyle tetiklenmeyecektir. Belirli bir kural numarası dahil etmeden [[gsl:: bastır (sınır)]] yazarak tüm sınır profillerinin görüntülenmesini sağlayabilirsiniz. C++ Temel yönergeler daha iyi ve daha güvenli bir kod yazmanıza yardımcı olacak şekilde tasarlanmıştır. Gizleme özniteliği, uyarı istenmediğinde uyarıları kapatmayı kolaylaştırır.
  