---
title: C++ Standart öznitelikleri | Microsoft Docs
ms.custom: ''
ms.date: 03/28/2017
ms.topic: language-reference
ms.assetid: 748340d9-8abf-4940-b0a0-91b6156a3ff8
ms.openlocfilehash: 7bd7fd4e01fb210069f4dbae42a671e4dd9c64c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="attributes-in-c"></a>C++ öznitelikleri

C++ Standart öznitelikler kümesi tanımlar ve ayrıca kendi özniteliklerle (satıcıya özgü ad alanı) tanımlamak derleyici satıcılarının izin verir, ancak derleyicileri yalnızca standardında tanımlanan özniteliklere tanımak için gereklidir.

Bazı durumlarda standart öznitelikleri derleyici özgü declspec parametrelerle çakışıyor. Visual C++'da, kullandığınız `[[deprecated]]` kullanmak yerine özniteliği `declspec(deprecated)` ve öznitelik herhangi uyumluluğunu derleyici tarafından tanınır. Diğer tüm declspec parametreleri için dllimport ve dllexport gibi olmadığından olarak henüz hiçbir öznitelik eşdeğeri declspec sözdizimi kullanmaya devam etmeniz gerekir. Öznitelikler tür sistemi etkilemez ve bir program anlamını değiştirmeyin. Derleyicileri bunlar tanımadığınız öznitelik değerleri yok sayın.

**Visual Studio 2017 15.3 ve sonraki sürümleri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): bir öznitelik listesi kapsamında tüm adlar için ad alanı tek bir tıklatmayla belirtebilirsiniz `using` introducer:

```cpp
void g() {
    [[using rpr: kernel, target(cpu,gpu)]] // equivalent to [[ rpr::kernel, rpr::target(cpu,gpu) ]]
    do task();
}
```

## <a name="c-standard-attributes"></a>C++ Standart öznitelikleri

C ++ 11'de öznitelikleri olabilir veya satıcıya özgü olmayabilir ek bilgilerle C++ yapıları (ancak bunlarla sınırlı olmamak sınıfları, İşlevler, değişkenler ve blokları dahil) ek açıklama eklemek için standartlaştırılmış bir yol sağlar. Derleyici bilgilendirici iletileri oluşturmak veya atanmış kodu derlerken özel mantığını uygulamak için bu bilgileri kullanabilirsiniz. Derleyici bu söz dizimini kullanarak kendi özel öznitelikler tanımlayamazsınız yani tanımazsa, tüm öznitelikleri yoksayar. Öznitelikleri tarafından çift köşeli ayraç içine alınır:

```cpp
[[deprecated]]
void Foo(int);
```

Öznitelikleri temsil #pragma yönergeleri, __declspec() (Visual C++) gibi satıcıya özel uzantıları için standartlaştırılmış bir alternatif veya &#95; &#95;özniteliği&#95; &#95; (GNU). Ancak, yine satıcıya özgü yapıları çoğu amaç için kullanmanız gerekecektir. Standart şu anda uyumlu derleyici tanımalıdır aşağıdaki öznitelikler belirtir:

- `[[noreturn]]` Bir işlev hiçbir zaman döndürür belirtir; diğer bir deyişle her zaman bir özel durum oluşturur. Derleyici için derleme kurallarını ayarlayabilirsiniz `[[noreturn]]` varlıklar.

- `[[carries_dependency]]` İşlev iş parçacığı eşitleme göre sıralama veri bağımlılığı yayar belirtir. Öznitelik, geçilen bağımsız değişken bir bağımlılık işlev gövdesine taşır belirtmek üzere bir veya daha fazla parametreler için uygulanabilir. Öznitelik, işlevin dönüş değeri işlevi dışında bir bağımlılık gerçekleştirecek belirtmeniz kendisi için uygulanabilir. Derleyici daha verimli kodu oluşturmak için bu bilgileri kullanabilirsiniz.

- `[[deprecated]]` **Visual Studio 2015 ve sonraki sürümler:** bir işlev kullanılmak üzere tasarlanmamıştır belirtir ve bir kitaplık arabirimi sürümleri gelecekte mevcut olmayabilir. Derleyici bu işlevi çağırmak istemci kodu denediğinde, bir bilgilendirme iletisi oluşturmak için kullanabilirsiniz. Bir sınıf, typedef adı, bir değişkeni, statik olmayan veri üyesi, bir işlev, bir ad alanı, numaralandırma, bir numaralandırıcı veya şablon uzmanlık bildirimine uygulanabilir.  

- `[[fallthrough]]` **Visual Studio 2017 ve üzeri:** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)) `[[fallthrough]]` özniteliği bağlamında kullanılabilir [geçiş](switch-statement-cpp.md) derleyici (veya okuyan herkes ipucu olarak deyimleri kodu), fallthrough bir davranıştır. Bu öznitelik hiçbir etkisi derleyici davranışı nedenle Visual C++ Derleyici fallthrough davranışı üzerinde şu anda uyarmaz.

- `[[nodiscard]]` **Visual Studio 2017 15.3 ve sonraki sürümleri:** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)) bir işlevin dönüş değeri atılmak üzere tasarlanmamıştır belirtir. Bu örnekte gösterildiği gibi C4834, uyarı oluşturur:

   ```cpp
   [[nodiscard]]
   int foo(int i) { return i * i; }

   int main()
   {
       foo(42); //warning C4834: discarding return value of function with 'nodiscard' attribute
       return 0;
   }
   ```

- `[[maybe_unused]]` **Visual Studio 2017 15.3 ve sonraki sürümleri:** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)) bir değişkeni, işlevi, sınıf, typedef, statik olmayan veri üyesi, enum veya şablon uzmanlık kasıtlı olarak kullanılamayabilir olduğunu belirtir. Bir varlık işaretlendiğinde derleyici uyarmaz `[[maybe_unused]]` kullanılmaz. Özniteliği olmadan bildirilen bir varlık daha sonra öznitelik ve tersi yönde yeniden bildirilen. Bir varlık olarak işaretlenmiş ilk bildiriminden analiz sonra ve geçerli çeviri birim çevrilmesi kalanı için işaretlenmiş olarak kabul edilir.

## <a name="microsoft-specific-attributes"></a>Microsoft'a özgü öznitelikleri

- `[[gsl::suppress(rules)]]` Bu Microsoft özgü öznitelik zorunlu denetleyicileri gelen uyarıları gizleme için kullanılan [yönergeleri destek kitaplığı (GSL)](https://github.com/Microsoft/GSL) kod kuralları. Örneğin, bu kod parçacığını göz önünde bulundurun:

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

   Örneğin, bu uyarılar oluşturur:

   - 26494 (tür kural 5: her zaman bir nesne başlatılamıyor.)

   - 26485 (sınırları kural 3: hiçbir dizisine bir işaretçi decay.)

   - 26481 (sınırları kural 1: işaretçi aritmetiği kullanmayın. Aralık yerine bunu kullanın.)

   Bu kod yüklenmeli ve etkinleştirilmelidir CppCoreCheck kod analizi aracı ile derlerken ilk iki uyarıları kov. Ancak üçüncü uyarıyı nedeniyle öznitelik yangın değil. [[Gsl::suppress(bounds)]] yazarak bir özel kural numarası dahil olmak üzere tüm sınırların profil gizleyebilirsiniz. C++ çekirdek kılavuzları, daha iyi ve daha güvenli kod yazmanıza yardımcı olmak için tasarlanmıştır. Bastır özniteliği değil istediği zaman uyarılarını devre dışı bırakma kolaylaştırır.
