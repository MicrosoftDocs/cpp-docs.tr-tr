---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: shared_ptr örnekleri oluşturma ve kullanma'
title: 'Nasıl yapılır: shared_ptr örnekleri oluşturma ve kullanma'
ms.custom: how-to
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 7d6ebb73-fa0d-4b0b-a528-bf05de96518e
ms.openlocfilehash: b98a9a349f7f33805bd86c58e854b1d988733da2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221260"
---
# <a name="how-to-create-and-use-shared_ptr-instances"></a>Nasıl yapılır: shared_ptr örnekleri oluşturma ve kullanma

`shared_ptr`Bu tür, C++ standart kitaplığı 'nda bulunan ve bellek içindeki nesne ömrünü yönetmek için birden fazla sahibin sahip olabileceği senaryolar için tasarlanan akıllı bir işaretçidir. Başlattıktan sonra `shared_ptr` , onu kopyalayabilir, işlev bağımsız değişkenlerinde değere göre geçirebilir ve diğer `shared_ptr` örneklere atayabilirsiniz. Tüm örnekler aynı nesneyi işaret edip, her yeni `shared_ptr` eklendiğinde, kapsam dışına çıktığında veya sıfırlandığında, başvuru sayısını artıran ve azaltır bir "Denetim bloğuna" erişimi paylaşır. Başvuru sayısı sıfıra ulaştığında, denetim bloğu bellek kaynağını ve kendisini siler.

Aşağıdaki çizimde, `shared_ptr` bir bellek konumuna işaret eden birkaç örnek gösterilmektedir.

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

Mümkün olduğunda, [](../standard-library/memory-functions.md#make_shared) `shared_ptr` bellek kaynağı ilk kez oluşturulduğunda bir oluşturmak için make_shared işlevini kullanın. `make_shared` özel durum güvenlidir. Denetim bloğu ve kaynak için belleği ayırmak için aynı çağrıyı kullanır, bu da oluşturma ek yükünü azaltır. Kullanmıyorsanız `make_shared` , **`new`** oluşturucuyu geçirmeden önce nesneyi oluşturmak için açık bir ifade kullanmanız gerekir `shared_ptr` . Aşağıdaki örnek, yeni bir nesneyle birlikte bildirmek ve başlatmak için çeşitli yollar gösterir `shared_ptr` .

[!code-cpp[stl_smart_pointers#1](codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_1.cpp)]

## <a name="example-2"></a>Örnek 2

Aşağıdaki örnek, `shared_ptr` başka bir tarafından zaten ayrılmış olan bir nesnenin paylaşılan sahipliğini alan örneklerin nasıl bildirilemeyeceğini ve başlatılacağını gösterir `shared_ptr` . `sp2`Öğesinin başlatıldığını varsayın `shared_ptr` .

[!code-cpp[stl_smart_pointers#2](codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_2.cpp)]

## <a name="example-3"></a>Örnek 3

`shared_ptr` , öğeleri kopyalayabileceğiniz algoritmaları kullanırken C++ standart kitaplık kapsayıcılarında da yararlıdır. Öğeleri bir içinde sarabilir `shared_ptr` ve ardından, temel alınan belleğin, ihtiyacınız olduğu sürece geçerli olduğunu ve artık daha fazla kapsayıcıyla, diğer kapsayıcılara kopyalayabilirsiniz. Aşağıdaki örnek, `remove_copy_if` `shared_ptr` bir vektör içindeki örneklerde algoritmanın nasıl kullanılacağını gösterir.

[!code-cpp[stl_smart_pointers#4](codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_3.cpp)]

## <a name="example-4"></a>Örnek 4

`dynamic_pointer_cast`,, Ve ' `static_pointer_cast` `const_pointer_cast` a dönüştürmek için kullanabilirsiniz `shared_ptr` . Bu işlevler,, **`dynamic_cast`** **`static_cast`** ve **`const_cast`** işleçlerine benzer. Aşağıdaki örnek, temel sınıfların bir vektöründe her bir öğenin türetilmiş türünün nasıl test alınacağını gösterir `shared_ptr` ve ardından öğeleri kopyalayıp bunlarla ilgili bilgileri görüntüler.

[!code-cpp[stl_smart_pointers#5](codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_4.cpp)]

## <a name="example-5"></a>Örnek 5

`shared_ptr`Aşağıdaki yollarla bir diğer işleve geçiş yapabilirsiniz:

- `shared_ptr`Değere göre geçirin. Bu, kopya oluşturucusunu çağırır, başvuru sayısını artırır ve aranan bir sahip yapar. Bu işlemde, kaç nesne geçirdiğinize bağlı olarak önemli olabilecek küçük miktarda ek yük vardır `shared_ptr` . Çağıran ve çağrılan arasında örtük veya açık kod sözleşmesi, aranan kişinin bir sahip olmasını gerektirdiğinde bu seçeneği kullanın.

- `shared_ptr`Başvuruya veya const başvuruya göre geçirin. Bu durumda, başvuru sayısı artmaz ve arayan kapsam dışında olmadığı sürece çağrılan işaretçiye erişebilir. Ya da aranan, başvuruya göre bir oluşturup oluşturmaya karar verebilir `shared_ptr` ve paylaşılan bir sahip olabilir. Çağıranın aranan bilgisi olmadığında veya ne zaman geçitirsiniz `shared_ptr` ve performans nedenleriyle kopyalama işleminin oluşmasını önlemek istediğinizde bu seçeneği kullanın.

- Temel alınan işaretçiyi veya bir başvuruyu temel alınan nesneye geçirin. Bu, aranan nesnenin nesneyi kullanmasını sağlar, ancak sahipliğini paylaşmasına veya yaşam süresini genişletmenize izin vermez. Aranan ham işaretçiden bir oluşturursa `shared_ptr` , yeni, `shared_ptr` orijinalden bağımsızdır ve temel alınan kaynağı denetlemez. Çağıran ve aranan arasındaki sözleşme, çağıranın, yaşam süresinin sahipliğini koruduğunu açıkça belirttiğinde bu seçeneği kullanın `shared_ptr` .

- Nasıl geçireceğinize karar verirken `shared_ptr` , aranan kaynağın sahipliğini paylaşmak için gerekip gerekmediğini saptayın. "Owner", temel alınan kaynağı, ihtiyaç duyması gerektiği sürece etkin tutan bir nesne veya işlevdir. Çağıranın, çağrılan işaretçinin ömrünü (işlevin) ömrünü aşacak şekilde genişletebileceğinizin garantisi varsa, ilk seçeneğini kullanın. Aranan 'un yaşam süresini genişlettiğinden ve sonra başvuruya göre geçiş yapıp yapmadığından, bu dosyayı kopyalamasına izin verip vermediğini dikkate almanız gerekmez.

- Temel işaretçiye bir yardımcı işlev erişimi vermeniz gerekiyorsa ve yardımcı işlevin yalnızca işaretçiyi kullanacağı ve çağıran işlev döndürmeden önce döndürdüğünü biliyorsanız, bu işlevin temeldeki işaretçinin sahipliğini paylaşması gerekmez. Yalnızca çağıranın kullanım ömrü içinde işaretçiye erişmesi yeterlidir `shared_ptr` . Bu durumda, `shared_ptr` başvuruya göre iletmek veya ham işaretçiyi ya da temel alınan nesneye bir başvuruyu geçirmek güvenlidir. Bu şekilde geçirmek, küçük bir performans avantajı sağlar ve ayrıca programlama amacınızı ifade etmenize yardımcı olabilir.

- Bazen, örneğin `std::vector<shared_ptr<T>>` , bir `shared_ptr` lambda ifadesi gövdesine veya adlandırılmış işlev nesnesine geçirmeniz gerekebilir. Lambda veya işlev işaretçiyi depolamazsa, `shared_ptr` her öğe için kopya oluşturucuyu çağırmaktan kaçınmak için başvuruya göre geçirin.

## <a name="example-6"></a>Örnek 6

Aşağıdaki örnek, `shared_ptr` örneklerin sahip olduğu bellekte işaretçi karşılaştırmaları nasıl etkinleştireceğinizi gösteren çeşitli karşılaştırma işleçlerinin nasıl aşırı yükleneceğini gösterir `shared_ptr` .

[!code-cpp[stl_smart_pointers#3](codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_6.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Akıllı İşaretçiler (Modern C++)](smart-pointers-modern-cpp.md)
