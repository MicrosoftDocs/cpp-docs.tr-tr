---
title: Bildirimler ve tanımlar (C++)
ms.date: 12/12/2019
ms.assetid: 678f1424-e12f-45e0-a957-8169e5fef6cb
ms.openlocfilehash: 7aa9e07a471ed5a32ecc8f13690f1a1bf08b655f
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077214"
---
# <a name="declarations-and-definitions-c"></a>Bildirimler ve tanımlar (C++)

C++ Program değişkenler, işlevler, türler ve ad alanları gibi çeşitli varlıklardan oluşur. Bu varlıkların her biri, kullanılmadan önce *bildirilmelidir* . Bir bildirim varlık için benzersiz bir ad ve kendi türü ve diğer özellikleri hakkında bilgi gösterir. C++ Bir adın bildirildiği noktada derleyiciye görünür hale geldiği bir noktasıdır. Derleme biriminde daha sonraki bir noktada belirtilen bir işleve veya sınıfa başvuramaz. Değişkenler, kullanıldıkları noktadan önce mümkün olduğunca yakın olarak bildirilmelidir.

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

5\. satırda `main` işlevi bildirilmiştir. 7\. satırda, `pi` adlı bir **const** değişkeni bildirilmiştir ve *başlatılır*. 8\. satırda, bir tamsayı `i`, işlev `f`tarafından üretilen değer ile bildirilmiştir ve başlatılır. `f` adı, 3. satırdaki *iletme bildirimi* nedeniyle derleyici tarafından görülebilir.

9\. satırda, `C` türünde `obj` adlı bir değişken bildirilmiştir. Ancak, bu bildirim bir hata oluşturur, çünkü `C` programın sonraki kısımlarında olana kadar bildirilmemiş ve ileriye dönük olarak bildirilmemiş. Hatayı onarmak için, `main` önce tüm `C` *tanımını* taşıyabilir ya da bunun için bir ileri bildirim ekleyebilirsiniz. Bu davranış C#, bir kaynak dosyasındaki bildirim noktasından önce işlev ve sınıfların kullanılabileceği gibi diğer dillerden farklıdır.

10. satırda, `std::string` türünde `str` adlı bir değişken bildirilmiştir. `std::string` adı, 1. satırdaki kaynak dosyayla birleştirilmiş `string` [üst bilgi dosyasında](header-files-cpp.md) tanıtıldığı için görülebilir. `std`, `string` sınıfının bildirildiği ad alanıdır.

11. satırda, `j` adı bildirilmemiş olduğundan bir hata oluşur. Bir bildirimin, javaScript gibi diğer dillerin aksine bir tür sağlaması gerekir. 12. satırda, derleyicinin `k` türünü, ile başlatıldığı değere göre çıkardığını belirten `auto` anahtar sözcüğü kullanılır. Bu örnekte derleyici tür için `int` seçer.  

## <a name="declaration-scope"></a>Bildirim kapsamı

Bildirim tarafından tanıtılan ad, bildirimin gerçekleştiği *kapsam* içinde geçerlidir. Önceki örnekte, `main` işlevi içinde belirtilen değişkenler *Yerel değişkenlerdir*. Ana, *genel kapsamda*`i` adlı başka bir değişken belirtebilirsiniz ve tamamen ayrı bir varlık olabilir. Ancak, bu tür bir ad yinelemesi programcı karışıklığına ve hatalara neden olabilir ve kaçınılması gerekir. 21. satırda `C` sınıfı, `N`ad alanı kapsamında bildirilmiştir. Ad alanı kullanımı *ad çakışmalarını*önlemeye yardımcı olur. Çoğu C++ standart kitaplık adı `std` ad alanı içinde bildirilmiştir. Kapsam kurallarının bildirimlerle nasıl etkileşim kurduğu hakkında daha fazla bilgi için bkz. [scope](../cpp/scope-visual-cpp.md).

## <a name="definitions"></a>Tanımlar

İşlevler, sınıflar, numaralandırmalar ve sabit değişkenler dahil olmak üzere bazı varlıkların, bildirildiği gibi tanımlanmalıdır. *Tanım* , derleyicinin programın ilerleyen kısımlarında makine kodu oluşturması için ihtiyaç duyacağı tüm bilgileri sağlar. Önceki örnekte, 3. satır `f` işlev için bir bildirim içerir, ancak işlevin *tanımı* , 15 ile 18 arası satırlarda sağlanır. 21. satırda, sınıf `C` hem hem de tanımlanır (tanımlanmış sınıfın hiçbir şey yapmamasına rağmen). Bir sabit değişken tanımlanmış, diğer bir deyişle, bildirildiği aynı ifadede bir değer atanmış olmalıdır. Derleyici için ne kadar alan ayrılacağını bildiğinden, `int` gibi yerleşik bir türün bildirimi otomatik olarak bir tanımdır.

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

Daha eski sürümlerinde C++, başka bir ad için *diğer* ad olan yeni bir ad bildirmek üzere [typedef](aliases-and-typedefs-cpp.md) anahtar sözcüğü kullanılır. Örneğin `std::string` tür `std::basic_string<char>`için başka bir addır. Programcıların, gerçek adı değil, typedef adını kullanmasının açık olması gerekir. Modern C++bir [using](aliases-and-typedefs-cpp.md) anahtar sözcüğü typedef üzerinden tercih edilir, ancak fikir aynıdır: zaten tanımlanmış ve tanımlı bir varlık için yeni bir ad bildirilmiştir.

## <a name="static-class-members"></a>Statik sınıf üyeleri

Statik sınıf veri üyeleri, sınıfının tüm nesneleri tarafından paylaşılan farklı değişkenler olduğundan, bunların sınıf tanımının dışında tanımlanması ve başlatılması gerekir. (Daha fazla bilgi için bkz. [sınıflar](../cpp/classes-and-structs-cpp.md).)

## <a name="extern-declarations"></a>extern bildirimleri

Bir C++ program birden fazla [derleme birimi](header-files-cpp.md)içerebilir. Ayrı bir derleme biriminde tanımlı bir varlık bildirmek için [extern](extern-cpp.md) anahtar sözcüğünü kullanın. Bildirimdeki bilgiler derleyici için yeterlidir, ancak varlığın tanımı bağlantı adımında bulunamıyorsa, bağlayıcı bir hata oluşturacak.

## <a name="in-this-section"></a>Bu bölümde

[Depolama sınıfları](storage-classes-cpp.md)<br/>
[const](const-cpp.md)<br/>
[constexpr](constexpr-cpp.md)<br/>
[extern](extern-cpp.md)<br/>
[Başlatıcılar](initializers.md)<br/>
[Diğer adlar ve tür tanımları](aliases-and-typedefs-cpp.md)<br/>
[using bildirimi](using-declaration.md)<br/>
[volatile](volatile-cpp.md)<br/>
[decltype](decltype-cpp.md)<br/>
[İçindeki özniteliklerC++](attributes.md)<br/>

## <a name="see-also"></a>Ayrıca bkz.

[Temel Kavramlar](../cpp/basic-concepts-cpp.md)<br/>
