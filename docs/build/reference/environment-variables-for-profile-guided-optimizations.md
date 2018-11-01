---
title: Profil Temelli İyileştirmeler için Ortam Değişkenleri
ms.date: 03/14/2018
helpviewer_keywords:
- profile-guided optimizations, environment variables
ms.assetid: f95a6d1e-49a4-4802-a144-092026b600a3
ms.openlocfilehash: 2d69019f01a59f170aeeee22ef10b1af0de07a68
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595669"
---
# <a name="environment-variables-for-profile-guided-optimizations"></a>Profil Temelli İyileştirmeler için Ortam Değişkenleri

Test senaryoları ile oluşturulan bir görüntüye etkileyen üç ortam değişkenleri vardır **/LTCG:PGI** profil temelli iyileştirmeler için:

- **PogoSafeMode** uygulama profil oluşturma için hızlı mod veya güvenli mod kullanılıp kullanılmayacağını belirtir.

- **Vcprofıle_alloc_scale** ek bellek Profil Oluşturucu tarafından kullanılmak üzere ekler.

- **Vcprofıle_path** .pgc dosyaları için kullanılan klasör belirtmenize olanak tanır.

**PogoSafeMode ve vcprofıle_alloc_scale ortam değişkenleri, Visual Studio 2015'ten başlayarak kullanım dışı bırakılmıştır.** Bağlayıcı seçenekleri [/genprofıle veya fastgenprofıle](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) ve [/USEPROFILE](useprofile.md) bu ortam değişkenleri olarak aynı bağlayıcı davranışı belirtin.

## <a name="pogosafemode"></a>PogoSafeMode

Bu ortam değişkeni kullanım dışı bırakılmıştır. Kullanım **EXACT** veya **NOEXACT** bağımsız değişkenleri **/genprofıle** veya **fastgenprofıle** bu davranışını denetlemek için.

Temizleyin veya ayarlayın **PogoSafeMode** x86 üzerinde uygulama profilini oluşturmak için hızlı mod veya güvenli mod kullanılıp kullanılmayacağını belirtmek için ortam değişkeni sistemler.

Profil temelli iyileştirme (PGO) profil oluşturma aşamasında olası iki modu vardır: *hızlı mod* ve *güvenli mod*. Hızlı modda profil oluşturulduğunda, kullandığı **dahil edilen** veri sayısını artırmak için yönergeler. **Dahil edilen** yönergesi daha hızlıdır ancak iş parçacığı açısından güvenli değildir. Güvenli modda profil oluşturulduğunda, kullandığı **kilit dahil edilen** veri sayısını artırmak için yönergeler. **Kilit dahil edilen** yönergesi ile aynı işlevlere sahip **dahil edilen** yönerge sahiptir ve iş parçacığı açısından güvenlidir, ancak daha yavaştır **dahil edilen** yönergesi.

Varsayılan olarak, PGO profil oluşturma Hızlı modda çalışır. **PogoSafeMode** olduğundan yalnızca güvenli mod kullanmak isterseniz gereklidir.

PGO profil oluşturmayı güvenli modda çalıştırmak için ya da ortam değişkenini kullanmalısınız **PogoSafeMode** veya bağlayıcı anahtarını **/PogoSafeMode**sistem bağlı olarak. X x64 profil oluşturma işlemi yapıyorsanız bilgisayarı bağlayıcı anahtarını kullanmanız gerekir. X x86 profil oluşturma işlemi yapıyorsanız bilgisayar, bağlayıcı kullanabilir geçin veya ayarlayın **PogoSafeMode** ortam değişkeni en iyi duruma getirme işlemine başlamadan önce herhangi bir değer.

### <a name="pogosafemode-syntax"></a>PogoSafeMode söz dizimi

> **PogoSafeMode ayarlamak**[**=**_değer_]

Ayarlama **PogoSafeMode** için güvenli modunu etkinleştirmek için herhangi bir değer. Bir önceki değeri temizlemek ve hızlı mod yeniden etkinleştirmek için bir değer olmadan ayarlayın.

## <a name="vcprofileallocscale"></a>VCPROFILE_ALLOC_SCALE

Bu ortam değişkeni kullanım dışı bırakılmıştır. Kullanım **MEMMIN** ve **MEMMAX** bağımsız değişkenleri **/genprofıle** veya **fastgenprofıle** bu davranışını denetlemek için.

Değiştirme **vcprofıle_alloc_scale** ayrılan bellek miktarını değiştirmek için ortam değişkeni profil verilerini tutacak. Nadir durumlarda olmayacaktır desteklemek için yeterli kullanılabilir bellek test senaryoları çalışırken profili verilerini toplama. Bu gibi durumlarda ayarlayarak bellek miktarını artırabilir **vcprofıle_alloc_scale**. Yetersiz bellek olduğunu gösteren bir test çalıştırması sırasında bir hata iletisi alırsanız, büyük bir değer atayın **vcprofıle_alloc_scale**kadar çalıştırmalar yok bellek yetersiz hatalarla tamamlandı.

### <a name="vcprofileallocscale-syntax"></a>Vcprofıle_alloc_scale söz dizimi

> **vcprofıle_alloc_scale ayarlamak**[__=__*scale_value*]

*Scale_value* parametresi, bir Ölçeklendirme çarpanı test senaryoları çalıştırmak için istediğiniz bellek miktarı.  Varsayılan değer 1'dir. Örneğin, bu komut satırı ölçek faktörü 2'ye ayarlanır:

`set VCPROFILE_ALLOC_SCALE=2`

## <a name="vcprofilepath"></a>VCPROFILE_PATH

Kullanım **vcprofıle_path** ortam değişkenini .pgc dosyaları oluşturmak için dizini belirtin. Varsayılan olarak, profili oluşturulan ikili dosya ile aynı dizinde .pgc dosyası oluşturulur. Ancak, ikili burada oluşturulmuş başka bir makine profili senaryoları çalıştırdığınızda durumda olabileceğinden ikili mutlak yolu, mevcut değilse, ayarlayabilirsiniz **vcprofıle_path** hedef makinede var olan bir yolu.

### <a name="vcprofilepath-syntax"></a>Vcprofıle_path söz dizimi

> **vcprofıle_path ayarlamak**[**=**_yolu_]

Ayarlama *yolu* parametresi .pgc dosyaları eklemek dizin yolu. Örneğin, bu komut satırı klasör C:\profile için ayarlar:

`set VCPROFILE_PATH=c:\profile`

## <a name="see-also"></a>Ayrıca bkz.

[Profil Temelli İyileştirmeler](../../build/reference/profile-guided-optimizations.md)<br/>
[/ GENPROFILE ve fastgenprofıle](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/USEPROFILE](useprofile.md)<br/>
