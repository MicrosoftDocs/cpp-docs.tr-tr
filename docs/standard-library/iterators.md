---
title: Yineleyiciler
ms.date: 11/04/2016
helpviewer_keywords:
- iterator conventions
- C++ Standard Library, iterator conventions
ms.assetid: 2f746be7-b37d-4bfc-bf05-be4336ca982f
ms.openlocfilehash: cf1f519521d86f2b7782fb93ed3b4aca4ecd5b24
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643449"
---
# <a name="iterators"></a>Yineleyiciler

Bir yineleyicinin bir C++ Standart Kitaplığı kapsayıcı öğeler üzerinden yineleme yapma ve tek tek öğelere erişim sağlayan bir nesnedir. Öğeleri algoritmaları öğeleri standart bir biçimde kapsayıcı türü ile merak gerek kalmadan erişebilmesi için tüm yineleyiciler sağlayan C++ Standart Kitaplığı kapsayıcıları depolanır.

Yineleyiciler açıkça üyesi ve genel işlevler gibi kullanarak kullanabileceğiniz `begin()` ve `end()` ve işleçler gibi **++** ve **--** ilerlemek için veya Geriye dönük. Yineleyiciler örtük olarak bir aralık kullanabilirsiniz-(bazı yineleyici türleri için) veya döngü için alt simge işleci  **\[]**.

C++ Standart Kitaplığı dizisi veya aralık başına ilk öğesidir. Dizisi veya aralığın sonu, her zaman son öğeden bir öncekine olarak tanımlanır. Genel işlevler `begin` ve `end` belirtilen kapsayıcıya yineleyiciler döndürür. Bir kapsayıcıdaki tüm öğeleri tipik açık yineleyici döngüsü şöyle görünür:

```cpp
vector<int> vec{ 0,1,2,3,4 };
for (auto it = begin(vec); it != end(vec); it++)
{
    // Access element using dereference operator
    cout << *it << " ";
}
```

Aynı şeyi daha basit bir aralık gerçekleştirilebilir-for döngüsü:

```cpp
for (auto num : vec)
{
    // no deference operator
    cout << num << " ";
}
```

Yineleyicilerin beş kategorisi vardır. Güç artan sırada kategorileri şunlardır:

- **Çıkış**. Bir *çıkış yineleyici* `X` kullanarak bir dizi üzerinde İleri yineleyebilirsiniz **++** işleci ve kullanarak bir öğe yalnızca bir kez yazabilirsiniz **&ast;** işleci.

- **Giriş**. Bir *giriş yineleyici* `X` kullanarak bir dizi üzerinde İleri yineleyebilirsiniz ++ işleç ve bir öğe herhangi sayıda kullanarak okuyabilir **&ast;** işleci. Giriş yineleyiciler kullanarak karşılaştırabilirsiniz **++** ve **! =** işleçleri. Herhangi bir giriş yineleyici kopyasını artırmanız sonra diğer kopyaların hiçbiri güvenli bir şekilde, başvurusu kaldırılmış veya artan bundan sonra karşılaştırılabilir.

- **İleri**. A *ileriye doğru yineleyici* `X` İleri dizisi kullanılarak üzerinden yineleme ++ işleci ve herhangi bir öğeyi okuyabilen veya sabit olmayan öğeleri kullanarak herhangi bir sayıda kez yazma **&ast;** işleci. Öğe üyeleri kullanarak erişebileceğiniz **->** işleci ve karşılaştırma İleri yineleyiciler kullanılarak **==** ve **! =** işleçleri. Her biri kullanılabilir başvurusu ve bağımsız olarak artan bir ileriye doğru yineleyici birden çok kopyasını yapabilirsiniz. Tüm kapsayıcı başvuru adlı olmadan başlatılır ileri doğru yineleyici bir *null ileriye doğru yineleyici*. Null İleri yineleyiciler her zaman eşit karşılaştırın.

- **Çift yönlü**. A *çift yönlü yineleyici* `X` ileriye doğru yineleyici yerini alabilir. Ancak ayrıca çift yönlü bir yineleyici gibi azaltma kullanabileceği `--X`, `X--`, veya `(V = *X--)`. Öğe üyelere erişmek ve çift yönlü yineleyiciler ileriye doğru Yineleyicilerin aynı şekilde karşılaştırın.

- **Rastgele erişim**. A *rastgele erişim yineleyicisini* `X` çift yönlü bir yineleyici yerini alabilir. Alt simge işleci kullanabileceğiniz bir rastgele erişim yineleyici ile  **\[]** öğelere erişim. Kullanabileceğiniz **+**, **-**, **+=** ve **-=** taşımak işleçleri ileriye veya geriye doğru öğelerin ve yineleyici arasındaki uzaklığı hesaplamak için belirtilen bir sayı. Çift yönlü yineleyiciler kullanarak karşılaştırabilirsiniz **==**, **! =**, **\<**, **>**, **\< =**, ve **>=**.

Tüm yineleyiciler atanan veya kopyalanır. Bunlar basit nesneler olarak kabul edilir ve genellikle geçirilen ve başvuruya göre değil değere göre döndürdü. Ayrıca, daha önce açıklanan işlemlerin hiçbiri üzerinde geçerli bir yineleyici gerçekleştirildiğinde bir özel durum oluşturabilecek unutmayın.

Yineleyici kategori hiyerarşisi üç dizileri göstererek özetlenebilir. Bir diziye salt yazılır erişim için herhangi birini kullanabilirsiniz:

> Çıkış yineleyici<br/>
> ileriye doğru yineleyici -><br/>
> çift yönlü yineleyici -><br/>
> rastgele erişim yineleyicisini -><br/>

Sağ ok "tarafından değiştirilebilir." anlamına gelir. Çıkış yineleyici güzelce ileriye doğru yineleyici ile Örneğin, iş, çağıran herhangi bir algoritma ancak *değil* güvenmelidir.

Bir diziye salt okunur erişim için herhangi birini kullanabilirsiniz:

> Giriş yineleyici<br/>
> ileriye doğru yineleyici -><br/>
> çift yönlü yineleyici -><br/>
> rastgele erişim yineleyicisini -><br/>

Bir giriş yineleyici zayıf tüm kategoriler, bu durumda olur.

Son olarak, bir dizi için okuma/yazma erişimi için herhangi birini kullanabilirsiniz:

> ileriye doğru yineleyici<br/>
> çift yönlü yineleyici -><br/>
> rastgele erişim yineleyicisini -><br/>

Uygun okuma/yazma erişimi, atayan dizisine destekliyorsa, yineleyici herhangi bir kategori sunabilmeniz için bir nesne işaretçisi her zaman bir rastgele erişim yineleyici hizmet verebilir.

Bir yineleyici `Iterator` dışındaki bir nesnenin uzmanlık tarafından gerekli üye türleri de işaretçi tanımlamalıdır `iterator_traits<Iterator>`. Bu gereksinimleri türetilerek karşılanabiliyorsa unutmayın `Iterator` genel temel sınıftan [yineleyici](../standard-library/iterator-struct.md).

Gösterir ve her bir yineleyici kategori sınırlamaları yineleyiciler kapsayıcılar ve C++ Standart Kitaplığı algoritmaları tarafından nasıl kullanıldığını görmek için anlamak önemlidir.

> [!NOTE]
> Yineleyicilerin aralığı kullanarak kullanarak açıkça kaçınabilirsiniz-döngüler için. Daha fazla bilgi için [Range-based for deyimi](../cpp/range-based-for-statement-cpp.md).

Visual C++ artık işaretli yineleyiciler ve hata ayıklama yineleyiciler, kapsayıcınızın sınırlarının üzerine değil emin olmak için de sunar. Daha fazla bilgi için [Checked Iterators](../standard-library/checked-iterators.md) ve [Debug Iterator Support](../standard-library/debug-iterator-support.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
