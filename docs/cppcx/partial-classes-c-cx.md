---
title: Kısmi sınıflar (C++/CX)
ms.date: 12/30/2016
ms.assetid: 69d93575-636c-4564-8cca-6dfba0c7e328
ms.openlocfilehash: 703f12498e0f2c68448e2b3896d3d5f906aba779
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740487"
---
# <a name="partial-classes-ccx"></a>Kısmi sınıflar (C++/CX)

Kısmi bir sınıf, bir sınıf tanımının bir bölümünü değiştirmekte olduğunuz senaryoları destekleyen bir yapıdır ve örneğin XAML Tasarımcısı, aynı sınıftaki kodu de değiştiriyor. Kısmi bir sınıf kullanarak, tasarımcının kodunuzun üzerine yazmasını engelleyebilirsiniz. Visual Studio projesinde, `partial` değiştirici oluşturulan dosyaya otomatik olarak uygulanır.

## <a name="syntax"></a>Sözdizimi

Kısmi bir sınıf tanımlamak için `partial` anahtar sözcüğünü, diğer bir deyişle normal sınıf tanımı olacak şekilde sınıf anahtarından hemen önce kullanın. Gibi bir anahtar sözcük `partial ref class` , boşluk karakterleri içeren bir bağlamsal anahtar sözcüktür. Kısmi tanımlar aşağıdaki yapılar için desteklenir.

- `class` veya `struct`

- `ref class` veya `ref struct`

- `value class` veya `value struct`

- `enum` veya `enum class`

- `ref interface`, `interface class`,veya `interface struct``__interface`

- `union`

Bu örnekte kısmi `ref class`gösterilmektedir:

[!code-cpp[cx_partial#01](../cppcx/codesnippet/CPP/partialclassexample/class1.h#01)]

## <a name="contents"></a>İçindekiler

Bir kısmi sınıf tanımı, `partial` anahtar sözcüğü atlanmışsa tam sınıf tanımının içerebileceği her şeyi içerebilir. Tek bir özel durumla, bu, temel sınıflar, veri üyeleri, üye işlevleri, numaralandırmalar, arkadaş bildirimleri ve öznitelikler gibi geçerli bir yapıyı içerir. Statik veri üyelerinin satır içi tanımlarına izin verilir.

Bir özel durum sınıf erişilebilirliğine sahiptir. Örneğin, ifade `public partial class MyInvalidClass {/* ... */};` bir hatadır. Myınvalidclass için kısmi sınıf tanımında kullanılan erişim belirticileri, Myınvalidclass için sonraki kısmi veya tam sınıf tanımında varsayılan erişilebilirliği etkilemez.

Aşağıdaki kod parçası erişilebilirliği gösterir. İlk kısmi sınıfta, `Method1` erişilebilirliği ortak olduğundan geneldir. İkinci kısmi sınıfta, `Method2` varsayılan sınıf erişilebilirliği Private olduğundan özeldir.

[!code-cpp[cx_partial#02](../cppcx/codesnippet/CPP/partialclassexample/class1.h#02)]

## <a name="declaration"></a>Bildirim

*MyClass* gibi bir sınıfın kısmi tanımı yalnızca MyClass bildirimi olur. Diğer bir deyişle, yalnızca *MyClass*adını tanıtır. *MyClass* , bir sınıf tanımı gerektiren bir şekilde kullanılamaz, örneğin, *MyClass* boyutunu bilmek veya *MyClass*bir temelini ya da üyesini kullanmak. *MyClass* yalnızca derleyici, *MyClass*'ın kısmi olmayan tanımıyla karşılaştığında tanımlanması kabul edilir.

Aşağıdaki örnek, kısmi bir sınıfın bildirim davranışını gösterir. Bildirim #1 sonra *MyClass* , iletme bildirimi `ref class MyClass;`olarak yazılmış gibi kullanılabilir. Bildirim #2, bildirim #1 eşdeğerdir. bildirim #3, bir sınıfa yönelik bir iletme bildirimi olduğundan geçerlidir. Ancak bildirim #4 geçersiz çünkü

*MyClass* tam olarak tanımlı değil.

Bildirim #5 `partial` anahtar sözcüğünü kullanmaz ve bildirim tam olarak *MyClass*'yi tanımlar. Sonuç olarak, bildirim #6 geçerlidir.

[!code-cpp[Cx_partial#03](../cppcx/codesnippet/CPP/partialclassexample/class1.h#03)]

## <a name="number-and-ordering"></a>Sayı ve sıralama

Bir sınıfın her tam tanımı için sıfır veya daha fazla kısmi sınıf tanımı olabilir.

Bir sınıfın her kısmi sınıf tanımının, bu sınıfın bir tam tanımına sözcüksel olarak gelmesi gerekir, ancak sınıfın ileri bildirimlerin önüne geçmeleri gerekmez. Sınıfın tam tanımı yoksa, kısmi sınıf bildirimleri yalnızca iletme bildirimleri olabilir.

`class` Ve`struct` gibi tüm sınıf anahtarlarının eşleşmesi gerekir. Örneğin, kodda `partial class X {}; struct X {};`bir hata olabilir.

Aşağıdaki örnek, sayı ve sıralamayı gösterir. Sınıf zaten tanımlandığından son kısmi bildirim başarısız olur.

[!code-cpp[cx_partial#04](../cppcx/codesnippet/CPP/partialclassexample/class1.h#04)]

## <a name="full-definition"></a>Tam tanım

X sınıfının tam tanımının bulunduğu durumda, bu davranış, X tanımının tüm temel sınıfları, üyeleri, vb. olarak bildirdikleri ve kısmi sınıflarda tanımlandığı sırayla aynı olur. Diğer bir deyişle, kısmi sınıfların içerikleri, sınıfın tam tanımı üzerine yazıldıkları gibi değerlendirilir ve ad arama ve diğer dil kuralları, sınıfın tam tanımının kısmi sınıfların içeriği gibi bir noktasına uygulanır yerinde yazıldı

Aşağıdaki iki kod örneği aynı anlam ve etkiye sahiptir. İlk örnek, kısmi bir sınıf kullanır ve ikinci örnek değildir.

[!code-cpp[cx_partial#05](../cppcx/codesnippet/CPP/partialclassexample/class1.h#05)]

[!code-cpp[cx_partial#06](../cppcx/codesnippet/CPP/partialclassexample/class1.h#06)]

## <a name="templates"></a>Şablonlar

Kısmi bir sınıf şablon olamaz.

## <a name="restrictions"></a>Kısıtlamalar

Kısmi bir sınıf, bir çeviri biriminin ötesine yayılamaz.

Anahtar sözcüğü yalnızca `ref class` anahtar sözcüğü veya `value class` anahtar sözcüğü ile birlikte desteklenir. `partial`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek, `Address` sınıfını iki kod dosyası genelinde tanımlar. Tasarımcı `Address.details.h` değiştirilir ve değiştirirsiniz `Address.h`. Yalnızca ilk dosyadaki sınıf tanımı `partial` anahtar sözcüğünü kullanır.

[!code-cpp[cx_partial#07](../cppcx/codesnippet/CPP/partialclassexample/address.details.h#07)]

[!code-cpp[cx_partial#09](../cppcx/codesnippet/CPP/partialclassexample/address.h#09)]

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
