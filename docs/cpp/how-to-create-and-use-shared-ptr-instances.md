---
title: 'Nasıl yapılır: shared_ptr örnekleri oluşturma ve kullanma'
ms.custom: how-to
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 7d6ebb73-fa0d-4b0b-a528-bf05de96518e
ms.openlocfilehash: 9820e4cd2d1b981d82760fc1cea4e07c85792177
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245825"
---
# <a name="how-to-create-and-use-shared_ptr-instances"></a>Nasıl yapılır: shared_ptr örnekleri oluşturma ve kullanma

`shared_ptr` türü, C++ standart kitaplıkta bulunan ve bellek içindeki nesne ömrünü yönetmek için birden fazla sahibin sahip olabileceği senaryolar için tasarlanan akıllı bir işaretçidir. Bir `shared_ptr` başlattıktan sonra, onu kopyalayabilir, işlev bağımsız değişkenlerinde değere göre geçirebilir ve diğer `shared_ptr` örneklerine atayabilirsiniz. Tüm örnekler aynı nesneyi işaret edip, her yeni `shared_ptr` eklendiğinde, kapsam dışına çıktığında veya sıfırlandığında, başvuru sayısını artıran ve azaltır bir "Denetim bloğuna" erişimi paylaşır. Başvuru sayısı sıfıra ulaştığında, denetim bloğu bellek kaynağını ve kendisini siler.

Aşağıdaki çizimde, bir bellek konumuna işaret eden çeşitli `shared_ptr` örnekleri gösterilmektedir.

![Paylaşılan işaretçi diyagramı](media/shared_ptr.png "Paylaşılan işaretçi diyagramı")

## <a name="example-setup"></a>Örnek kurulum

Tüm bunları izleyen örneklerde, gerekli üst bilgileri eklediğiniz ve gerekli türleri burada gösterildiği gibi bildirdiniz:

```cpp
// shared_ptr-examples.cpp
// The following examples assume these declarations:
#include <algorithm>
#include <iostream>
#include <memory>
#include <string>
#include <vector>

struct MediaAsset
{
    virtual ~MediaAsset() = default; // make it polymorphic
};

struct Song : public MediaAsset
{
    std::wstring artist;
    std::wstring title;
    Song(const std::wstring& artist_, const std::wstring& title_) :
        artist{ artist_ }, title{ title_ } {}
};

struct Photo : public MediaAsset
{
    std::wstring date;
    std::wstring location;
    std::wstring subject;
    Photo(
        const std::wstring& date_,
        const std::wstring& location_,
        const std::wstring& subject_) :
        date{ date_ }, location{ location_ }, subject{ subject_ } {}
};

using namespace std;

int main()
{
    // The examples go here, in order:
    // Example 1
    // Example 2
    // Example 3
    // Example 4
    // Example 6
}
```

## <a name="example-1"></a>Örnek 1

Mümkün olduğunda, bellek kaynağı ilk kez oluşturulduğunda bir `shared_ptr` oluşturmak için [make_shared](../standard-library/memory-functions.md#make_shared) işlevini kullanın. `make_shared` özel durum güvenlidir. Denetim bloğu ve kaynak için belleği ayırmak için aynı çağrıyı kullanır, bu da oluşturma ek yükünü azaltır. `make_shared`kullanmıyorsanız, nesneyi `shared_ptr` oluşturucusuna geçirmeden önce oluşturmak için açık bir `new` ifadesi kullanmanız gerekir. Aşağıdaki örnek, `shared_ptr` yeni bir nesneyle birlikte bildirmek ve başlatmak için çeşitli yollar gösterir.

[!code-cpp[stl_smart_pointers#1](codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_1.cpp)]

## <a name="example-2"></a>Örnek 2

Aşağıdaki örnek, başka bir `shared_ptr`tarafından zaten ayrılmış olan bir nesnenin paylaşılan sahipliğini alan `shared_ptr` örneklerinin nasıl bildirilemeyeceğini ve başlatılacağını gösterir. `sp2` başlatılmış bir `shared_ptr`olduğunu varsayalım.

[!code-cpp[stl_smart_pointers#2](codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_2.cpp)]

## <a name="example-3"></a>Örnek 3

Ayrıca, öğeleri kopyalayabileceğiniz C++ algoritmaları kullanırken standart kitaplık kapsayıcılarında da yardımcı `shared_ptr`. Öğeleri bir `shared_ptr`sarabilir ve daha sonra, temel alınan belleğin, ihtiyacınız olduğu sürece geçerli olduğunu ve artık hiç olmadığını anlamak için başka kapsayıcılara kopyalayabilirsiniz. Aşağıdaki örnek, Vektördeki `shared_ptr` örneklerde `remove_copy_if` algoritmasının nasıl kullanılacağını gösterir.

[!code-cpp[stl_smart_pointers#4](codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_3.cpp)]

## <a name="example-4"></a>Örnek 4

`shared_ptr`dönüştürmek için `dynamic_pointer_cast`, `static_pointer_cast`ve `const_pointer_cast` kullanabilirsiniz. Bu işlevler `dynamic_cast`, `static_cast`ve `const_cast` işleçlerine benzer. Aşağıdaki örnek, her öğenin türetilmiş türünün temel sınıfların `shared_ptr` vektöründe nasıl test alınacağını gösterir ve ardından öğeleri kopyalayıp bunlarla ilgili bilgileri görüntüler.

[!code-cpp[stl_smart_pointers#5](codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_4.cpp)]

## <a name="example-5"></a>Örnek 5

Aşağıdaki yollarla `shared_ptr` başka bir işleve geçirebilirsiniz:

- `shared_ptr` değere göre geçirin. Bu, kopya oluşturucusunu çağırır, başvuru sayısını artırır ve aranan bir sahip yapar. Bu işlemde çok sayıda `shared_ptr` nesne sayısına bağlı olarak önemli olabilecek küçük bir ek yük vardır. Çağıran ve çağrılan arasında örtük veya açık kod sözleşmesi, aranan kişinin bir sahip olmasını gerektirdiğinde bu seçeneği kullanın.

- `shared_ptr` başvuruya veya const başvuruya göre geçirin. Bu durumda, başvuru sayısı artmaz ve arayan kapsam dışında olmadığı sürece çağrılan işaretçiye erişebilir. Ya da aranan, başvuruya göre bir `shared_ptr` oluşturmaya ve paylaşılan bir sahip olmaya karar verebilir. Çağıranın aranan bilgisi olmadığında veya bir `shared_ptr` iletmeniz gerektiğinde ve performans nedenleriyle kopyalama işlemini önlemek istediğinizde bu seçeneği kullanın.

- Temel alınan işaretçiyi veya bir başvuruyu temel alınan nesneye geçirin. Bu, aranan nesnenin nesneyi kullanmasını sağlar, ancak sahipliğini paylaşmasına veya yaşam süresini genişletmenize izin vermez. Çağrılan, ham işaretçiden bir `shared_ptr` oluşturursa, yeni `shared_ptr` orijinalden bağımsızdır ve temel alınan kaynağı denetlemez. Çağıran ve aranan arasındaki sözleşme, çağıranın `shared_ptr` yaşam süresinin sahipliğini koruduğunu açıkça belirttiğinde bu seçeneği kullanın.

- `shared_ptr`nasıl geçireceğinize karar verirken, aranan kaynağın sahipliğini paylaşmak için gerekip gerekmediğini saptayın. "Owner", temel alınan kaynağı, ihtiyaç duyması gerektiği sürece etkin tutan bir nesne veya işlevdir. Çağıranın, çağrılan işaretçinin ömrünü (işlevin) ömrünü aşacak şekilde genişletebileceğinizin garantisi varsa, ilk seçeneğini kullanın. Aranan 'un yaşam süresini genişlettiğinden ve sonra başvuruya göre geçiş yapıp yapmadığından, bu dosyayı kopyalamasına izin verip vermediğini dikkate almanız gerekmez.

- Temel işaretçiye bir yardımcı işlev erişimi vermeniz gerekiyorsa ve yardımcı işlevin yalnızca işaretçiyi kullanacağı ve çağıran işlev döndürmeden önce döndürdüğünü biliyorsanız, bu işlevin temeldeki işaretçinin sahipliğini paylaşması gerekmez. Yalnızca çağrı yapanın `shared_ptr`ömrü içinde işaretçiye erişmesi yeterlidir. Bu durumda, `shared_ptr` başvuruya göre geçirmek veya ham işaretçiyi veya temel alınan nesneye bir başvuruyu geçirmek güvenlidir. Bu şekilde geçirmek, küçük bir performans avantajı sağlar ve ayrıca programlama amacınızı ifade etmenize yardımcı olabilir.

- Bazen bir `std::vector<shared_ptr<T>>`Örneğin, her bir `shared_ptr` bir lambda ifadesi gövdesine veya adlandırılmış işlev nesnesine geçirmeniz gerekebilir. Lambda veya işlev işaretçiyi depolamazsa, her öğe için kopya oluşturucuyu çağırmaktan kaçınmak için `shared_ptr` başvuruya göre geçirin.

## <a name="example-6"></a>Örnek 6

Aşağıdaki örnek, `shared_ptr` örneklerine ait olan bellekte işaretçi karşılaştırmaları sağlamak için `shared_ptr` çeşitli karşılaştırma işleçlerini nasıl aşırı yüklediğine gösterir.

[!code-cpp[stl_smart_pointers#3](codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_6.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Akıllı İşaretçiler (Modern C++)](smart-pointers-modern-cpp.md)
