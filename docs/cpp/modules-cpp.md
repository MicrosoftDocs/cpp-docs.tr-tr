---
title: C++ içindeki modüllere genel bakış
ms.date: 12/13/2019
helpviewer_keywords:
- modules [C++]
- modules [C++], overview
description: C++ 20 ' deki modüller üst bilgi dosyalarına modern bir alternatif sağlar.
ms.openlocfilehash: 286d2ec8a26dbd0a85e8f8721ad6fd7f12f45a31
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078036"
---
# <a name="overview-of-modules-in-c"></a>C++ içindeki modüllere genel bakış

C++ 20, *modules*kitaplıkları ve programları çözüme yönelik modern bir çözüm olan C++ modülleri tanıtır. Modül, içeri aktarılan [çeviri birimlerinden](https://wikipedia.org/wiki/Translation_unit_(programming)) bağımsız olarak derlenen bir kaynak kod dosyaları kümesidir. Modüller, üst bilgi dosyaları kullanımıyla ilişkili birçok sorunu ortadan kaldırır veya büyük ölçüde azaltır, ayrıca derleme sürelerini de azaltabilir. Bir modülde belirtilen makrolar, Önişlemci yönergeleri ve dışa aktarılmamış adlar görünür değildir ve bu nedenle modülü içeri aktaran çeviri biriminin derlenmesi üzerinde hiçbir etkisi yoktur. Herhangi bir sırada, makro yeniden tanımlarına yönelik bir sorun olmadan modülleri içeri aktarabilirsiniz. İçeri aktarma çeviri birimindeki bildirimler, içeri aktarılan modülde aşırı yükleme çözümüne veya ad aramasına katılmaz. Bir modül bir kez derlendikten sonra sonuçlar, tüm aktarılmış türleri, işlevleri ve şablonları açıklayan bir ikili dosyada depolanır. Bu dosya bir üstbilgi dosyasından çok daha hızlı işlenebilir ve derleyici bir projeye içeri aktarılırken her yerde derleyici tarafından yeniden kullanılabilir.

Modüller, üst bilgi dosyaları ile yan yana kullanılabilir. C++ Kaynak dosya, modülleri içeri aktarabilir ve ayrıca üstbilgi dosyalarını #include. Bazı durumlarda, bir üst bilgi dosyası Önişlemci tarafından metin içeriğini eklemek #included yerine bir modül olarak içeri aktarılabilir. Yeni projelerin, üst bilgi dosyaları yerine modüller kullanmasını mümkün olduğunca çok tercih ederiz. Etkin geliştirme kapsamındaki daha büyük mevcut projeler için, derleme saatlerinde anlamlı bir azaltma elde edilip edilmeyeceğini görmek üzere eski üst bilgileri modüllere dönüştürmeyi öneririz.

## <a name="enable-modules-in-the-microsoft-c-compiler"></a>Microsoft C++ derleyicisinde modülleri etkinleştirme

Visual Studio 2019 sürüm 16,2 itibariyle, modüller Microsoft C++ derleyicisinde tam olarak uygulanmamıştır. Modüller özelliğini kullanarak tek bölümlü modüller oluşturabilir ve Microsoft tarafından sunulan standart kitaplık modüllerini içeri aktarabilirsiniz. Modüller desteğini etkinleştirmek için [/deneysel: Module](../build/reference/experimental-module.md) ve [/std: c + + en son](../build/reference/std-specify-language-standard-version.md)ile derleyin. Visual Studio projesinde **Çözüm Gezgini** ' de proje düğümüne sağ tıklayın ve **Özellikler**' i seçin. **Yapılandırma** açılan öğesini **tüm yapılandırmalar**olarak ayarlayın ve ardından **yapılandırma özellikleri** > **C++ C/**  > **dil** >  **C++ modülleri etkinleştir (deneysel)** seçeneğini belirleyin.

Bir modül ve onu tüketen kod aynı derleyici seçenekleriyle derlenmelidir.

## <a name="consume-the-c-standard-library-as-modules"></a>C++ Standart kitaplığı modüller olarak kullanma

C++ 20 standardı tarafından belirtilmediği halde Microsoft, C++ standart kitaplık uygulamasının, modül olarak içeri aktarılmalarını sağlar. Standart Kitaplığı, C++ üst bilgi dosyaları aracılığıyla #including yerine modüller olarak içeri aktararak, projenizin boyutuna bağlı olarak derleme sürelerini hızlandırabilirsiniz. Kitaplık aşağıdaki modüllere bileşen haline sahiptir:

- STD. Regex üst bilgi \<Regex içeriğini sağlar >
- STD. FileSystem, üstbilgi \<FileSystem içeriğini sağlar >
- STD. bellek, üst bilgi \<bellek > içeriğini sağlar
- STD. Threading \<atomik >, \<condition_variable >, gelecekteki \<>, \<mutex >, \<shared_mutex > ve \<iş parçacığı için üst bilgilerin içeriğini sağlar >
- STD. Core, C++ standart kitaplıkta diğer her şeyi sağlar

Bu modülleri kullanmak için, kaynak kodu dosyasının en üstüne bir içeri aktarma bildirimi eklemeniz yeterlidir. Örnek:

```cpp
import std.core;
import std.regex;
```

Microsoft standart kitaplık modülünü kullanmak için, programınızı [/EHsc](../build/reference/eh-exception-handling-model.md) ve [/md](../build/reference/md-mt-ld-use-run-time-library.md) seçenekleriyle derleyin.

## <a name="basic-example"></a>Temel örnek

Aşağıdaki örnek, bir kaynak dosyasında **foo. IXX**adlı basit bir modül tanımını gösterir. Visual Studio 'da modül arabirimi dosyaları için **. IXX** uzantısı gereklidir. Bu örnekte, arabirim dosyası, bir işlev tanımını ve bildirimi içerir. Ancak, tanımlar aynı zamanda bir veya daha fazla ayrı dosyaya yerleştirilebilir (sonraki örnekte gösterildiği gibi). **Export Module foo** ifadesini, bu dosyanın `Foo`adlı bir modülün birincil arabirimi olduğunu gösterir. `f()` ' deki **dışarı aktarma** değiştiricisi, `Foo` başka bir program veya modül tarafından içeri aktarıldığında bu işlevin görünür olacağını gösterir. Modülün `Bar`bir ad alanına başvurmadığını unutmayın.

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

**MyProgram. cpp** dosyası, `Foo`tarafından dışarı aktarılan ada erişmek için **içeri aktarma** bildirimini kullanır. Ad `Bar` burada görünür olduğunu, ancak tüm üyelerini Not etmez. Ayrıca makro `ANSWER` görünür olmadığına de unutmayın.

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

İçeri aktarma bildirimi yalnızca genel kapsamda görünebilir.

## <a name="implementing-modules"></a>Modül uygulama

Adları dışarı aktaran ve tüm işlevlerin ve türlerin uygulamalarını içeren tek bir arabirim dosyası (. IXX) içeren bir modül oluşturabilirsiniz. Ayrıca,. h ve. cpp dosyalarının kullanılmasına benzer şekilde, uygulamaları bir veya daha fazla ayrı uygulama dosyasına koyabilirsiniz. **Export** anahtar sözcüğü yalnızca arabirim dosyasında kullanılır. Uygulama dosyası başka bir modülü **içeri** aktarabilir, ancak hiçbir adı **veremez** . Uygulama dosyaları herhangi bir uzantıyla adlandırılmış olabilir. Bir arabirim dosyası ve onu geri yükleyen uygulama dosyaları kümesi, *Modül birimi*olarak adlandırılan özel bir çeviri birimi türü olarak değerlendirilir. Herhangi bir uygulama dosyasında belirtilen bir ad, aynı modül birimi içindeki diğer tüm dosyalarda otomatik olarak görünür.

Daha büyük modüller için, modülü *bölümler*adlı birden fazla modül birimine bölebilirsiniz. Her bölüm bir veya daha fazla uygulama dosyası tarafından desteklenen bir arabirim dosyasından oluşur. (Visual Studio 2019 sürüm 16,2 itibariyle, bölümler henüz tam olarak uygulanmadı.)

## <a name="modules-namespaces-and-argument-dependent-lookup"></a>Modüller, ad alanları ve bağımsız değişkene bağlı arama

Modüllerde ad alanları için kurallar, diğer tüm kodlar ile aynıdır. Bir ad alanı içindeki bir bildirim verildiğinde, kapsayan ad alanı (verilemeyen Üyeler hariç) örtük olarak da aktarılabilir. Bir ad alanı açıkça aktarılıyorsa, bu ad alanı tanımındaki tüm bildirimler verilir.

İçeri aktarma çeviri birimindeki aşırı yükleme çözümleri için bağımsız değişkene bağlı arama gerçekleştirirken, derleyici aynı çeviri biriminde (modül arabirimleri dahil), işlevin bağımsız değişkenlerinin türü olarak belirtilen işlevleri kabul eder tanımlanmıştır.

### <a name="module-partitions"></a>Modül bölümleri

> [!NOTE]
> Bu bölüm, eksiksiz bir şekilde sağlanır. Bölümler henüz Microsoft C++ derleyicisinde uygulanmamıştır.

Bir modül, her biri bir arabirim dosyası ve sıfır veya daha fazla uygulama dosyasından oluşan *bölümler*halinde bileşen oluşturabilir. Modül bölümü modülle benzerdir, ancak modülün tamamında tüm bildirimlerin sahipliğini paylaşır. Bölüm arabirimi dosyaları tarafından içeri aktarılan tüm adlar içeri aktarılır ve birincil arabirim dosyası tarafından yeniden verilir. Bir bölümün adı modül adıyla başlamalı ve iki nokta üst üste gelmelidir. Bölümlerin hiçbirinde bulunan bildirimler tüm modülün içinde görünür. Tek tanım kuralı (ODR) hatalarından kaçınmak için özel önlemler gerekmez. Bir ad (Function, Class, vb.) bir bölüm içinde bildirebilir ve bunu başka bir bölümde tanımlayabilirsiniz. Bölüm uygulama dosyası şöyle başlar:

```cpp
module Foo:part1
```

ve bölüm arabirimi dosyası şöyle başlar:

```cpp
export module Foo:part1
```

Başka bir bölümdeki bildirimlere erişmek için bir bölümün içeri aktarılması gerekir, ancak yalnızca bölüm adı kullanılabilir, modül adı değil:

```cpp
module Foo:part2;
import :part1;
```

Birincil arabirim birimi aşağıdaki gibi tüm modülün arabirim bölüm dosyalarını içeri aktarıp yeniden dışarı aktarmalıdır:

```cpp
export import :part1
export import :part2
...
```

Birincil arabirim birimi bölüm uygulama dosyalarını içeri aktarabilir, ancak bu dosyaların adları dışarı aktarmaya izin verilmediği için dışarı aktaramazsınız. Bu, bir modülün modül içi uygulama ayrıntılarını tutmasını sağlar.

## <a name="modules-and-header-files"></a>Modüller ve üstbilgi dosyaları

Modül bildiriminden önce `#include` yönergesini yerleştirerek bir modül kaynak dosyasına üst bilgi dosyalarını dahil edebilirsiniz. Bu dosyalar, *genel modül parçasında*olduğu kabul edilir. Modül, *genel modül parçasındaki* adları yalnızca açıkça içerdiği üst bilgilerde görebilir. Genel modül parçası yalnızca gerçekten kullanılan sembolleri içerir.

```cpp
// MyModuleA.cpp

#include "customlib.h"
#include "anotherlib.h"

import std.core;
import MyModuleB;

//... rest of file
```

Hangi modüllerin içeri aktarılacağını denetlemek için geleneksel bir üst bilgi dosyası kullanabilirsiniz:

```cpp
// MyProgram.h
import std.core;
#ifdef DEBUG_LOGGING
import std.filesystem;
#endif
```

### <a name="imported-header-files"></a>İçeri aktarılan üst bilgi dosyaları

> [!NOTE]
> Bu bölüm yalnızca bilgilendirme amaçlıdır. Eski içeri aktarmalar henüz Microsoft C++ derleyicisinde uygulanmadı.

Bazı üst bilgiler, **içeri aktarma** anahtar sözcüğünü kullanarak kullanılmasına izin verildikleri kadar bağımsızdır. İçeri aktarılan bir üst bilgi ve içeri aktarılan bir modül arasındaki temel fark, üstbilgideki tüm önişlemci tanımlarının içeri aktarma ifadesinden hemen sonra içeri aktarma programında görünür hale gelmelidir. (Bu üst bilgi tarafından eklenen dosyalardaki Önişlemci tanımları görünür *değildir* .)

```cpp
import <vector>
import "myheader.h"
```

## <a name="see-also"></a>Ayrıca bkz.

[Modül, içeri aktarma, dışarı aktarma](import-export-module.md)
