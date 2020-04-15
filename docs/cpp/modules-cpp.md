---
title: C++ içindeki modüllere genel bakış
ms.date: 12/13/2019
helpviewer_keywords:
- modules [C++]
- modules [C++], overview
description: C++20'deki modüller üstbilgi dosyalarına modern bir alternatif sunar.
ms.openlocfilehash: cd45be1dee888c8caeb65b7ff002ac8fee1ecbe1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370754"
---
# <a name="overview-of-modules-in-c"></a>C++ içindeki modüllere genel bakış

C++20, C++ kitaplıklarının ve programlarının bileşenleştirilmesi için modern bir çözüm olan *modülleri*tanıtır. Modül, bunları içe aktaran [çeviri birimlerinden](https://wikipedia.org/wiki/Translation_unit_(programming)) bağımsız olarak derlenen kaynak kod dosyaları kümesidir. Modüller üstbilgi dosyalarının kullanımıyla ilişkili sorunların çoğunu ortadan kaldırır veya büyük ölçüde azaltır ve derleme sürelerini de potansiyel olarak azaltır. Modülde bildirilen makrolar, önişlemci yönergeleri ve dışa aktarılmaz adlar görünmez ve bu nedenle modülü ithal eden çeviri biriminin derlemesi üzerinde hiçbir etkisi yoktur. Makro yeniden tanımlamaları için endişelenmeden modülleri istediğiniz sırada içe aktarabilirsiniz. İthalat ılıma birimdeki bildirimler, alınan modülde aşırı yük çözünürlüğü veya ad araması yapmaz. Bir modül bir kez derlendikten sonra, sonuçlar tüm dışa aktarılan türleri, işlevleri ve şablonları açıklayan bir ikili dosyada depolanır. Bu dosya üstbilgi dosyasından çok daha hızlı işlenebilir ve derleyici tarafından modülün bir projede içe aktarıldığı her yerde yeniden kullanılabilir.

Modüller üstbilgi dosyalarıyla yan yana kullanılabilir. C++ kaynak dosyası modülleri içe aktarabilir ve üstbilgi dosyalarına #include. Bazı durumlarda, üstbilgi dosyası önişlemci tarafından metinsel olarak #included yerine bir modül olarak içe aktarılabilir. Yeni projelerin üstbilgi dosyaları yerine mümkün olduğunca modülkullanmalarını öneririz. Etkin geliştirme aşamasındaki daha büyük mevcut projeler için, derleme sürelerinde anlamlı bir azalma alıp almadığınızı görmek için eski üstbilgibaşlıklarını modüllere dönüştürmeyi denemenizi öneririz.

## <a name="enable-modules-in-the-microsoft-c-compiler"></a>Microsoft C++ derleyicisindeki modülleri etkinleştirme

Visual Studio 2019 sürüm 16.2 itibariyle, modüller Microsoft C++ derleyicisinde tam olarak uygulanmaz. Modüller özelliğini tek bölümlü modüller oluşturmak ve Microsoft tarafından sağlanan Standart Kitaplık modüllerini almak için kullanabilirsiniz. Modüller için destek sağlamak için [,/experimental:module](../build/reference/experimental-module.md) ve [/std:c++latest](../build/reference/std-specify-language-standard-version.md)ile derleyin. Visual Studio projesinde, **Solution Explorer'daki** proje düğümüne sağ tıklayın ve **Özellikler'i**seçin. Yapılandırma açılır **düşüşünü** **Tüm Yapılandırmalara**ayarlayın, ardından **Configuration Properties** > **C/C++** > **Language** > **Enable C++ Modüllerini (deneysel)** seçin.

Bir modül ve onu tüketen kod aynı derleyici seçenekleriyle derlenmelidir.

## <a name="consume-the-c-standard-library-as-modules"></a>C++ Standart Kitaplığını modül olarak tüketin

C++20 standardı tarafından belirtilmese de, Microsoft C++ Standart Kitaplığı uygulamasının modül olarak içe aktarılmasını sağlar. C++ Standart Kitaplığını üstbilgi dosyaları üzerinden #including yerine modül olarak içe aktararak, projenizin boyutuna bağlı olarak derleme sürelerini hızlandırabilirsiniz. Kitaplık aşağıdaki modüllere ayrılır:

- std.regex başlık \<regex içeriğini sağlar>
- std.filesystem üstbilgi \<dosya sisteminin içeriğini sağlar>
- std.memory başlık \<bellek içeriği sağlar>
- std.threading başlıklar \<atom>, \<condition_variable>, \<gelecekteki \<>, \<mutex>, shared_mutex> ve \<iş parçacığı> içeriğini sağlar
- std.core C++ Standart Kitaplığı'ndaki diğer her şeyi sağlar

Bu modülleri tüketmek için kaynak kod dosyasının en üstüne bir alma bildirimi eklemeniz gerekir. Örneğin:

```cpp
import std.core;
import std.regex;
```

Microsoft Standart Kitaplığı modüllerini tüketmek için programınızı [/EHsc](../build/reference/eh-exception-handling-model.md) ve [/MD](../build/reference/md-mt-ld-use-run-time-library.md) seçenekleriyle derleyin.

## <a name="basic-example"></a>Temel örnek

Aşağıdaki örnek, **Foo.ixx**adlı bir kaynak dosyada basit bir modül tanımı gösterir. **.ixx** uzantısı Visual Studio modül arabirim dosyaları için gereklidir. Bu örnekte, arabirim dosyası işlev tanımının yanı sıra bildirimi de içerir. Ancak, tanımlar bir veya daha fazla ayrı dosyaya da yerleştirilebilir (daha sonraki bir örnekte gösterildiği gibi). **Dışa aktarma modülü Foo** deyimi, bu dosyanın `Foo`. Üzerinde `f()` `Foo` **dışa** aktarma değiştirici, bu işlevin başka bir program veya modül tarafından içe aktarıldığında görünür olacağını gösterir. Modülün bir ad alanına `Bar`başvurulabilir.

```cpp
export module Foo;

#define ANSWER 42

namespace Bar
{
   int f_internal() {
        return ANSWER;
      }

   export int f() {
      return f_internal();
   }
}
```

**MyProgram.cpp** dosyası, `Foo`dışa aktarılan ada erişmek için **alma** bildirimini kullanır. Adın `Bar` burada görülebildiğine, ancak tüm üyelerinin görünmediğini unutmayın. Ayrıca makronun `ANSWER` görünür olmadığını da unutmayın.

```cpp

import Foo;
import std.core;

using namespace std;

int main()
{
   cout << "The result of f() is " << Bar::f() << endl; // 42
   // int i = Bar::f_internal(); // C2039
   // int j = ANSWER; //C2065
}

```

Alma bildirimi yalnızca genel kapsamda görünebilir.

## <a name="implementing-modules"></a>Modüllerin uygulanması

Adları dışa aktaran ve tüm işlevlerin ve türlerin uygulamalarını içeren tek bir arabirim dosyasına (.ixx) sahip bir modül oluşturabilirsiniz. Uygulamaları,.h ve .cpp dosyalarının nasıl kullanıldığına benzer bir veya daha fazla ayrı uygulama dosyasına da koyabilirsiniz. **Dışa aktarma** anahtar kelimesi yalnızca arabirim dosyasında kullanılır. Uygulama dosyası başka bir modülü **içe aktarabilir,** ancak herhangi bir ad **dışa** aktaramaz. Uygulama dosyaları herhangi bir uzantı ile adlandırılabilir. Bir arayüz dosyası ve geri uygulama dosyaları kümesi *bir modül birimi*olarak adlandırılan çeviri birimi özel bir tür olarak kabul edilir. Herhangi bir uygulama dosyasında bildirilen ad, aynı modül birimindeki diğer tüm dosyalarda otomatik olarak görünür.

Daha büyük modüller için, modülü *bölüm*adı verilen birden çok modül birimine bölebilirsiniz. Her bölüm, bir veya daha fazla uygulama dosyası tarafından desteklenen bir arabirim dosyasından oluşur. (Visual Studio 2019 sürüm 16.2 itibariyle, bölümler henüz tam olarak uygulanmamıştır.)

## <a name="modules-namespaces-and-argument-dependent-lookup"></a>Modüller, ad alanları ve bağımsız değişkene bağımlı arama

Modüllerde ad alanları için kurallar diğer kodlarla aynıdır. Ad alanı içindeki bir bildirim dışa aktarılırsa, çevreleyen ad alanı (dışa aktarma yapılan üyeler hariç) da dolaylı olarak dışa aktarılır. Ad alanı açıkça dışa aktarılırsa, bu ad alanı tanımıiçindeki tüm bildirimler dışa aktarılır.

Derleyici, içe aktarma birimindeki aşırı yük çözümleri için bağımsız değişkene bağımlı arama yaparken, aynı çeviri biriminde (modül arabirimleri dahil) bildirilen işlevleri, işlevin bağımsız değişkenlerinin türünün tanımlandığı şekilde değerlendirir.

### <a name="module-partitions"></a>Modül bölümleri

> [!NOTE]
> Bu bölüm bütünlük için sağlanmıştır. Microsoft C++ derleyicisinde bölümler henüz uygulanmamıştır.

Bir modül *bölümlere,* her biri bir arabirim dosyası ve sıfır veya daha fazla uygulama dosyasından oluşan bölümlere dönüştürülebilir. Modül bölümü, tüm modüldeki tüm bildirimlerin sahipliğini paylaşması dışında bir modüle benzer. Bölüm arabirimi dosyaları tarafından dışa aktarılan tüm adlar, birincil arabirim dosyası tarafından içe aktarılır ve yeniden dışa aktarılır. Bir bölümün adı, bir üst üste gelen modül adı ile başlamalıdır. Bölümlerin herhangi birinde bildirimler tüm modül içinde görülebilir. Tek tanımlı kural (ODR) hatalarından kaçınmak için özel önlemler gerekmez. Bir bölümde bir ad (işlev, sınıf, vb.) bildirebilir ve başka bir bölümde tanımlayabilirsiniz. Bir bölüm uygulama dosyası şu şekilde başlar:

```cpp
module Foo:part1
```

ve bölüm arabirimi dosyası aşağıdaki gibi başlar:

```cpp
export module Foo:part1
```

Başka bir bölümdeki bildirimlere erişmek için, bir bölümün içe aktarması gerekir, ancak modül adını değil, yalnızca bölüm adını kullanabilir:

```cpp
module Foo:part2;
import :part1;
```

Birincil arabirim birimi, modülün tüm arabirim bölüm dosyalarını şu şekilde içe aktarmalı ve yeniden dışa aktarmalıdır:

```cpp
export import :part1
export import :part2
...
```

Birincil arabirim birimi bölüm uygulama dosyalarını içe aktarabilir, ancak bu dosyaların herhangi bir ad dışa aktarmasına izin verilmediği için bunları dışa aktaramaz. Bu, bir modülün uygulama ayrıntılarını modüle dahil tutmasını sağlar.

## <a name="modules-and-header-files"></a>Modüller ve üstbilgi dosyaları

Yönergeyi modül bildiriminin `#include` önüne koyarak üstbilgi dosyalarını modül kaynak dosyasına ekleyebilirsiniz. Bu dosyalar genel modül *parçası*olarak kabul edilir. Bir modül yalnızca açıkça içerdiği üstbilgideki *genel modül parçasındaki* adları görebilir. Genel modül parçası yalnızca gerçekte kullanılan semboller içerir.

```cpp
// MyModuleA.cpp

#include "customlib.h"
#include "anotherlib.h"

import std.core;
import MyModuleB;

//... rest of file
```

Hangi modüllerin alındığını denetlemek için geleneksel bir üstbilgi dosyası kullanabilirsiniz:

```cpp
// MyProgram.h
import std.core;
#ifdef DEBUG_LOGGING
import std.filesystem;
#endif
```

### <a name="imported-header-files"></a>İçe aktarılan üstbilgi dosyaları

> [!NOTE]
> Bu bölüm yalnızca bilgilendirme amaçlıdır. Eski içeri almalar henüz Microsoft C++ derleyicisinde uygulanmamıştır.

Bazı üstbilgi, **alma** anahtar sözcüğü kullanılarak getirilmelerine izin verilecek kadar bağımsızdır. İçe aktarılan üstbilgi ile içe aktarılan modül arasındaki temel fark, üstbilgideki önişlemci tanımlarının alma bildiriminden hemen sonra alma programında görünür olmasıdır. (Bu üstbilgi tarafından dahil edilen dosyalardaki *not* önişlemci tanımları görünmez.)

```cpp
import <vector>
import "myheader.h"
```

## <a name="see-also"></a>Ayrıca bkz.

[modül, içeri aktarma, dışarı aktarma](import-export-module.md)
