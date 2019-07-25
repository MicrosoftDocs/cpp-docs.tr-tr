---
title: Yineleyiciler
ms.date: 11/04/2016
helpviewer_keywords:
- iterator conventions
- C++ Standard Library, iterator conventions
ms.assetid: 2f746be7-b37d-4bfc-bf05-be4336ca982f
ms.openlocfilehash: ec23cbea63bc6884a361600362fcf0061e927ca6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449957"
---
# <a name="iterators"></a>Yineleyiciler

Yineleyici bir C++ standart kitaplık kapsayıcısındaki öğeleri yinelemek ve tek tek öğelere erişim sağlamak için bir nesnedir. Standart C++ kitaplık kapsayıcıları, algoritmaların öğelerine, öğelerin depolandığı kapsayıcı türüyle ilgilenmeden bir standart şekilde erişmelerini sağlamak için yineleyiciler sağlar.

Yineleyiciler, `begin()` ve `end()` gibi nesneler ve genel işlevleri kullanarak, ve gibi işleçler **++** **--** ve ileri veya geri taşımak için kullanabilirsiniz. Yineleyicilerin bir for döngüsü veya (bazı yineleyici türleri için) alt  **\[simge işleci ile**örtülü olarak de kullanabilirsiniz.

C++ Standart kitaplıkta, bir sıranın veya aralığın başlangıcı ilk öğedir. Bir sıranın veya aralığın sonu her zaman son öğeden bir geçmiş olarak tanımlanır. Genel işlevler `begin` ve `end` yineleyiciler belirtilen kapsayıcıya döndürülür. Bir kapsayıcıdaki tüm öğeler üzerinde tipik açık Yineleyici döngüsü şöyle görünür:

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

- **Çıktı**. *Çıkış Yineleyici* `X` , **++** işlecini kullanarak bir sıra boyunca İleri doğru bir şekilde yineleyebilirsiniz ve __\*__ işlecini kullanarak bir öğeyi yalnızca bir kez yazabilir.

- **Giriş**. Bir *giriş Yineleyici* `X` , + + işlecini kullanarak bir dizi üzerinde ileri doğru bir şekilde yineleyebilirsiniz ve **&ast;** işlecini kullanarak herhangi bir sayıda öğeyi okuyabilir. **++** Ve **! =** işleçlerini kullanarak giriş yineleyicilerini karşılaştırabilirsiniz. Bir giriş yineleyicisinin herhangi bir kopyasını artırdıktan sonra, diğer kopyaların hiçbiri güvenli bir şekilde karşılaştırılamaz, başvurulduktan veya artmaz.

- **İleri**. Bir *ileriye doğru yineleyici* `X` , + + işlecini kullanarak bir dizi üzerinde ileri doğru yineleyebilir ve **&ast;** işlecini kullanarak herhangi bir öğeyi okuyabilir veya const olmayan öğeleri yazabilir. **->** İşlecini kullanarak öğe üyelerine erişebilir ve **==** ve **! =** işleçlerini kullanarak ileri yineleyicileri karşılaştırın. Bir ileri yineleyicisinin, her biri başvurusu kaldırılmış ve bağımsız olarak arttırılan birden çok kopyasını oluşturabilirsiniz. Herhangi bir kapsayıcıya başvuru olmadan başlatılan bir ileri Yineleyici, *null ileri Yineleyici*olarak adlandırılır. Null ileri yineleyiciler her zaman eşit olarak Karşılaştır.

- **Çift yönlü**. *Çift yönlü bir yineleyici* `X` , ileriye doğru bir yineleyicinin yerini alabilir. Bununla birlikte,, veya `--X` `(V = *X--)`' de `X--`olduğu gibi çift yönlü yineleyiciyi de azaledebilirsiniz. Öğe üyelerine erişebilir ve çift yönlü yineleyiciler ileri yineleyiciler ile aynı şekilde karşılaştırabilirsiniz.

- **Rastgele erişim**. *Rastgele erişim Yineleyici* `X` , çift yönlü yineleyicinin yerini alabilir. Rastgele bir erişim yineleyicisi ile, öğelere  **\[erişmek için '** alt simge işlecini kullanabilirsiniz. **+** **,-** Ve **işleçlerini,belirtilensayıdaöğeyiileriveyageritaşımakveyineleyicilerarasındakimesafeyihesaplamakiçinkullanabilirsiniz.-=** **+=** , **==** **!** **\<** **=, ,,\<Ve kullanarak çift yönlü yineleyiciler karşılaştırabilirsiniz. =**  **>** **>=**

Tüm yineleyiciler atanabilir veya kopyalanabilir. Bunlar, hafif nesneler olarak kabul edilir ve genellikle, başvuruya göre değil, değer tarafından geçirilir ve döndürülür. Ayrıca, daha önce açıklanan işlemlerden hiçbirinin geçerli bir yineleyiciden gerçekleştirildiğinde özel durum oluşturabildiğini unutmayın.

Yineleyici kategorilerinin hiyerarşisi üç sıra göstererek özetlenebilir. Bir diziye salt yazılır erişim için aşağıdakilerden birini kullanabilirsiniz:

> Çıkış Yineleyici \
> -> ileri Yineleyici \
> -Çift yönlü yineleyiciyi > \
> -> Rastgele erişimli Yineleyici

Sağ ok, "değiştirilerek değiştirilebilir" anlamına gelir. Bir çıkış yineleyiciyi çağıran her bir algoritma, örneğin, bir ileri Yineleyici ile biraz çalışır *, ancak başka* bir şekilde çalışmaz.

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

Bir nesne `Iterator` işaretçisi dışındaki bir yineleyici, özelleşmenin `iterator_traits<Iterator>`gerektirdiği üye türlerini de tanımlamalıdır. Bu gereksinimlerin, genel temel sınıf `Iterator` [yineleyiciden](../standard-library/iterator-struct.md)türeterek karşılanabileceği unutulmamalıdır.

Yineleyicilerin C++ standart kitaplıktaki kapsayıcılar ve algoritmalar tarafından nasıl kullanıldığını görmek için her Yineleyici kategorisinin taahhüt ve sınırlamalarını anlamak önemlidir.

> [!NOTE]
> Döngüler için Range-for döngüleri kullanarak yineleyiciler kullanmaktan kaçınabilirsiniz. Daha fazla bilgi için bkz. [Aralık tabanlı for deyimleri](../cpp/range-based-for-statement-cpp.md).

Microsoft C++ artık, kapsayıcının sınırları üzerine yazılmadığından emin olmak için, denetlenen yineleyiciler ve hata ayıklama yineleyicileri sunmaktadır. Daha fazla bilgi için bkz. [denetlenen yineleyiciler](../standard-library/checked-iterators.md) ve [hata ayıklama Yineleyici desteği](../standard-library/debug-iterator-support.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++Standart kitaplık başvurusu](../standard-library/cpp-standard-library-reference.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
