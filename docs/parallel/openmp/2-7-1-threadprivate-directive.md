---
title: 2.7.1 threadprivate Yönergesi
ms.date: 11/04/2016
ms.assetid: 08e0b70f-5359-4607-b0ca-38c2d570d7b3
ms.openlocfilehash: 0ba5ea4892d70458f0f63bcb5b92968b36235273
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647011"
---
# <a name="271-threadprivate-directive"></a>2.7.1 threadprivate Yönergesi

`threadprivate` Yönergesi yapar adlandırılmış dosya kapsam, ad alanı kapsamında veya belirtilen blok kapsamı statik değişkenler *değişken listesi* özel bir iş parçacığına. *değişken listesi* tamamlanmamış bir türleri olmadığı değişkenlerin virgülle ayrılmış listesidir. Söz dizimi `threadprivate` yönerge aşağıdaki gibidir:

```
#pragma omp threadprivate(variable-list) new-line
```

Her bir kopyasını bir `threadprivate` değişkeni başlatılır bir kez bu kopyayı olan ilk başvurunun önce program ve her zamanki şekilde belirtilmeyen bir noktada (yani, ana kopyayı programının bir seri yürütme başlatılması gibi). Bir nesnenin açık bir Başlatıcısı içinde başvuruluyorsa unutmayın bir `threadprivate` değişkenin bir kopyası olan ilk başvurunun önce değişken ve nesnenin değeri değiştirildiğinde, ardından davranıştır belirtilmemiş.

Herhangi bir özel değişken ile başka bir iş parçacığının kopyasını bir iş parçacığı başvurmamalıdır gibi bir `threadprivate` nesne. Seri bölgelerde ve programın ana bölge sırasında başvuruları ana iş parçacığının Kopyala nesnesinin olur.

İlk paralel bölgenin yürütüldükten sonra verileri `threadprivate` nesneleri yalnızca dinamik mekanizması iş parçacıkları, devre dışı bırakıldı ve iş parçacığı sayısı için tüm paralel bölgeleri değişmeden kalır kalıcı hale getirmek için garantisi.

Kısıtlamaları `threadprivate` yönerge aşağıdaki gibidir:

- A `threadprivate` yönergesi dosya kapsam veya isim uzayı kapsam değişkenleri için herhangi bir tanım veya bildirimi dışında görünmelidir ve tüm başvuruları herhangi bir değişken, listesinde sözcüksel olarak gelmelidir.

- Her bir değişken *değişken listesi* , bir `threadprivate` yönergesi dosya veya ad alanı kapsamında bir Değişken bildiriminde sözcüksel olarak yönergesi önündeki dosya veya ad alanı kapsamında başvurmalıdır.

- A `threadprivate` blok kapsamı statik değişkenler yönergesi bir değişkenin kapsamını ve iç içe kapsam içinde değil görünmesi gerekir. Yönergesi, tüm başvuruları herhangi bir değişken sözcüksel olarak kendi listesinde gelmelidir.

- Her bir değişken *değişken listesi* , bir `threadprivate` yönergesi blok kapsamında aynı kapsamda yönergesi sözcüksel olarak önce gelen bir Değişken bildiriminde başvurmalıdır. Değişken bildirimi statik depolama sınıfı tanımlayıcısı kullanmanız gerekir.

- Bir değişken belirtilmişse bir `threadprivate` bir çeviri birimindeki yönergesi içinde belirtilmelidir bir `threadprivate` bunu bildirilen her çeviri biriminde yönergesi.

- A `threadprivate` değişkeni dışında herhangi bir yan tümcesinde değil görünmelidir `copyin`, `copyprivate`, `schedule`, `num_threads`, veya **varsa** yan tümcesi.

- Adresini bir `threadprivate` değişkenin adresi sabit değil.

- A `threadprivate` değişken tamamlanmamış bir türü veya bir başvuru türü değil olmalıdır.

- A `threadprivate` açık bir başlatıcı ile bildirilirse, değişken POD harici sınıf türünde bir erişilebilir, açık bir kopya Oluşturucu olması gerekir.

Aşağıdaki örnek nasıl, bir başlatıcı içinde görüntülenen bir değişken değiştirme belirtilmeyen davranışlara neden olabilir ve ayrıca bir yardımcı nesnesi ve bir kopya Oluşturucusu kullanarak bu sorunu önlemek nasıl gösterir.

```
int x = 1;
T a(x);
const T b_aux(x); /* Capture value of x = 1 */
T b(b_aux);
#pragma omp threadprivate(a, b)

void f(int n) {
   x++;
   #pragma omp parallel for
   /* In each thread:
   * Object a is constructed from x (with value 1 or 2?)
   * Object b is copy-constructed from b_aux
   */
   for (int i=0; i<n; i++) {
      g(a, b); /* Value of a is unspecified. */
   }
}
```

## <a name="cross-references"></a>Başvuruları çapraz:

- Dinamik dizileri gör [bölümü 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39.

- `OMP_DYNAMIC` ortam değişkeni, bkz: [bölümü 4.3](../../parallel/openmp/4-3-omp-dynamic.md) 49 sayfasında.