---
title: Örnek Kapsayıcı Sınıfı
ms.date: 11/04/2016
helpviewer_keywords:
- container classes [C++]
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
ms.openlocfilehash: c797a893549c8ec708cfb60e6f002b35c27cd35c
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220237"
---
# <a name="sample-container-class"></a>Örnek Kapsayıcı Sınıfı

> [!NOTE]
> Bu konu Microsoft olan C++ kullanılan kapsayıcıları işlevsiz bir örnek olarak belgeleri C++ standart kitaplığı. Daha fazla bilgi için [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).

Öğeler, genellikle türündeki değişen uzunluktaki dizisini denetleyen bir nesneyi tanımlayan `Ty`. Sıralı kapsayıcı bağlı olarak farklı şekillerde depolanır.

Bir kapsayıcı Oluşturucusu veya üye işlev oluşturucuyu çağırmak için gün bulabilirsiniz **Ty**(**const Ty &**) veya işlev **Ty::operator =**(**const Ty &**). Böyle bir çağrı, bir özel durum oluşturursa, kapsayıcı nesnesi bütünlüğünü sağlamak ve zaman yakalar herhangi bir özel durumu yeniden oluşturulması için'de de yükümlülüğü olan. Güvenli bir şekilde değiştirme, silme veya bu özel durumları oluşturur sonra kapsayıcı nesnesini yok etmek için atayın. Genel olarak, ancak, aksi takdirde kapsayıcı nesnesi tarafından denetlenen dizinin durumunu tahmin edemezsiniz.

Birkaç ek uyarılar:

- İfade `~Ty` özel durumu oluşturur, sonuçta elde edilen kapsayıcı nesnenin durumu tanımsızdır.

- Kapsayıcı bir ayırıcı nesnesini depolar *al*, ve *al* dışında bir özel durum çağrı sonucunda oluşturur `al.allocate`, sonuçta elde edilen kapsayıcı nesnenin durumu tanımsızdır.

- Kapsayıcı bir işlev nesnesi depoluyorsa *comp*, denetlenen sıra sıralamanızı nasıl belirlemek için ve *comp* herhangi bir türde özel durumu oluşturur, sonuçta elde edilen kapsayıcı nesnenin durumu tanımsızdır.

C++ Standart Kitaplığı tarafından tanımlanan kapsayıcı sınıfları, aşağıdaki paragrafta açıklandığı gibi bazı ek gereksinimleri karşılar.

Kapsayıcı Şablon sınıfı [listesi](../standard-library/list-class.md) bile yukarıda açıklanan özel durumlar varsa kararlı ve yararlı davranış sağlar. Örneğin, bir ekleme sırasında bir özel durum veya daha fazla öğe, kapsayıcının sol değiştirilmeden ve özel durum yeniden oluşur.

İçin *tüm* aşağıdaki üye işlevleri, çağrı sırasında bir özel durum oluşturulursa, C++ Standart Kitaplığı tarafından tanımlanan kapsayıcı sınıfları `insert`, `push_back`, veya `push_front`, kapsayıcının sol değiştirilmemiş ve özel durum yeniden oluşur.

İçin *tüm* C++ Standart Kitaplığı tarafından tanımlanan, bir kapsayıcı sınıfları aşağıdaki üye işlevleri çağrı sırasında hiçbir özel durum: `pop_back`, `pop_front`.

Üye işlevi [silme](../standard-library/container-class-erase.md) yalnızca bir kopyalama işlemi (atama veya kopya oluşturma) bir özel durum oluşturursa, bir özel durum oluşturur.

Ayrıca, üye işlevi tarafından döndürülen yineleyici kopyalanırken hiçbir özel durum oluşturulur.

Üye işlevi [takas](../standard-library/container-class-swap.md) ek öneriler yapar *tüm* C++ Standart Kitaplığı tarafından tanımlanan kapsayıcı sınıfları:

- Üye işlevi yalnızca bir ayırıcı nesnesi al kapsayıcı depolayan bir özel durum oluşturur ve `al` kopyalarken bir özel durum oluşturur.

- Başvurular, işaretçiler ve öğeleri değiştiriliyor denetimli sıralarının belirlemek yineleyiciler geçerli kalır.

C++ Standart Kitaplığı tarafından tanımlanan bir kapsayıcı sınıfının bir nesnesi ayırır ve serbest bırakma türü depolanmış bir nesne denetlediği dizi için depolama `Alloc`, olduğu genellikle bir şablon parametresi. Böyle bir ayırıcı nesnenin sınıfın bir nesnesi olarak aynı dış arayüze sahip olması gerekir `allocator<Ty>`. Özellikle, `Alloc` aynı türde olmalıdır `Alloc::rebind<value_type>::other`

İçin *tüm* C++ Standart Kitaplığı tarafından üye işlevi tanımlanan kapsayıcı sınıfları `Alloc get_allocator const;` saklı ayırıcı nesnesini bir kopyasını döndürür. Saklı ayırıcı nesnesini olduğuna dikkat edin *değil* kapsayıcı nesne atandığında kopyalanır. Tüm oluşturucular depolanan değeriyle `allocator`, `Alloc` Oluşturucu ayırıcı parametre içeriyorsa.

C++ standardına göre C++ Standart Kitaplığı tarafından tanımlanan bir kapsayıcı sınıfı, kabul edilebilir:

- Sınıfın tüm nesneleri `Alloc` karşılaştırma eşittir.

- Tür `Alloc::const_pointer` aynı `const Ty *`.

- Tür `Alloc::const_reference` aynı `const Ty&`.

- Tür `Alloc::pointer` aynı `Ty *`.

- Tür `Alloc::reference` aynı `Ty&`.

Bu uygulama, ancak böyle basitleştirme varsayımlar kapsayıcıları yapmayın. Bu nedenle, daha hırslı ayırıcı nesneleri ile düzgün çalıştıklarını:

- Sınıfın tüm nesneleri `Alloc` karşılaştırma eşit gerek yoktur. (Birden çok depolama havuzlarını koruyabilirsiniz.)

- Tür `Alloc::const_pointer` aynı olması gerekmez `const Ty *`. (Bir const işaretçisi bir sınıf olabilir.)

- Tür `Alloc::pointer` aynı olması gerekmez `Ty *`. (Bir işaretçiyi bir sınıf olabilir.)

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<örnek kapsayıcı >

## <a name="see-also"></a>Ayrıca bkz.

[\<Örnek kapsayıcı >](../standard-library/sample-container.md)<br/>
