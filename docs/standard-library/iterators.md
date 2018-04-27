---
title: Yineleyiciler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- iterator conventions
- C++ Standard Library, iterator conventions
ms.assetid: 2f746be7-b37d-4bfc-bf05-be4336ca982f
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c1012add5e2a62110a8f10792a0ea2bb878dce2
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="iterators"></a>Yineleyiciler

Yineleyici C++ Standart Kitaplığı kapsayıcı öğelerinde üzerinden yineleme ve tek tek öğelere erişim sağlayan bir nesnedir. Öğeleri algoritmaları öğelerini standart bir şekilde kapsayıcı türü ile endişelenmeniz gerek kalmadan erişebilmesi için tüm yineleyiciler sağlayın C++ Standart Kitaplığı kapsayıcıları depolanır.

Üye ve genel işlevler begin() ve end() ve işleçler gibi açıkça gibi kullanılarak yineleyiciler kullanabilirsiniz ++ ve--ileriye veya geriye doğru taşımak için. Yineleyiciler örtük olarak bir aralık kullanabilirsiniz-döngü veya için (bazı yineleyici türleri) [] alt simge işleci.

C++ Standart Kitaplığı'nda, bir dizi veya aralığı başlangıcı ilk öğedir. Bir dizi veya aralığı sonu her zaman bir geçmiş son öğesi olarak tanımlanır. Genel işlevler başlayan ve belirtilen bir kapsayıcıya dönüş yineleyiciler bitmelidir. Bir kapsayıcıdaki tüm öğeler üzerinde tipik açık yineleyici döngü şöyle görünür:

```cpp
vector<int> vec{ 0,1,2,3,4 };
for (auto it = begin(vec);

it != end(vec);

it++)
{  // Access element using dereference operator
    cout <<*it <<" ";
}
```

Aynı şey bir aralık daha basit bir şekilde gerçekleştirilebilir-döngü için:

```cpp
for (auto num : vec)
 {  // no deference operator
    cout <<num <<" ";
 }
```

Yineleyiciler beş kategoriye ayrılır. Güç artan sırada kategorileri şunlardır:

- **Çıktı**. Çıktı yineleyici `X` kullanarak üzerinde bir dizi ilet yineleyebilirsiniz ++ işleç ve bir öğe, yalnızca bir kez kullanarak yazabilirsiniz * işleci.

- **Giriş**. Giriş yineleyici `X` kullanarak üzerinde bir dizi ilet yineleyebilirsiniz ++ işleç ve bir öğe kullanarak herhangi bir sayıda kez okuyabilirsiniz * işleci. Kullanarak giriş yineleyiciler karşılaştırabilirsiniz ++ ve! = işleç. Giriş yineleyici herhangi bir kopyasına Artır sonra diğer kopyaların hiçbiri güvenle, başvuru yapıldı veya artırılır bundan sonra karşılaştırılabilir.

- **İleri**. Bir iletme yineleyici `X` İleri dizisi kullanılarak üzerinden yineleme ++ işleci ve herhangi bir öğe okuma veya kullanarak herhangi bir sayıda kez const olmayan öğeler yazma * işleci. Kullanarak öğesi üyeleri erişebilir -> işleci ve == kullanarak İleri yineleyiciler karşılaştırın ve! = işleç. Her biri kullanılabilir başvuru yapıldı ve bağımsız olarak artan bir iletme yineleyici birden çok kopyasını yapabilirsiniz. Tüm kapsayıcı başvuru olmadan başlatılan bir iletme yineleyici null bir iletme yineleyici adı verilir. Null iletme yineleyiciler her zaman eşit karşılaştırın.

- Çift yönlü. Çift yönlü yineleyici `X` iletme yineleyici yer alabilir. Ancak aynı zamanda bir çift yönlü yineleyici de--azaltma`X`, `X`--, veya (`V` = *`X`--). Öğe üyelere erişmek ve iletme yineleyiciler aynı şekilde çift yönlü yineleyiciler karşılaştırın.

- **Rasgele erişim**. Rasgele erişim yineleyici `X` çift yönlü yineleyici yer alabilir. Rasgele erişim yineleyici ile kullanabileceğiniz [] için erişim öğeleri alt simge işleci. Kullanabileceğiniz +, -, ileriye veya geriye doğru belirtilen sayıda öğeyi taşımak ve yineleyiciler arasındaki uzaklığı hesaplamak için += ve-= işleç. Çift yönlü yineleyiciler kullanarak karşılaştırabilirsiniz ==,! =, \<, >, \<= ve > =.

Tüm yineleyiciler atanan veya kopyalanır. Bunlar Hafif nesneler olarak kabul edilir ve genellikle geçirilen ve başvuru değil tarafından döndürülen değer tarafından. Ayrıca, daha önce açıklanan işlemlerin hiçbiri üzerinde geçerli bir yineleyici gerçekleştirildiğinde bir özel durum olduğunu unutmayın.

Yineleyici kategori hiyerarşisi üç sıraları göstererek özetlenebilir. Salt yazılır erişimi için bir dizisini, herhangi birini kullanabilirsiniz:

> Yineleyici çıktı<br/>
> iletme yineleyici -><br/>
> çift yönlü yineleyici -><br/>
> rasgele erişim yineleyici -><br/>

Sağ ok "tarafından değiştirilebilir." anlamına gelir. Çıktı yineleyici sorunsuz şekilde bir iletme yineleyici ile Örneğin, çalışması gereken için çağıran herhangi bir algoritma ancak *değil* tersi.

Salt okunur erişim için bir dizisini, herhangi birini kullanabilirsiniz:

> Giriş yineleyici<br/>
> iletme yineleyici -><br/>
> çift yönlü yineleyici -><br/>
> rasgele erişim yineleyici -><br/>

Giriş yineleyici zayıf tüm kategorileri, bu durumda olur.

Son olarak, bir dizi için okuma/yazma erişimi için herhangi birini kullanabilirsiniz:

> iletme yineleyici<br/>
> çift yönlü yineleyici -><br/>
> rasgele erişim yineleyici -><br/>

Bunu atayan dizisi uygun okuma/yazma erişimi destekliyorsa yineleyici herhangi bir kategoriye hizmet verebilir şekilde bir nesne işaretçisi her zaman bir rastgele erişim yineleyici hizmet verebilir.

Yineleyici `Iterator` dışındaki bir nesnenin işaretçi ayrıca uzmanlık tarafından gerekli üye türleri tanımlamalıdır `iterator_traits<Iterator>`. Bu gereksinimleri türetme tarafından karşılanabilir Not `Iterator` ortak temel sınıfından [yineleyici](../standard-library/iterator-struct.md).

Her yineleyici kategori sınırlamaları ve öneriler yineleyiciler kapsayıcıları ve C++ Standart Kitaplığı'nda algoritmaları tarafından nasıl kullanıldığını görmek için anlamak önemlidir.

> [!NOTE]
> Yineleyiciler açıkça aralığı kullanarak önleyebilirsiniz-döngüler için. Daha fazla bilgi için bkz: [aralığı-based for deyimi](../cpp/range-based-for-statement-cpp.md).

Visual C++ işaretli yineleyiciler ve hata ayıklama yineleyiciler, kapsayıcı sınırları üzerine yazma emin olmak için şimdi sunar. Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md) ve [hata ayıklama yineleyici desteği](../standard-library/debug-iterator-support.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
