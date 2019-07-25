---
title: Örnek Kapsayıcı Sınıfı
ms.date: 11/04/2016
helpviewer_keywords:
- container classes [C++]
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
ms.openlocfilehash: 2024574633069cc70f0885fdce63f3afc09227c0
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451105"
---
# <a name="sample-container-class"></a>Örnek Kapsayıcı Sınıfı

> [!NOTE]
> Bu konu, C++ standart kitaplıkta kullanılan C++ kapsayıcıların Işlevsel bir örneği olarak Microsoft belgelerimde yer almaktadır. Daha fazla bilgi için bkz [ C++ . standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

Genellikle türündeki `Ty`, değişken uzunluklu bir öğe dizisini denetleyen bir nesne tanımlar. Sıra, gerçek kapsayıcıya bağlı olarak farklı yollarla depolanır.

Bir kapsayıcı Oluşturucu veya üye işlevi, Oluşturucu **Ty**(**const Ty &** ) veya işlev **Ty:: operator =** (**const Ty &** ) çağırmak için bir durum bulabilir. Böyle bir çağrı bir özel durum oluşturursa, kapsayıcı nesne bütünlüğünü sürdürmek ve yakalar özel durumu yeniden oluşturmak için kullanılır. Bir kapsayıcı nesnesini, bu özel durumlardan birini oluşturduktan sonra güvenle takas edebilir, atayabilir, silebilir veya yok edebilirsiniz. Ancak genel olarak, kapsayıcı nesnesi tarafından denetlenen sıranın durumunu tahmin edilemez.

Birkaç ek uyarılar:

- İfade `~Ty` bir özel durum oluşturursa, kapsayıcı nesnesinin sonuç durumu tanımsız olur.

- Kapsayıcı bir ayırıcı nesnesi *Al*ve *Al* , bir çağrısının `al.allocate`sonucu olarak dışında bir özel durum oluşturursa, kapsayıcı nesnesinin sonuç durumu tanımsız olur.

- Kapsayıcı bir işlev nesnesi *kompozisyonu*depoluyorsa, denetlenen sıranın nasıl oluşturulacağını ve *comp* her türlü özel durum oluşturduğunda, kapsayıcı nesnesinin sonuç durumu tanımsız olur.

Standart kitaplık tarafından C++ tanımlanan kapsayıcı sınıfları, aşağıdaki paragraflarda açıklandığı gibi birkaç ek gereksinimi karşılar.

Kapsayıcı şablonu sınıf [listesi](../standard-library/list-class.md) , yukarıda açıklanan özel durumların varlığına bile belirleyici ve yararlı bir davranış sağlar. Örneğin, bir veya daha fazla öğenin eklenmesi sırasında bir özel durum oluşturulursa, kapsayıcı değiştirilmemiş olarak kalır ve özel durum yeniden oluşturulur.

Standart  kitaplık tarafından C++ tanımlanan tüm kapsayıcı sınıfları için, bir özel durum aşağıdaki `insert`üye `push_back`işlevlerine yapılan çağrılar sırasında oluşturulursa,,, veya `push_front`, kapsayıcı değiştirilmemiş olarak bırakılır ve özel durum işlenemezse.

Standart  kitaplık tarafından C++ tanımlanan tüm kapsayıcı sınıfları için, aşağıdaki üye işlevlerine yapılan çağrılar sırasında hiçbir özel durum oluşturulmaz: `pop_back`, `pop_front`.

[Erase](../standard-library/container-class-erase.md) üye işlevi yalnızca bir kopyalama işlemi (atama veya kopyalama oluşturma) bir özel durum oluşturursa bir özel durum oluşturur.

Üstelik, bir üye işlevi tarafından döndürülen bir yineleyici kopyalanırken hiçbir özel durum oluşturulmaz.

Üye işlevi [takası](../standard-library/container-class-swap.md) , standart kitaplık tarafından C++ tanımlanan *Tüm* kapsayıcı sınıfları için ek taahhüt yapar:

- Üye işlevi yalnızca kapsayıcı bir ayırıcı nesnesi Al ' ı depoladığında bir özel durum oluşturur ve `al` kopyalanırken bir özel durum oluşturur.

- Değiştirilen denetim sıralarının öğelerini belirten başvurular, işaretçiler ve yineleyiciler geçerli kalır.

Standart kitaplık tarafından C++ tanımlanan kapsayıcı sınıfının bir nesnesi, genellikle bir şablon parametresi olan türünde `Alloc`depolanan bir nesne aracılığıyla denetlediği sıra için depolamayı ayırır ve boşaltır. Böyle bir ayırıcı nesne, sınıfının `allocator<Ty>`bir nesnesi ile aynı dış arabirime sahip olmalıdır. Özellikle, `Alloc` ile aynı türde olmalıdır`Alloc::rebind<value_type>::other`

Standart  kitaplık tarafından C++ tanımlanan tüm kapsayıcı sınıfları için, üye işlevi `Alloc get_allocator const;` Depolanan ayırıcı nesnesinin bir kopyasını döndürür. Kapsayıcı nesne atandığında saklı ayırıcı nesnesinin *kopyalanmadığını* unutmayın. Oluşturucu Ayırıcı parametresi içermiyorsa `allocator` `Alloc` , tüm oluşturucular ' de depolanan değeri başlatır.

C++ Standart olarak, standart kitaplık tarafından C++ tanımlanan bir kapsayıcı sınıfı şunları varsayabilir:

- Sınıf `Alloc` karşılaştırıldığı tüm nesneler eşittir.

- Tür `Alloc::const_pointer` ile`const Ty *`aynıdır.

- Tür `Alloc::const_reference` ile`const Ty&`aynıdır.

- Tür `Alloc::pointer` ile`Ty *`aynıdır.

- Tür `Alloc::reference` ile`Ty&`aynıdır.

Ancak, kapsayıcılar bu uygulamada basitleşmez. Bu nedenle, daha hırslı olan ayırıcı nesneleriyle düzgün şekilde çalışırlar:

- Sınıfın `Alloc` tüm nesnelerinin eşit olarak karşılaştırılabilmesi gerekmez. (Birden çok depolama havuzunu koruyabilirsiniz.)

- Türün `Alloc::const_pointer` ile`const Ty *`aynı olması gerekmez. (Const işaretçisi bir sınıf olabilir.)

- Türün `Alloc::pointer` ile`Ty *`aynı olması gerekmez. (Bir işaretçi bir sınıf olabilir.)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi**: \<örnek kapsayıcı >

## <a name="see-also"></a>Ayrıca bkz.

[\<örnek kapsayıcı >](../standard-library/sample-container.md)
