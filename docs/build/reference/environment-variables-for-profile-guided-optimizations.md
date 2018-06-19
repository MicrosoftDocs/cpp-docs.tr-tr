---
title: Profil temelli iyileştirmeler için ortam değişkenleri | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- profile-guided optimizations, environment variables
ms.assetid: f95a6d1e-49a4-4802-a144-092026b600a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19edc9c8a2702e5b7ac9ae4a49364718f19d3900
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379451"
---
# <a name="environment-variables-for-profile-guided-optimizations"></a>Profil Temelli İyileştirmeler için Ortam Değişkenleri

Test senaryoları ile oluşturulan görüntüdeki etkileyen üç ortam değişkenleri vardır **/LTCG:PGI** profil temelli iyileştirmeler için:

- **PogoSafeMode** hızlı mod veya güvenli mod uygulama profili oluşturma için kullanılıp kullanılmayacağını belirtir.

- **Vcprofıle_alloc_scale** Profil Oluşturucu tarafından kullanım için ek bellek ekler.

- **Vcprofıle_path** .pgc dosyaları için kullanılan klasör belirtmenize olanak sağlar.

**PogoSafeMode ve vcprofıle_alloc_scale ortam değişkenleri, Visual Studio 2015'ten başlayarak kullanım dışı bırakılmıştır.** Bağlayıcı seçenekleri [/GENPROFILE veya /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) ve [/USEPROFILE](useprofile.md) bu ortam değişkenleri olarak aynı bağlayıcı davranışı belirtin.

## <a name="pogosafemode"></a>PogoSafeMode

Bu ortam değişkeni kullanım dışı bırakılmıştır. Kullanım **tam** veya **NOEXACT** bağımsız değişkenleri **/GENPROFILE** veya **/FASTGENPROFILE** bu davranışını denetlemek için.

İşaretini kaldırın veya ayarlama **PogoSafeMode** hızlı mod veya güvenli mod x86 üzerinde uygulama profili oluşturma için kullanılıp kullanılmayacağını belirtmek için ortam değişkeni sistemler.

Profil temelli iyileştirme (PGO) sahip iki olası modları profil oluşturma aşamasında: *hızlı mod* ve *güvenli mod*. Profil oluşturma Hızlı modunda olduğunda kullanan **Inc** veri sayaçları artırmak için yönerge. **Inc** yönerge hızlıdır ancak iş parçacığı açısından güvenli değil. Profil oluşturma güvenli modda olduğunda, kullanan **kilit Inc** veri sayaçları artırmak için yönerge. **Kilit Inc** yönerge olan ile aynı işlevselliği **Inc** yönergesi sahiptir ve iş parçacığı güvenlidir, ancak daha yavaştır **Inc** yönergesi.

Varsayılan olarak, PGO profil hızlı modunda çalışır. **PogoSafeMode** olduğundan yalnızca güvenli mod kullanmak istiyorsanız gereklidir.

Güvenli modda PGO profil çalıştırmak için ya da ortam değişkeni kullanmanız gerekir **PogoSafeMode** ya da bağlayıcı anahtar **/PogoSafeMode**sistemine bağlı olarak. Profil oluşturma x x64 üzerinde gerçekleştirdiğiniz, bilgisayar, bağlayıcı anahtarı kullanmanız gerekir. Profil x x86 üzerinde gerçekleştirdiğiniz, bilgisayar, bağlayıcı kullanabilir geçiş veya ayarlayın **PogoSafeMode** ortam değişkeni, en iyi duruma getirme işlemine başlamadan önce herhangi bir değer.

### <a name="pogosafemode-syntax"></a>PogoSafeMode sözdizimi

> **PogoSafeMode ayarlamak**[**=**_değeri_]

Ayarlama **PogoSafeMode** güvenli modunu etkinleştirmek için herhangi bir değere. Önceki bir değeri silin ve hızlı mod yeniden etkinleştirmek için bir değer ayarlayın.

## <a name="vcprofileallocscale"></a>VCPROFILE_ALLOC_SCALE

Bu ortam değişkeni kullanım dışı bırakılmıştır. Kullanım **MEMMIN** ve **MEMMAX** bağımsız değişkenleri **/GENPROFILE** veya **/FASTGENPROFILE** bu davranışını denetlemek için.

Değiştirme **vcprofıle_alloc_scale** ayrılan bellek miktarını değiştirmek için ortam değişkeni profil verileri tutmak için. Nadir durumlarda olmayacaktır desteklemek için yeterli kullanılabilir bellek sınama senaryolarını çalıştırırken profil verilerini toplama. Bu gibi durumlarda ayarlayarak bellek miktarını artırabilirsiniz **vcprofıle_alloc_scale**. Yeterli bellek yok gösteren testi sırasında bir hata iletisi alırsanız, daha büyük bir değer atadığınız **vcprofıle_alloc_scale**, test bellek yetersiz hatasız tam çalıştırılana kadar.

### <a name="vcprofileallocscale-syntax"></a>Vcprofıle_alloc_scale sözdizimi

> **vcprofıle_alloc_scale ayarlamak**[__=__*scale_value*]

*Scale_value* ölçekleme faktörü sınama senaryolarını çalıştırmak için istediğiniz bellek miktarı için bir parametredir.  Varsayılan değer 1'dir. Örneğin, bu komut satırı ölçek faktörü 2'ye ayarlanır:

`set VCPROFILE_ALLOC_SCALE=2`

## <a name="vcprofilepath"></a>VCPROFILE_PATH

Kullanım **vcprofıle_path** ortam değişkeni .pgc dosyaları oluşturmak için bir dizini belirtin. Varsayılan olarak, .pgc dosyaları profili oluşturuluyor ikili olarak aynı dizinde oluşturulur. Ancak, ikili burada oluşturulmuş başka bir makine profili senaryoları çalıştırdığınızda durumda olabileceğinden ikili mutlak yolu, mevcut değilse, ayarlayabileceğiniz **vcprofıle_path** hedef makinede mevcut bir yolu.

### <a name="vcprofilepath-syntax"></a>Vcprofıle_path sözdizimi

> **vcprofıle_path ayarlamak**[**=**_yolu_]

Ayarlama *yolu* .pgc dosyaları eklemek dizin yolu parametresi. Örneğin, bu komut satırı klasör C:\profile için ayarlar:

`set VCPROFILE_PATH=c:\profile`

## <a name="see-also"></a>Ayrıca bkz.

[Profil Temelli İyileştirmeler](../../build/reference/profile-guided-optimizations.md)<br/>
[/ GENPROFILE ve /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/ USEPROFILE](useprofile.md)<br/>
