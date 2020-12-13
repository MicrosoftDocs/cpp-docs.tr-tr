---
description: 'Daha fazla bilgi edinin: örnek kapsayıcı sınıfı'
title: Örnek Kapsayıcı Sınıfı
ms.date: 11/04/2016
helpviewer_keywords:
- container classes [C++]
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
ms.openlocfilehash: 728cec44462a8e09aad7f87000520f0fa5a15b3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148882"
---
# <a name="sample-container-class"></a>Örnek Kapsayıcı Sınıfı

> [!NOTE]
> Bu konu, C++ standart kitaplığı 'nda kullanılan kapsayıcılardan oluşan işlevsel bir örnek olarak Microsoft C++ belgelerinde yer almaktadır. Daha fazla bilgi için bkz. [C++ standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

Genellikle türündeki, değişken uzunluklu bir öğe dizisini denetleyen bir nesne tanımlar `Ty` . Sıra, gerçek kapsayıcıya bağlı olarak farklı yollarla depolanır.

Bir kapsayıcı Oluşturucu veya üye işlevi, Oluşturucu **Ty**(**const Ty&**) veya işlev **Ty:: operator =**(**const Ty&**) çağırmak için bir durum bulabilir. Böyle bir çağrı bir özel durum oluşturursa, kapsayıcı nesne bütünlüğünü sürdürmek ve yakalar özel durumu yeniden oluşturmak için kullanılır. Bir kapsayıcı nesnesini, bu özel durumlardan birini oluşturduktan sonra güvenle takas edebilir, atayabilir, silebilir veya yok edebilirsiniz. Ancak genel olarak, kapsayıcı nesnesi tarafından denetlenen sıranın durumunu tahmin edilemez.

Birkaç ek uyarılar:

- İfade `~Ty` bir özel durum oluşturursa, kapsayıcı nesnesinin sonuç durumu tanımsız olur.

- Kapsayıcı bir ayırıcı nesnesi *Al* ve *Al* , bir çağrısının sonucu olarak dışında bir özel durum oluşturursa `al.allocate` , kapsayıcı nesnesinin sonuç durumu tanımsız olur.

- Kapsayıcı bir işlev nesnesi *kompozisyonu* depoluyorsa, denetlenen sıranın nasıl oluşturulacağını ve *comp* her türlü özel durum oluşturduğunda, kapsayıcı nesnesinin sonuç durumu tanımsız olur.

C++ standart kitaplığı tarafından tanımlanan kapsayıcı sınıfları, aşağıdaki paragraflarda açıklandığı gibi birkaç ek gereksinimi karşılar.

Kapsayıcı sınıfı şablon [listesi](../standard-library/list-class.md) , yukarıda açıklanan özel durumların varlığına bile belirleyici ve yararlı bir davranış sağlar. Örneğin, bir veya daha fazla öğenin eklenmesi sırasında bir özel durum oluşturulursa, kapsayıcı değiştirilmemiş olarak kalır ve özel durum yeniden oluşturulur.

C++ standart kitaplığı tarafından tanımlanan *Tüm* kapsayıcı sınıfları için,,, veya, aşağıdaki üye işlevlerine yapılan çağrılar sırasında bir özel durum oluşturulursa,, `insert` veya, `push_back` `push_front` kapsayıcı değiştirilmemiş olarak kalır ve özel durum yeniden oluşturulur.

C++ standart kitaplığı tarafından tanımlanan *Tüm* kapsayıcı sınıfları için, aşağıdaki üye işlevlerine yapılan çağrılar sırasında hiçbir özel durum oluşturulmaz: `pop_back` , `pop_front` .

[Erase](../standard-library/container-class-erase.md) üye işlevi yalnızca bir kopyalama işlemi (atama veya kopyalama oluşturma) bir özel durum oluşturursa bir özel durum oluşturur.

Üstelik, bir üye işlevi tarafından döndürülen bir yineleyici kopyalanırken hiçbir özel durum oluşturulmaz.

[Swap](../standard-library/container-class-swap.md) üye Işlevi, C++ standart kitaplığı tarafından tanımlanan *Tüm* kapsayıcı sınıfları için ek taahhüt yapar:

- Üye işlevi yalnızca kapsayıcı bir ayırıcı nesnesi Al ' ı depoladığında bir özel durum oluşturur ve `al` kopyalanırken bir özel durum oluşturur.

- Değiştirilen denetim sıralarının öğelerini belirten başvurular, işaretçiler ve yineleyiciler geçerli kalır.

C++ standart kitaplığı tarafından tanımlanan bir kapsayıcı sınıfının nesnesi `Alloc` , genellikle bir şablon parametresi olan türünde depolanan bir nesne aracılığıyla denetlediği sıra için depolamayı ayırır ve boşaltır. Böyle bir ayırıcı nesne, sınıfının bir nesnesi ile aynı dış arabirime sahip olmalıdır `allocator<Ty>` . Özellikle, `Alloc` ile aynı türde olmalıdır `Alloc::rebind<value_type>::other`

C++ standart kitaplığı tarafından tanımlanan *Tüm* kapsayıcı sınıfları için, üye işlevi `Alloc get_allocator const;` Depolanan ayırıcı nesnesinin bir kopyasını döndürür. Kapsayıcı nesne atandığında saklı ayırıcı nesnesinin *kopyalanmadığını* unutmayın. `allocator`Oluşturucu Ayırıcı parametresi içermiyorsa, tüm oluşturucular ' de depolanan değeri başlatır `Alloc` .

C++ standardına göre, C++ standart kitaplığı tarafından tanımlanan bir kapsayıcı sınıfı şunları varsayabilir:

- Sınıf `Alloc` karşılaştırıldığı tüm nesneler eşittir.

- Tür `Alloc::const_pointer` ile aynıdır `const Ty *` .

- Tür `Alloc::const_reference` ile aynıdır `const Ty&` .

- Tür `Alloc::pointer` ile aynıdır `Ty *` .

- Tür `Alloc::reference` ile aynıdır `Ty&` .

Ancak, kapsayıcılar bu uygulamada basitleşmez. Bu nedenle, daha hırslı olan ayırıcı nesneleriyle düzgün şekilde çalışırlar:

- Sınıfın tüm nesnelerinin `Alloc` eşit olarak karşılaştırılabilmesi gerekmez. (Birden çok depolama havuzunu koruyabilirsiniz.)

- Türün `Alloc::const_pointer` ile aynı olması gerekmez `const Ty *` . (Const işaretçisi bir sınıf olabilir.)

- Türün `Alloc::pointer` ile aynı olması gerekmez `Ty *` . (Bir işaretçi bir sınıf olabilir.)

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<sample container>

## <a name="see-also"></a>Ayrıca bkz.

[\<sample container>](../standard-library/sample-container.md)
