---
description: 'Hakkında daha fazla bilgi edinin: bildirimler ve tanımlar (C++)'
title: Bildirimler ve tanımlar (C++)
ms.date: 12/12/2019
ms.assetid: 678f1424-e12f-45e0-a957-8169e5fef6cb
ms.openlocfilehash: 00d86e4df70e150a2e9f2417050b47b943a054ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339520"
---
# <a name="declarations-and-definitions-c"></a>Bildirimler ve tanımlar (C++)

C++ programı, değişkenler, işlevler, türler ve ad alanları gibi çeşitli varlıklardan oluşur. Bu varlıkların her biri, kullanılmadan önce *bildirilmelidir* . Bir bildirim varlık için benzersiz bir ad ve kendi türü ve diğer özellikleri hakkında bilgi gösterir. C++ ' da, bir adın bildirildiği nokta derleyiciye görünür hale geldiği noktasıdır. Derleme biriminde daha sonraki bir noktada belirtilen bir işleve veya sınıfa başvuramaz. Değişkenler, kullanıldıkları noktadan önce mümkün olduğunca yakın olarak bildirilmelidir.

Aşağıdaki örnekte bazı bildirimler gösterilmektedir:

```cpp
#include <string>

void f(); // forward declaration

int main()
{
    const double pi = 3.14; //OK
    int i = f(2); //OK. f is forward-declared
    std::string str; // OK std::string is declared in <string> header
    C obj; // error! C not yet declared.
    j = 0; // error! No type specified.
    auto k = 0; // OK. type inferred as int by compiler.
}

int f(int i)
{
    return i + 42;
}

namespace N {
   class C{/*...*/};
}
```

5. satırda, `main` işlev bildirilmiştir. 7. satırda, **`const`** adlı bir değişken `pi` bildirilmiştir ve *başlatılır*. 8. satırda, bir tamsayı `i` bildirilmiştir ve işlev tarafından üretilen değer ile başlatılır `f` . `f`3. satırdaki *iletme bildirimi* nedeniyle ad derleyici tarafından görülebilir.

9. satırda, tür adlı bir değişken `obj` `C` bildirilmiştir. Ancak, bu bildirim bir hata oluşturur çünkü `C` daha sonra program içinde bildirilmemiş ve ileriye dönük olarak bildirilmemiş. Hatayı onarmak için önce tüm *tanımını* taşıyabilir `C` ya da `main` bunun için bir ileri bildirim ekleyebilirsiniz. Bu davranış, C# gibi işlevlerin ve sınıfların bir kaynak dosyadaki bildirim noktasından önce kullanılabileceği diğer dillerden farklıdır.

10. satırda, tür adlı bir değişken `str` `std::string` bildirilmiştir. Bu ad, `std::string` `string` 1. satırda kaynak dosyayla birleştirilmiş [üst bilgi dosyasında](header-files-cpp.md) tanıtıldığı için görülebilir. `std` , `string` sınıfının bildirildiği ad alanıdır.

11. satırda, ad bildirilmemiş olduğundan bir hata oluşur `j` . Bir bildirimin, javaScript gibi diğer dillerin aksine bir tür sağlaması gerekir. 12 **`auto`** . satırda anahtar sözcüğü kullanılır, bu da derleyiciye başlatıldığı değere göre türü çıkarmasını söyler `k` . Bu örnekte derleyici **`int`** tür için seçer.  

## <a name="declaration-scope"></a>Bildirim kapsamı

Bildirim tarafından tanıtılan ad, bildirimin gerçekleştiği *kapsam* içinde geçerlidir. Önceki örnekte, işlevinin içinde bildirildiği değişkenler `main` *Yerel değişkenlerdir*. `i` *Genel kapsamda* Main dışında adlı başka bir değişken bildirebilir ve tamamen ayrı bir varlık olabilir. Ancak, bu tür bir ad yinelemesi programcı karışıklığına ve hatalara neden olabilir ve kaçınılması gerekir. 21. satırda, sınıf `C` ad alanının kapsamında bildirilmiştir `N` . Ad alanı kullanımı *ad çakışmalarını* önlemeye yardımcı olur. Çoğu C++ Standart Kitaplık adı ad alanı içinde bildirilmiştir `std` . Kapsam kurallarının bildirimlerle nasıl etkileşim kurduğu hakkında daha fazla bilgi için bkz. [scope](../cpp/scope-visual-cpp.md).

## <a name="definitions"></a>Tanımlar

İşlevler, sınıflar, numaralandırmalar ve sabit değişkenler dahil olmak üzere bazı varlıkların, bildirildiği gibi tanımlanmalıdır. *Tanım* , derleyicinin programın ilerleyen kısımlarında makine kodu oluşturması için ihtiyaç duyacağı tüm bilgileri sağlar. Önceki örnekte, 3. satırda, işlev için bir bildirim bulunur, `f` ancak işlevin *tanımı* , 15 ile 18 arası satırlarda sağlanır. 21. satırda, sınıf `C` hem olarak hem de tanımlanır (tanımlanmış sınıf hiçbir şey yapmasa da). Bir sabit değişken tanımlanmış, diğer bir deyişle, bildirildiği aynı ifadede bir değer atanmış olmalıdır. **`int`** Derleyici için ne kadar alan ayrılacağını bildiğinden, gibi yerleşik bir türün bildirimi otomatik olarak bir tanımdır.

Aşağıdaki örnek ayrıca tanımlar olan bildirimleri gösterir:

```cpp
// Declare and define int variables i and j.
int i;
int j = 10;

// Declare enumeration suits.
enum suits { Spades = 1, Clubs, Hearts, Diamonds };

// Declare class CheckBox.
class CheckBox : public Control
{
public:
    Boolean IsChecked();
    virtual int     ChangeState() = 0;
};
```

Tanımları olmayan bazı bildirimler aşağıda verilmiştir:

```cpp
extern int i;
char *strchr( const char *Str, const char Target );
```

## <a name="typedefs-and-using-statements"></a>Typedefs ve using deyimleri

C++ ' ın eski sürümlerinde [`typedef`](aliases-and-typedefs-cpp.md) anahtar sözcüğü, başka bir ad için *diğer* ad olan yeni bir ad bildirmek üzere kullanılır. Örneğin, türü `std::string` için başka bir addır `std::basic_string<char>` . Programcıların, gerçek adı değil, typedef adını kullanmasının açık olması gerekir. Modern C++ ' da, [`using`](aliases-and-typedefs-cpp.md) anahtar sözcük tercih edilir **`typedef`** , ancak fikir aynıdır: zaten bildirildiği ve tanımlanan bir varlık için yeni bir ad bildirilmiştir.

## <a name="static-class-members"></a>Statik sınıf üyeleri

Statik sınıf veri üyeleri, sınıfının tüm nesneleri tarafından paylaşılan farklı değişkenler olduğundan, bunların sınıf tanımının dışında tanımlanması ve başlatılması gerekir. (Daha fazla bilgi için bkz. [sınıflar](../cpp/classes-and-structs-cpp.md).)

## <a name="extern-declarations"></a>extern bildirimleri

C++ programı birden fazla [derleme birimi](header-files-cpp.md)içerebilir. Ayrı bir derleme biriminde tanımlı bir varlık bildirmek için [`extern`](extern-cpp.md) anahtar sözcüğünü kullanın. Bildirimdeki bilgiler derleyici için yeterlidir, ancak varlığın tanımı bağlantı adımında bulunamıyorsa, bağlayıcı bir hata oluşturacak..

## <a name="in-this-section"></a>Bu bölümde

[Depolama sınıfları](storage-classes-cpp.md)<br/>
[`const`](const-cpp.md)<br/>
[`constexpr`](constexpr-cpp.md)<br/>
[`extern`](extern-cpp.md)<br/>
[Başlatıcılar](initializers.md)<br/>
[Diğer adlar ve tür tanımları](aliases-and-typedefs-cpp.md)<br/>
[`using` bağımsız](using-declaration.md)<br/>
[`volatile`](volatile-cpp.md)<br/>
[`decltype`](decltype-cpp.md)<br/>
[C++ içindeki öznitelikler](attributes.md)<br/>

## <a name="see-also"></a>Ayrıca bkz.

[Temel kavramlar](../cpp/basic-concepts-cpp.md)<br/>
