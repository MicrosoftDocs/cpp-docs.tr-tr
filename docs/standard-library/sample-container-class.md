---
title: "Örnek kapsayıcı sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- container classes [C++]
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0d528f53747979da7b95d8d3298a43ea717007a5
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="sample-container-class"></a>Örnek Kapsayıcı Sınıfı
> [!NOTE]
>  Bu konu, Visual C++ belge C++ Standart Kitaplığı'nda kullanılan kapsayıcıları işlevsel bir örnek olarak kullanılıyor. Daha fazla bilgi için bkz: [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).  
  
 Genellikle türündeki öğeler değişen uzunluk dizisi denetleyen bir nesneyi tanımlayan **Ty**. Sıra gerçek kapsayıcı bağlı olarak, farklı şekillerde depolanır.  
  
 Kapsayıcı Oluşturucusu veya üye işlevi oluşturucuyu çağırmak için gün bulabilirsiniz **Ty**(**const Ty &**) veya işlev **Ty::operator =**(**const Ty &**). Bu tür bir çağrı bir özel durum oluşturursa, kapsayıcı nesnesinin kendi bütünlüğünü sağlamak ve onu yakalar herhangi bir özel durum yeniden oluşturulması için'de de yükümlülüğü olan. Güvenli bir şekilde değiştirme, silmek veya bu özel durumları oluşturur sonra bir kapsayıcı nesne yok etmek için atayın. Genel olarak, ancak, aksi takdirde kapsayıcı nesne tarafından denetlenen sırası durumunu tahmin edemezsiniz.  
  
 Birkaç ek uyarılar:  
  
-   Varsa ifade **~ Ty** özel durumu verir, sonuçta elde edilen durumu kapsayıcı nesnesinin tanımlanmadı.  
  
-   Kapsayıcı ayırıcısı nesneyi depoluyorsa *al*, ve *al* dışında yapılan bir çağrı sonucunda aykırı * al ***.allocate**, kapsayıcı elde edilen durumu Nesne tanımlanmamıştır.  
  
-   Kapsayıcı işlev nesnesi depoluyorsa *comp*nasıl denetimli, sırasını belirlemek için ve *comp* atar özel durum herhangi türde bir kapsayıcı nesnesinin ortaya çıkan durum tanımlanmadı.  
  
 C++ Standart Kitaplığı tarafından tanımlanan kapsayıcı sınıfları aşağıdaki paragrafta açıklanan bazı ek gereksinimleri karşılar.  
  
 Kapsayıcı Şablon sınıfı [listesi](../standard-library/list-class.md) bile yukarıda açıklanan özel durumlar varlığında belirleyici ve yararlı davranış sağlar. Örneğin, bir ekleme sırasında bir özel durum ya da daha fazla öğe, kapsayıcı ise sol değiştirilmemiş ve özel durum işlenemezse.  
  
 İçin *tüm* aşağıdaki üye işlevleri çağrı sırasında bir özel durum, C++ Standart Kitaplığı tarafından tanımlanan kapsayıcı sınıfları:  
  
```  
<A NAME="vclrfcontainerinsert"></A>insert // single element inserted  
<A NAME="vclrfcontainerpushback"></A>push_back  
<A NAME="vclrfcontainerpushfront"></A>push_front  
```  
  
 kapsayıcı sol değiştirilmemiş ve özel durum işlenemezse.  
  
 İçin *tüm* C++ Standart Kitaplığı tarafından tanımlanan kapsayıcı sınıfları aşağıdaki üye işlevleri çağrı sırasında hiçbir özel durum oluşur:  
  
```  
<A NAME="vclrfcontainerpopback"></A>pop_back  
<A NAME="vclrfcontainerpopfront"></A>pop_front  
```  
  
 Üye işlevini [silme](../standard-library/container-class-erase.md) yalnızca bir kopyalama işlemi (ataması ya da kopyalama yapım) bir özel durum oluşturursa bir özel durum oluşturur.  
  
 Ayrıca, herhangi bir özel durumu, üye işlevi tarafından döndürülen yineleyici kopyalanırken atılır.  
  
 Üye işlevini [takas](../standard-library/container-class-swap.md) ek öneriler yapar *tüm* C++ Standart Kitaplığı tarafından tanımlanan kapsayıcı sınıfları:  
  
-   Yalnızca kapsayıcı bir ayırıcı nesne al depoluyorsa üye işlevi bir özel durum oluşturur ve `al` kopyalandığında bir özel durum oluşturur.  
  
-   Başvurular, işaretçiler ve öğeleri değiştiriliyor denetimli sıralarının tanımladığınız yineleyiciler geçerli kalır.  
  
 C++ Standart Kitaplığı tarafından tanımlanan bir kapsayıcı sınıfın bir nesnesi ayırır ve depolanan bir nesne türü denetlediği dizisi için depolama boşaltır `Alloc`, olduğu genellikle bir şablon parametresi. Ayırıcı böyle bir nesnenin aynı dış arabirimi sınıfın bir nesnesi olarak olmalıdır **ayırıcısı\<Ty >**. Özellikle, `Alloc` aynı türde olmalıdır **Alloc::rebind < value_type >:: diğer**  
  
 İçin *tüm* C++ Standart Kitaplığı tarafından üye fonksiyonu tanımlanan kapsayıcı sınıfları **ayırma get_allocator const;** saklı ayırıcısı nesnesinin bir kopyasını döndürür. Saklı ayırıcısı nesne olduğuna dikkat edin *değil* container nesnesi atandığında kopyalanır. Tüm oluşturucular depolanan değeriyle **ayırıcısı**, `Alloc` oluşturucusu yok ayırıcısı parametresi içeriyorsa.  
  
 C++ Standart göre C++ Standart Kitaplığı tarafından tanımlanan bir kapsayıcı sınıfını çalıştığını kabul edebilirsiniz:  
  
-   Sınıfın tüm nesneleri `Alloc` karşılaştırma eşittir.  
  
-   Tür **Alloc::const_pointer** aynı **const Ty \*** .  
  
-   Tür **Alloc::const_reference** aynı **const Ty &**.  
  
-   Tür **Alloc::pointer** aynı **Ty \*** .  
  
-   Tür **Alloc::reference** aynı **Ty &**.  
  
 Bu uygulama, ancak, bu tür basitleştirme varsayımlar kapsayıcıları yapmayın. Bu nedenle, bunların düzgün daha hırslı ayırıcı nesneleri ile çalışma:  
  
-   Sınıfın tüm nesneleri `Alloc` karşılaştırmak eşit gerekmez. (Birden çok havuz depolama bulundurabilir.)  
  
-   Tür **Alloc::const_pointer** aynı olması gerekmez **const Ty \*** . (Const bir işaretçi bir sınıf olabilir.)  
  
-   Tür **Alloc::pointer** aynı olması gerekmez **Ty \*** . (Bir işaretçi bir sınıf olabilir.)  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: \<örnek kapsayıcı >  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Örnek kapsayıcı >](../standard-library/sample-container.md)

