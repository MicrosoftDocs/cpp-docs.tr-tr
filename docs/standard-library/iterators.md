---
title: Yineleyiciler
ms.date: 11/04/2016
helpviewer_keywords:
- iterator conventions
- C++ Standard Library, iterator conventions
ms.assetid: 2f746be7-b37d-4bfc-bf05-be4336ca982f
ms.openlocfilehash: eaa4d50fc50528febf923f1c13a5283b9a1bd389
ms.sourcegitcommit: 8645408c7929558b8162f781776d0908d790a41c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85334959"
---
# <a name="iterators"></a>Yineleyiciler

Yineleyici, C++ standart kitaplığı kapsayıcısındaki öğeleri yinelemek ve tek tek öğelere erişim sağlamak için bir nesnedir. C++ standart kitaplığı kapsayıcıları, algoritmaların öğelerine, öğelerin depolandığı kapsayıcı türüyle ilgilenmeden bir standart şekilde erişmelerini sağlamak için yineleyiciler sağlar.

Yineleyiciler, ve gibi nesneler ve genel işlevleri kullanarak, ve gibi `begin()` `end()` İşleçler ve `++` `--` İleri veya geri taşımak için kullanabilirsiniz. Yineleyiciler bir for döngüsü veya (bazı yineleyici türleri için) alt simge işleci ile örtülü olarak da kullanabilirsiniz `[]` .

C++ standart kitaplığında, bir sıranın veya aralığın başlangıcı ilk öğedir. Bir sıranın veya aralığın sonu her zaman son öğeden bir geçmiş olarak tanımlanır. Genel işlevler `begin` ve `end` yineleyiciler belirtilen kapsayıcıya döndürülür. Bir kapsayıcıdaki tüm öğeler üzerinde tipik açık Yineleyici döngüsü şöyle görünür:

```cpp
vector<int> vec{ 0,1,2,3,4 };
for (auto it = begin(vec); it != end(vec); it++)
{
    // Access element using dereference operator
    cout << *it << " ";
}
```

Aynı şey, bir dizi döngüyle daha basit bir şekilde gerçekleştirilebilir:

```cpp
for (auto num : vec)
{
    // no deference operator
    cout << num << " ";
}
```

Yineleyicilerin beş kategorisi vardır. Güç artırma sırasıyla kategoriler şunlardır:

- **Çıktı**. *Çıkış Yineleyici* `X` , işlecini kullanarak bir sıra boyunca İleri doğru bir şekilde yineleyebilirsiniz `++` ve işlecini kullanarak bir öğeyi yalnızca bir kez yazabilir __`*`__ .

- **Giriş**. Bir *giriş Yineleyici* `X` , işlecini kullanarak bir dizi üzerinde ileri doğru bir şekilde yineleyebilirsiniz `++` ve işlecini kullanarak herhangi bir sayıda öğeyi okuyabilir `*` . Ve işleçlerini kullanarak giriş yineleyicilerini karşılaştırabilirsiniz `==` `!=` . Bir giriş yineleyicisinin herhangi bir kopyasını artırdıktan sonra, diğer kopyaların hiçbiri daha sonra güvenli bir şekilde karşılaştırılamaz, başvurulduktan veya artmaz.

- **İleri**. Bir *ileriye doğru yineleyici* `X` , + + işlecini kullanarak bir dizi üzerinde ileri doğru yineleyebilir ve işlecini kullanarak herhangi bir öğeyi okuyabilir veya const olmayan öğeleri yazabilir `*` . İşlecini kullanarak öğe üyelerine erişebilir `->` ve ve işleçlerini kullanarak ileriye doğru yineleyiciler karşılaştırabilirsiniz `==` `!=` . Bir ileri yineleyicisinin, her biri başvurusu kaldırılmış ve bağımsız olarak arttırılan birden çok kopyasını oluşturabilirsiniz. Herhangi bir kapsayıcıya başvuru olmadan başlatılan bir ileri Yineleyici, *null ileri Yineleyici*olarak adlandırılır. Null ileri yineleyiciler her zaman eşit olarak Karşılaştır.

- **Çift yönlü**. *Çift yönlü bir yineleyici* `X` , ileriye doğru bir yineleyicinin yerini alabilir. Bununla birlikte,, veya ' de olduğu gibi çift yönlü yineleyiciyi de azaledebilirsiniz `--X` `X--` `(V = *X--)` . Öğe üyelerine erişebilir ve çift yönlü yineleyiciler ileri yineleyiciler ile aynı şekilde karşılaştırabilirsiniz.

- **Rastgele erişim**. *Rastgele erişim Yineleyici* `X` , çift yönlü yineleyicinin yerini alabilir. Rastgele bir erişim yineleyicisi ile öğelere erişmek için indis işlecini kullanabilirsiniz `[]` . `+`, `-` `+=` Ve `-=` işleçlerini, belirtilen sayıda öğeyi ileri veya geri taşımak ve yineleyiciler arasındaki mesafeyi hesaplamak için kullanabilirsiniz. ,,,, Ve kullanarak çift yönlü yineleyiciler karşılaştırabilirsiniz `==` `!=` `<` `>` `<=` `>=` .

Tüm yineleyiciler atanabilir veya kopyalanabilir. Bunlar hafif nesneler olarak kabul edilir ve genellikle değere göre geçirilir ve başvuruya göre değil, döndürülür. Ayrıca, daha önce açıklanan işlemlerden hiçbirinin geçerli bir yineleyiciden gerçekleştirildiğinde özel durum oluşturabildiğini unutmayın.

Yineleyici kategorilerinin hiyerarşisi üç sıra göstererek özetlenebilir. Bir diziye salt yazılır erişim için aşağıdakilerden birini kullanabilirsiniz:

> Çıkış Yineleyici \
> -> ileri Yineleyici \
> -Çift yönlü yineleyiciyi > \
> -> Rastgele erişimli Yineleyici

Sağ ok, "değiştirilerek değiştirilebilir" anlamına gelir. Bir çıkış yineleyiciyi çağıran her bir algoritma, örneğin, bir ileri Yineleyici ile biraz çalışır, ancak başka bir *şekilde çalışmaz.*

Bir diziye salt okuma erişimi için aşağıdakilerden birini kullanabilirsiniz:

> giriş Yineleyici \
> -> ileri Yineleyici \
> -Çift yönlü yineleyiciyi > \
> -> Rastgele erişimli Yineleyici

Bu durumda, bir giriş yineleyicisi tüm kategorilerin en zayıf halini içerir.

Son olarak, bir diziye yönelik okuma/yazma erişimi için aşağıdakilerden birini kullanabilirsiniz:

> ileri Yineleyici \
> -Çift yönlü yineleyiciyi > \
> -> Rastgele erişimli Yineleyici

Bir nesne işaretçisi her zaman Rastgele erişimli bir yineleyici olarak görev yapabilir, bu sayede, yaptığı diziye uygun okuma/yazma erişimini destekliyorsa herhangi bir yineleyici kategorisi olarak görev yapabilir.

Bir nesne işaretçisi dışındaki bir yineleyici, `Iterator` özelleşmenin gerektirdiği üye türlerini de tanımlamalıdır `iterator_traits<Iterator>` . Bu gereksinimler `Iterator` , genel temel sınıf [yineleyiciden](../standard-library/iterator-struct.md)türeterek karşılandı.

Yineleyicilerin C++ standart kitaplığı 'ndaki kapsayıcılar ve algoritmalar tarafından nasıl kullanıldığını görmek için her Yineleyici kategorisinin taahhüt ve sınırlamalarını anlamak önemlidir.

> [!NOTE]
> Döngüler için Range-for döngüleri kullanarak yineleyiciler kullanmaktan kaçınabilirsiniz. Daha fazla bilgi için bkz. [Aralık tabanlı for deyimleri](../cpp/range-based-for-statement-cpp.md).

Microsoft C++ artık, kapsayıcının sınırları üzerine yazılmadığından emin olmak için, denetlenen yineleyiciler ve hata ayıklama yineleyicileri sunmaktadır. Daha fazla bilgi için bkz. [denetlenen yineleyiciler](../standard-library/checked-iterators.md) ve [hata ayıklama Yineleyici desteği](../standard-library/debug-iterator-support.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
