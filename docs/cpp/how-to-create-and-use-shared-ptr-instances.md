---
title: 'Nasıl yapılır: Shared_ptr örnekleri oluşturma ve kullanma'
ms.custom: how-to
ms.date: 05/22/2019
ms.topic: conceptual
ms.assetid: 7d6ebb73-fa0d-4b0b-a528-bf05de96518e
ms.openlocfilehash: 4e7d63840f60c00f97b02825965cc247cddc38fd
ms.sourcegitcommit: bde3279f70432f819018df74923a8bb895636f81
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66174805"
---
# <a name="how-to-create-and-use-sharedptr-instances"></a>Nasıl yapılır: Shared_ptr örnekleri oluşturma ve kullanma

`shared_ptr` Senaryoları, birden fazla sahibi gerekebilir bellekteki nesnenin ömrünü yönetmek için tasarlanan C++ Standart Kitaplığı'nda bir akıllı işaretçi türüdür. Başlatın, sonra bir `shared_ptr` kopyalayın, değer tarafından işlev bağımsız değişkenleri geçirme ve diğer atamak `shared_ptr` örnekleri. Tüm örnekleri aynı nesneye'nın üzerine gelin, yeni bir başvuru sayısı paylaşım erişimi için bir "artırır denetim bloğu" ve azaltır `shared_ptr` eklenir, kapsamın dışına çıkıncaya veya sıfırlanır. Başvuru sayısı sıfır ulaştığında, denetim bloğu bellek kaynağı ve kendisini siler.

Aşağıda birkaç gösterilmiştir `shared_ptr` bir bellek konumuna işaret örnekleri.

![Paylaşılan işaretçi diyagramı](../cpp/media/shared_ptr.png "paylaşılan işaretçi diyagramı")

## <a name="example-setup"></a>Örnek kurulumu

Tüm aşağıdaki örneklerde, dahil edilen gerekli üst bilgileri ve gerekli türleri bildirilen burada gösterildiği gibi varsayılır:

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

Mümkün olduğunda kullanın [make_shared](../standard-library/memory-functions.md#make_shared) oluşturmak için işlevi bir `shared_ptr` bellek kaynağı ilk kez oluşturulduğunda. `make_shared` özel durum-güvenli olmayandır. Aynı çağrı denetim bloğu ve oluşturma ek yükü azaltır kaynak için bellek ayırmak için kullanır. Kullanmazsanız `make_shared`, açık bir kullanmak zorunda sonra `new` kendisine geçirmeden önce nesneyi oluşturmak için ifade `shared_ptr` Oluşturucusu. Aşağıdaki örnek, bildirmek ve başlatmak için çeşitli yollar gösterir. bir `shared_ptr` birlikte yeni bir nesne.

[!code-cpp[stl_smart_pointers#1](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_1.cpp)]

## <a name="example-2"></a>Örnek 2

Aşağıdaki örnek, bildirmek ve başlatmak gösterilmektedir `shared_ptr` uygulamanız örnekler paylaşılan bir başkası tarafından zaten ayrılmış bir nesne sahipliğini `shared_ptr`. Varsayımında `sp2` başlatılan bir olan `shared_ptr`.

[!code-cpp[stl_smart_pointers#2](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_2.cpp)]

## <a name="example-3"></a>Örnek 3

`shared_ptr` içinde da yararlıdır C++ öğeleri kopyala algoritmaları kullanırken standart kitaplığı kapsayıcıları. Öğeleri kaydırılabilir bir `shared_ptr`ve diğer temel alınan bellek ihtiyacınız olduğu sürece geçerli ve artık olduğunu anlama kapsayıcılarla kopyalayın. Aşağıdaki örnek nasıl kullanılacağını gösterir `replace_copy_if` algoritmasına `shared_ptr` vektördeki örnekleri.

[!code-cpp[stl_smart_pointers#4](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_3.cpp)]

## <a name="example-4"></a>Örnek 4

Kullanabileceğiniz `dynamic_pointer_cast`, `static_pointer_cast`, ve `const_pointer_cast` dönüştürülecek bir `shared_ptr`. Bu işlevler benzer `dynamic_cast`, `static_cast`, ve `const_cast` işleçleri. Aşağıdaki örnek, bir vektör her öğenin türetilmiş tür test etme gösterir `shared_ptr` , temel sınıflar, öğeleri kopyalayın ve bunlarla ilgili bilgileri görüntüler.

[!code-cpp[stl_smart_pointers#5](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_4.cpp)]

## <a name="example-5"></a>Örnek 5

Geçirebilirsiniz bir `shared_ptr` aşağıdaki yollarla başka bir işleve:

- Geçirmek `shared_ptr` değere göre. Bu kopya oluşturucusunu çağırır, başvuru sayısını artırır ve çağrılan sahibi yapar. Az miktarda bir kaç bağlı olarak önemli bu işlem ek yükü var. `shared_ptr` geçirme nesneleri. Çağıran ve çağrılan arasında örtük veya açık kod sözleşme çağrılan sahibi olmanız gerektiğinde bu seçeneği kullanın.

- Geçirmek `shared_ptr` başvuru veya const başvuru. Bu durumda, başvuru sayısının artırılması değil ve çağıran kapsam dışına çıkmadan değil sürece çağrılan işaretçi erişebilirsiniz. Ya da çağrılan oluşturmaya karar bir `shared_ptr` Referanslı ve paylaşılan bir sahibi olur. Çağrılan olanağıyla çağırana sahip olduğunda ya da geçirmeniz gerekir bu seçeneği kullanın. bir `shared_ptr` ve performansı artırmak için kopyalama işlemini ortadan kaldırmak istiyorsanız.

- Temel alınan işaretçiye veya arka plandaki nesneye bir başvuru geçirin. Bu nesne kullanmak Aranan sağlar, ancak bu paylaşım sahipliğinin veya ömrü genişletmek sağlamaz. Çağrılan oluşturursa bir `shared_ptr` ham işaretçisinden yeni `shared_ptr` orijinalden bağımsızdır ve temel alınan kaynak denetlemez. Sözleşme çağıran ve çağrılan arasında NET bir şekilde çağıran sahipliğini korur belirttiğinde, bu seçeneği kullanın. `shared_ptr` yaşam süresi.

- Ne zaman karar geçirmek nasıl bir `shared_ptr`, çağrılan temel alınan kaynağın sahipliği paylaşmaya gerekip gerekmediğini belirlemek. "Sahip" nesne veya işlev ihtiyaç duyduğu sürece, temel alınan kaynak için canlı tut ' dir. Çağrılan işaretçi ömrünü genişletebilirsiniz güvence altına almak çağırıcı sahip değilse, (işlev) yaşam süresi, ilk kullanım seçeneği. Çağrılan yaşam süresini uzatır olup olmadığını İlgilenmiyor, başvuruya göre ve veya kopyalama çağrılan olanak tanır.

- Gerekirse temel alınan işaretçi için ve bir yardımcı işlev erişim yardımcı işlevini yalnızca işaretçi kullanıyor ve çağıran işlevi döndürür ve ardından bu işlev önce iade olduğunu bilmeniz verin temel alınan işaretçi sahipliğini paylaşma gerekmez. Yalnızca işaretçi arayanın yaşam süresi içinde erişmek sahip `shared_ptr`. Bu durumda, geçirilecek güvenli `shared_ptr` başvuru veya pass ham işaretçi veya başvuru temel alınan nesne. Bu şekilde geçirme küçük performans artar ve ayrıca, programlama amacınızla express yardımcı olabilir.

- Bazı durumlarda örneğin bir `std:vector<shared_ptr<T>>`, her geçmesi gerekebilir `shared_ptr` bir lambda ifadesi gövdesinin veya adlandırılmış işlev nesnesi. Lambda veya işlev işaretçisi depolamaz, ardından geçirin `shared_ptr` her öğe için kopya Oluşturucusu çağrılırken önlemek için başvuruya göre.

## <a name="example-6"></a>Örnek 6

Aşağıdaki örnekte gösterildiği nasıl `shared_ptr` tarafından sahip olunan bir bellek işaretçi karşılaştırmalar etkinleştirmek için çeşitli Karşılaştırma işleçleri aşırı `shared_ptr` örnekleri.

[!code-cpp[stl_smart_pointers#3](../cpp/codesnippet/CPP/how-to-create-and-use-shared-ptr-instances_6.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Akıllı İşaretçiler (Modern C++)](../cpp/smart-pointers-modern-cpp.md)
