---
title: Örnek Kapsayıcı Sınıfı
ms.date: 11/04/2016
helpviewer_keywords:
- container classes [C++]
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
ms.openlocfilehash: 404e372e65af8b93ae4f6f2827a73ef64336690a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688970"
---
# <a name="sample-container-class"></a>Örnek Kapsayıcı Sınıfı

> [!NOTE]
> Bu konu, C++ standart kitaplıkta kullanılan C++ kapsayıcıların Işlevsel bir örneği olarak Microsoft belgelerimde yer almaktadır. Daha fazla bilgi için bkz [ C++ . standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

Genellikle `Ty` türündeki, değişken uzunluklu bir öğe dizisini denetleyen bir nesne tanımlar. Sıra, gerçek kapsayıcıya bağlı olarak farklı yollarla depolanır.

Bir kapsayıcı Oluşturucu veya üye işlevi, Oluşturucu **Ty**(**const Ty &** ) veya işlev **Ty:: operator =** (**const Ty &** ) çağırmak için bir durum bulabilir. Böyle bir çağrı bir özel durum oluşturursa, kapsayıcı nesne bütünlüğünü sürdürmek ve yakalar özel durumu yeniden oluşturmak için kullanılır. Bir kapsayıcı nesnesini, bu özel durumlardan birini oluşturduktan sonra güvenle takas edebilir, atayabilir, silebilir veya yok edebilirsiniz. Ancak genel olarak, kapsayıcı nesnesi tarafından denetlenen sıranın durumunu tahmin edilemez.

Birkaç ek uyarılar:

- İfade `~Ty` bir özel durum oluşturursa, kapsayıcı nesnesinin sonuç durumu tanımsız olur.

- Kapsayıcı bir ayırıcı nesnesi *Al*ve *Al* , `al.allocate` bir çağrının sonucu olarak dışında bir özel durum oluşturursa, kapsayıcı nesnesinin sonuç durumu tanımsız olur.

- Kapsayıcı bir işlev nesnesi *kompozisyonu*depoluyorsa, denetlenen sıranın nasıl oluşturulacağını ve *comp* her türlü özel durum oluşturduğunda, kapsayıcı nesnesinin sonuç durumu tanımsız olur.

Standart kitaplık tarafından C++ tanımlanan kapsayıcı sınıfları, aşağıdaki paragraflarda açıklandığı gibi birkaç ek gereksinimi karşılar.

Kapsayıcı sınıfı şablon [listesi](../standard-library/list-class.md) , yukarıda açıklanan özel durumların varlığına bile belirleyici ve yararlı bir davranış sağlar. Örneğin, bir veya daha fazla öğenin eklenmesi sırasında bir özel durum oluşturulursa, kapsayıcı değiştirilmemiş olarak kalır ve özel durum yeniden oluşturulur.

Standart kitaplık tarafından C++ tanımlanan tüm kapsayıcı sınıfları için, aşağıdaki üye işlevlerine yapılan çağrılar sırasında bir özel durum oluşturulursa, `insert`, `push_back` veya `push_front`, kapsayıcı değiştirilmemiş olarak kalır ve özel durum yeniden oluşturulur.

Standart kitaplık tarafından C++ tanımlanan tüm kapsayıcı sınıfları için, şu üye işlevlerine yapılan çağrılar sırasında hiçbir özel durum oluşturulmaz: `pop_back`, `pop_front`.

[Erase](../standard-library/container-class-erase.md) üye işlevi yalnızca bir kopyalama işlemi (atama veya kopyalama oluşturma) bir özel durum oluşturursa bir özel durum oluşturur.

Üstelik, bir üye işlevi tarafından döndürülen bir yineleyici kopyalanırken hiçbir özel durum oluşturulmaz.

Üye işlevi [takası](../standard-library/container-class-swap.md) , standart kitaplık tarafından C++ tanımlanan *Tüm* kapsayıcı sınıfları için ek taahhüt yapar:

- Üye işlevi yalnızca kapsayıcı bir ayırıcı nesne al öğesini depoladığında bir özel durum oluşturur ve `al` kopyalanırken bir özel durum oluşturur.

- Değiştirilen denetim sıralarının öğelerini belirten başvurular, işaretçiler ve yineleyiciler geçerli kalır.

Standart kitaplık tarafından C++ tanımlanan kapsayıcı sınıfının bir nesnesi, genellikle bir şablon parametresi olan `Alloc` türünde depolanan bir nesne aracılığıyla denetleyen diziyi ayırır ve serbest bırakır. Böyle bir ayırıcı nesne, `allocator<Ty>` sınıf bir nesne ile aynı dış arabirime sahip olmalıdır. Özellikle, `Alloc` `Alloc::rebind<value_type>::other` aynı türde olmalıdır

Standart kitaplık tarafından C++ tanımlanan tüm kapsayıcı sınıfları için, üye işlevi `Alloc get_allocator const;` Depolanan ayırıcı nesnesinin bir kopyasını döndürür. Kapsayıcı nesne atandığında saklı ayırıcı nesnesinin *kopyalanmadığını* unutmayın. Oluşturucu Ayırıcı parametresi içermiyorsa, tüm oluşturucular `allocator` ' de depolanan değeri `Alloc` olarak başlatır.

C++ Standart olarak, standart kitaplık tarafından C++ tanımlanan bir kapsayıcı sınıfı şunları varsayabilir:

- @No__t_0 karşılaştırma sınıfının tüm nesneleri eşit.

- @No__t_0 türü `const Ty *` aynı.

- @No__t_0 türü `const Ty&` aynı.

- @No__t_0 türü `Ty *` aynı.

- @No__t_0 türü `Ty&` aynı.

Ancak, kapsayıcılar bu uygulamada basitleşmez. Bu nedenle, daha hırslı olan ayırıcı nesneleriyle düzgün şekilde çalışırlar:

- @No__t_0 sınıfının tüm nesnelerinin eşit karşılaştırmaya gerek yoktur. (Birden çok depolama havuzunu koruyabilirsiniz.)

- @No__t_0 türün `const Ty *` aynı olması gerekmez. (Const işaretçisi bir sınıf olabilir.)

- @No__t_0 türün `Ty *` aynı olması gerekmez. (Bir işaretçi bir sınıf olabilir.)

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: kapsayıcı > \<sample

## <a name="see-also"></a>Ayrıca bkz.

[kapsayıcı > \<sample](../standard-library/sample-container.md)
