---
description: 'Hakkında daha fazla bilgi edinin: D. Schedule yan tümcesi'
title: D. schedule yan tümcesi
ms.date: 01/22/2019
ms.assetid: bf3d8f51-ea05-4803-bf55-657c12e91efe
ms.openlocfilehash: bd1bb4f9a6c661205e2e647fc9e45d81903008c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342497"
---
# <a name="d-the-schedule-clause"></a>D. schedule yan tümcesi

Paralel bir bölgede en az bir engel vardır ve bunun sonunda daha fazla engelleri olabilir. Her bir engelte, takımın diğer üyelerinin son iş parçacığının gelmesi için beklemesi gerekir. Bu bekleme süresini en aza indirmek için, paylaşılan iş tüm iş parçacıklarının aynı anda yaklaşık olarak engelde gelmesi için dağıtılmalıdır. Bu paylaşılan çalışmalarından bazıları yapılar içinde yer alıyorsa `for` , `schedule` yan tümce bu amaçla kullanılabilir.

Aynı nesnelere tekrarlanmış başvurular olduğunda, bir yapı için zamanlama seçimi `for` birincil olarak bellek sisteminin özelliklerine göre belirlenebilir. Örneğin, önbelleğe alma ve boyut ve bellek erişim sürelerinin tek tek veya tek biçimli olup olmadığı. Bu tür konular, bazı iş parçacıklarının bazı Döngülerde görece daha az iş olmasına rağmen her bir iş parçacığının bir dizi döngü içinde her zaman sürekli olarak aynı öğe kümesine başvurmalarını tercih edebilir. Bu kurulum, `static` Tüm döngüler için aynı sınırlara sahip zamanlama kullanılarak yapılabilir. Aşağıdaki örnekte,, `k` zamanlama önemli değilse daha doğal olmasına rağmen, ikinci döngüde alt sınır olarak sıfır kullanılır.

```cpp
#pragma omp parallel
{
#pragma omp for schedule(static)
  for(i=0; i<n; i++)
    a[i] = work1(i);
#pragma omp for schedule(static)
  for(i=0; i<n; i++)
    if(i>=k) a[i] += work2(i);
}
```

Kalan örneklerde, bellek erişiminin baskın bir değerlendirme olmadığı varsayılır. Aksi belirtilmedikçe, tüm iş parçacıkları karşılaştırılabilir hesaplama kaynakları alır. Bu durumlarda, bir yapı için zamanlama seçimi, `for` en yakın önceki engeli ve kapsanan kapanış engeli ile bir yan tümce varsa en yakın yaklaşan engel arasında gerçekleştirilecek tüm paylaşılan çalışmaya bağlıdır `nowait` . Her zamanlama türü için, kısa bir örnek, bu zamanlama türünün en iyi seçim olma olasılığını gösterir. Her bir örnek için kısa bir tartışma aşağıda verilmiştir.

`static`Zamanlama, tek bir yapı içeren bir paralel bölge `for` olan ve her bir yineleme için aynı iş miktarını gerektiren bir paralel bölge olan en basit durum için de uygundur.

```cpp
#pragma omp parallel for schedule(static)
for(i=0; i<n; i++) {
  invariant_amount_of_work(i);
}
```

`static`Zamanlama, her bir iş parçacığının diğer iş parçacığıyla yaklaşık olarak aynı sayıda yinelemeyi aldığı ve her bir iş parçacığının kendisine atanan yinelemeleri bağımsız olarak belirleyebilen özelliklere göre belirlenir. Bu nedenle, çalışmayı dağıtmak için herhangi bir eşitleme gerekmez ve her bir yinelemenin aynı iş miktarı için gerekli olduğu varsayımıyla, tüm iş parçacıklarının aynı anda tamamlanmaları gerekir.

Bir *p* iş parçacığı ekibi için *tavan (n/p)* , *0 <= r < p* ile *n = p \* q-r* ' y i karşılayan, *q* tamsayı olmalıdır. `static`Bu örnek için zamanlamanın bir uygulanması, ilk *p-1* iş parçacığına *soru* -cevap yineleme ve son iş parçacığına *q-r* yinelemelerini atar.  Başka bir kabul edilebilir uygulama, ilk *p-r* iş parçacığına *q* yineleme ve kalan *r* iş parçacığı için *q-1* yinelemelerini atayacaktır. Bu örnekte, bir programın belirli bir uygulamanın ayrıntılarına dayanmaması gösterilmektedir.

`dynamic`Zamanlama `for` , yinelemeler, hatta tahmin edilemeyen, hatta tahmin edilemeyen iş miktarları gerektiren bir yapının olması için uygundur.

```cpp
#pragma omp parallel for schedule(dynamic)
  for(i=0; i<n; i++) {
    unpredictable_amount_of_work(i);
}
```

`dynamic`Zamanlama, iş parçacığının, son yinelemesini yürütmek için başka bir iş parçacığı kullandığından daha uzun süre boyunca engel olmadığı özelliği tarafından belirlenir. Bu gereksinim, her atamaya yönelik eşitlemeyle birlikte iş parçacıkları için her seferinde bir kez atanması gerektiği anlamına gelir. Eşitleme ek yükü, 1 ' *den büyük bir* en düşük öbek boyutu değeri olarak düşürüldüğünden azaltılabilir, bu sayede iş parçacıkları, *k* 'den az kalana kadar bir *kez atanır.* Bu, herhangi bir iş parçacığının son öbeğini (en fazla) *k* yinelemesi yürütmek için başka bir iş parçacığı kullandığından daha uzun süre beklememesini güvence altına alır.

`dynamic`İş parçacıkları, her yinelemede değişen miktarda iş ile aynı etkiye sahip olan değişen hesaplama kaynakları alıyorsa, zamanlama yararlı olabilir. Benzer şekilde, dinamik zamanlama aynı zamanda iş parçacıkları yapıyı farklı zamanlarda geldiğinde yararlı olabilir `for` , ancak bu durumda `guided` zamanlama tercih edilebilir.

`guided`Zamanlama, iş parçacıklarının `for` aynı iş miktarı hakkında gerekli olan her bir yineleme ile aynı zamanda farklı zamanlarda gelebileceği durum için uygundur. Örneğin, `for` yapının öncesinde bir veya daha fazla bölüm ya da `for` yan tümceleri olan yapılar olması durumunda bu durum oluşabilir `nowait` .

```cpp
#pragma omp parallel
{
  #pragma omp sections nowait
  {
    // ...
  }
  #pragma omp for schedule(guided)
  for(i=0; i<n; i++) {
    invariant_amount_of_work(i);
  }
}
```

Benzer şekilde `dynamic` , `guided` zamanlama, bir iş parçacığının, son yinelemeyi yürütmek için başka bir iş parçacığı aldığına veya bir *k* öbek boyutu belirtilmişse son *k* yinelemelerine engel olmasını garanti eder. Bu tür zamanlamalar arasında, `guided` zamanlama en az eşitleme gerektirdiğinden özelliği tarafından belirlenir. Öbek boyutu *k* için tipik bir uygulama, kullanılabilir ilk iş parçacığına *q = tavan (n/p)* yinelemelerini atar, *n* 'yi *n-q* ve *p \* k*'ın daha büyük bir öğesine ayarlar ve tüm yinelemeler atanıncaya kadar yinelenir.

En uygun zamanlamanın seçimi bu örneklerde olduğu kadar net olmadığı için, `runtime` zamanlama, programı değiştirmek ve yeniden derlemek zorunda kalmadan farklı zamanlamalar ve öbek boyutları denemek için uygundur. Ayrıca, programın uygulandığı giriş verilerinde en uygun zamanlamanın (bazı öngörülebilir bir şekilde) bağlı olduğu durumlarda da yararlı olabilir.

Farklı zamanlamalar arasındaki dengelerin bir örneğini görmek için, 1000 yinelemelerini sekiz iş parçacığı arasında paylaşmayı göz önünde bulundurun. Her yinelemede sabit bir iş miktarı olduğunu varsayın ve bu süreyi zaman birimi olarak kullanın.

Tüm iş parçacıkları aynı anda başladıysanız, `static` zamanlama yapının, eşitleme olmadan 125 birimlerinde yürütülmesine neden olur. Ancak, bir iş parçacığının 100 birimi geç olduğunu varsayalım. Ardından kalan yedi iş parçacığı, engelde 100 birim bekler ve tüm yapının yürütme süresi 225 olarak artar.

Hem hem de `dynamic` `guided` zamanlamaları, bir iş parçacığının engel üzerinde birden fazla birim beklemediğinden emin olduğundan, Gecikmeli iş parçacığı yapının yürütme sürelerinin yalnızca 138 birim kullanmasına neden olur, bu da eşitlemeden gecikmelerden daha fazla zaman arttırır. Bu gecikmeler göz ardı edilmemişse, eşitleme sayısının 1000 olması ve `dynamic` `guided` varsayılan öbek boyutunu varsayarak yalnızca 41 için olması önemli olur. 25 öbek boyutuyla `dynamic` ve `guided` her ikisi de 150 birimde ve ayrıca, sırasıyla yalnızca 40 ve 20 ' de olan gerekli eşitlemelerden her türlü gecikme ile tamamlanır.
