---
title: C++ öznitelikleri
ms.date: 06/01/2018
ms.assetid: 748340d9-8abf-4940-b0a0-91b6156a3ff8
ms.openlocfilehash: a4d24324165f3cce60d259adf6e3d21638296cf8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471831"
---
# <a name="attributes-in-c"></a>C++ öznitelikleri

C++ standardı bir öznitelik kümesini tanımlar ve ayrıca kendi öznitelikleri (içinde bir satıcıya özgü ad alanı) tanımlamak derleyici satıcıları sağlar, ancak derleyicileri standartlarındaki öznitelikleri tanımak için gereklidir.

Bazı durumlarda standart öznitelikleri derleyici özgü declspec parametrelerle çakışıyor. Visual c++'ta kullanabileceğiniz `[[deprecated]]` kullanmak yerine özniteliği `declspec(deprecated)` ve öznitelik herhangi uyumlu derleyici tarafından tanınır. Tüm diğer declspec parametreleri için dllimport ve dllexport gibi olarak henüz özniteliği eşdeğeri yoktur declspec sözdizimini kullanmaya devam etmelisiniz. Öznitelikler tür sistemine etkilemez ve bir program anlamını değişmiyor. Derleyiciler, bunlar tanımıyoruz öznitelik değerleri yok sayın.

**Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): bir öznitelik listesi kapsamında tüm adlar için ad alanı tek bir belirtebilirsiniz **kullanarak** introducer:

```cpp
void g() {
    [[using rpr: kernel, target(cpu,gpu)]] // equivalent to [[ rpr::kernel, rpr::target(cpu,gpu) ]]
    do task();
}
```

## <a name="c-standard-attributes"></a>C++ Standart öznitelikleri

C ++ 11'de, öznitelikler (ancak bunlarla sınırlı olmamak sınıfları, İşlevler, değişkenler ve blokları dahil) C++ yapıları satıcıya özgü olmayabilir veya ek bilgilerle açıklama eklemek için standartlaştırılmış bir yol sağlar. Derleyici, bilgi iletilerini oluşturmak veya öznitelikli kodunu derlerken özel mantığı uygulamak için bu bilgileri kullanabilirsiniz. Derleyici, yani bu söz dizimini kullanarak kendi özel öznitelikler tanımlanamaz tanımazsa, herhangi bir özniteliği yok sayar. Öznitelikleri çift köşeli ayraç içine alınır:

```cpp
[[deprecated]]
void Foo(int);
```

Öznitelikleri temsil eden satıcıya özgü uzantılar #pragma yönergeleri __declspec() (Visual C++) gibi standart bir alternatif veya &#95; &#95;özniteliği&#95; &#95; (GNU). Ancak, yine de satıcıya özel yapılar birçok amaç için kullanmanız gerekecektir. Standart şu anda uyumlu derleyici tanımalıdır aşağıdaki öznitelikleri belirtir:

- `[[noreturn]]` Bir işlev hiçbir zaman döndürür belirtir. diğer bir deyişle, her zaman bir özel durum oluşturur. Derleyici, derleme kuralları ayarlayabilirsiniz `[[noreturn]]` varlıklar.

- `[[carries_dependency]]` İşlevi iş parçacığı eşitleme göre sıralama veri bağımlılığı yayar belirtir. Öznitelik, geçilen bağımsız değişken işlev gövdesine bağımlılık izleme belirtmek için bir veya daha fazla parametrelere uygulanabilir. Özniteliği işlevin dönüş değeri işlevin dışında bir bağımlılık gerçekleştirecek belirtmeniz kendisi için uygulanabilir. Derleyici, daha verimli kod oluşturmak için bu bilgileri kullanabilirsiniz.

- `[[deprecated]]` **Visual Studio 2015 ve sonraki sürümler:** bir işlev kullanılmak üzere tasarlanmamıştır belirtir ve bir kitaplık arabirimi sürümleri gelecek mevcut olmayabilir. Derleyici bir işlevi çağırmak istemci kodu girişiminde bulunduğunda bir bilgi iletisidir oluşturmak için bunu kullanabilirsiniz. Bir sınıf, typedef adı, bir değişkenin, statik olmayan veri üyesi, bir işlev, bir ad alanı, bir numaralandırma, bir numaralandırıcı veya şablon uzmanlığı bildirimine uygulanabilir.

- `[[fallthrough]]` **Visual Studio 2017 ve üzeri:** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)) `[[fallthrough]]` özniteliği bağlamında kullanılabilir [geçiş](switch-statement-cpp.md) derleyici (veya herkesin okuma ipucu olarak deyimleri kodu), fallthrough davranıştır. Bu öznitelik hiçbir etkisi derleyici davranışı Bu nedenle Visual C++ derleyicisi fallthrough davranışı, şu anda uyarmaz.

- `[[nodiscard]]` **Visual Studio 2017 sürüm 15.3 ve üzeri:** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)) bir işlevin dönüş değerini atılmak üzere tasarlanmamıştır belirtir. Bu örnekte gösterildiği gibi C4834 uyarı oluşturur:

   ```cpp
   [[nodiscard]]
   int foo(int i) { return i * i; }

   int main()
   {
       foo(42); //warning C4834: discarding return value of function with 'nodiscard' attribute
       return 0;
   }
   ```

- `[[maybe_unused]]` **Visual Studio 2017 sürüm 15.3 ve üzeri:** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)) bir değişken, işlevi, sınıf, typedef, statik olmayan veri üyesi, enum veya şablon uzmanlığı amaçlanan kullanılabileceğini belirtir. Bir varlık işaretlendiğinde derleyici uyarmaz `[[maybe_unused]]` kullanılmaz. Özniteliği bildirilmiş bir varlık daha sonra özniteliğine sahip ve yeniden tanımlanıyor. Varlık olarak işaretlenmiş ilk bildiriminden analiz sonra ve çeviri geçerli çeviri biriminin geri kalanında işaretlenmiş olarak kabul edilir.

## <a name="microsoft-specific-attributes"></a>Microsoft'a özgü öznitelikleri

- `[[gsl::suppress(rules)]]` Bu Microsoft'a özgü öznitelik zorunlu kareler gelen uyarıları gizleme için kullanılır [yönergeleri destek kitaplığı (GSL)](https://github.com/Microsoft/GSL) kod kuralları. Örneğin, bu kod parçacığı göz önünde bulundurun:

    ```cpp
    void main()
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

   Örneğin, bu uyarıları oluşturur:

   - 26494 (tür kural 5: bir nesneyi her zaman başlatın.)

   - 26485 (sınırları kural 3: diziden işaretçiye bozunma gerçekleştirmeyin.)

   - 26481 (sınırları kural 1: işaretçi aritmetiği kullanmayın. Yayılma kullanın.)

   Bu kod yüklenmeli ve etkinleştirilmelidir CppCoreCheck kod analizi aracı ile derleme yaparken, ilk iki uyarıları kov. Ancak öznitelik nedeniyle üçüncü uyarı etkinleşmez. [[Gsl::suppress(bounds)]] yazarak bir özel kural numarası dahil olmak üzere tüm sınırların profil gösterilmemesini sağlayabilirsiniz. C++ temel yönergeleri, daha iyi ve daha güvenli kod yazmanıza yardımcı olmak için tasarlanmıştır. Bastır öznitelik değil istediğiniz zaman uyarılarını kapatmak kolaylaştırır.