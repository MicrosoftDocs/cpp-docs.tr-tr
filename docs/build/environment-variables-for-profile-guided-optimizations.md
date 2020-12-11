---
description: 'Hakkında daha fazla bilgi edinin: Profile-Guided Iyileştirmeleri için ortam değişkenleri'
title: Profil Temelli İyileştirmeler için Ortam Değişkenleri
ms.date: 03/14/2018
helpviewer_keywords:
- profile-guided optimizations, environment variables
ms.assetid: f95a6d1e-49a4-4802-a144-092026b600a3
ms.openlocfilehash: dd78db781fc19b7ecfd451e01dc046b21bd87d11
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156677"
---
# <a name="environment-variables-for-profile-guided-optimizations"></a>Profil Temelli İyileştirmeler için Ortam Değişkenleri

**/LTCG: PGI** ile oluşturulan bir görüntüde test senaryolarını, profil temelli iyileştirmeler için etkileyen üç ortam değişkeni vardır:

- **PogoSafeMode** uygulama profili oluşturma için hızlı mod veya güvenli mod kullanılıp kullanılmayacağını belirtir.

- **VCPROFILE_ALLOC_SCALE** profil oluşturucu tarafından kullanılmak üzere ek bellek ekler.

- **VCPROFILE_PATH** . pgc dosyaları için kullanılan klasörü belirtmenize olanak tanır.

**PogoSafeMode ve VCPROFILE_ALLOC_SCALE ortam değişkenleri, Visual Studio 2015 ' den itibaren kullanımdan kaldırılmıştır.** [/Genprofile veya/FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) ve [/useprofile](reference/useprofile.md) bağlayıcı seçenekleri, bu ortam değişkenleriyle aynı bağlayıcı davranışını belirtir.

## <a name="pogosafemode"></a>PogoSafeMode

Bu ortam değişkeni kullanım dışıdır. Bu davranışı denetlemek için **/Genprofile** veya **/fastgenprofile** **tam** veya **tam** bağımsız değişkenlerini kullanın.

X86 sistemlerinde uygulama profili oluşturma için hızlı mod veya güvenli mod kullanıp kullanmayacağınızı belirtmek için **PogoSafeMode** ortam değişkenini temizleyin veya ayarlayın.

Profil temelli iyileştirme (PGO), profil oluşturma aşamasında iki olası moda sahiptir: *hızlı mod* ve *Güvenli mod*. Profil oluşturma hızlı moddayken, veri sayaçlarını artırmak için **Inc** yönergesini kullanır. **Inc** yönergesi daha hızlıdır, ancak iş parçacığı açısından güvenli değildir. Profil oluşturma güvenli moddayken, veri sayaçlarını artırmak için **Lock Inc** yönergesini kullanır. **Lock Inc** yönergesi, **Inc** yönergesiyle aynı işlevselliğe sahiptir ve iş parçacığı açısından güvenlidir, ancak bu, **Inc** yönergesinden daha yavaştır.

Varsayılan olarak, PGO profil oluşturma hızlı modda çalışır. **PogoSafeMode** yalnızca güvenli mod kullanmak istiyorsanız gereklidir.

PGO profil oluşturmayı güvenli modda çalıştırmak için, sisteme bağlı olarak **PogoSafeMode** ortam değişkenini ya da **/PogoSafeMode** bağlayıcı anahtarını kullanmanız gerekir. Bir x64 bilgisayarda profil oluşturma işlemi yapıyorsanız bağlayıcı anahtarını kullanmanız gerekir. Bir x86 bilgisayarda profil oluşturma işlemi yapıyorsanız, en iyi duruma getirme işlemine başlamadan önce bağlayıcı anahtarını kullanabilir veya **PogoSafeMode** ortam değişkenini herhangi bir değere ayarlayabilirsiniz.

### <a name="pogosafemode-syntax"></a>PogoSafeMode sözdizimi

> **set PogoSafeMode**[ **=** _değer_]

Güvenli modu etkinleştirmek için **PogoSafeMode** değerini herhangi bir değere ayarlayın. Önceki bir değeri temizlemek ve hızlı modu yeniden etkinleştirmek için değer olmadan ayarlayın.

## <a name="vcprofile_alloc_scale"></a>VCPROFILE_ALLOC_SCALE

Bu ortam değişkeni kullanım dışıdır. Bu davranışı denetlemek için **/Genprofile** veya **/Fastgenprofile** Için **memmin** ve **MEMMAX** bağımsız değişkenlerini kullanın.

**VCPROFILE_ALLOC_SCALE** ortam değişkenini, profil verilerini tutmak için ayrılan bellek miktarını değiştirmek üzere değiştirin. Nadir durumlarda, test senaryolarını çalıştırırken profil verileri toplamayı desteklemek için yeterli kullanılabilir bellek olmayacaktır. Bu durumlarda, **VCPROFILE_ALLOC_SCALE** ayarlayarak bellek miktarını artırabilirsiniz. Yetersiz belleğinizin olduğunu belirten bir test çalıştırması sırasında bir hata iletisi alırsanız, test çalıştırmaları, yetersiz bellek hataları olmadan tamamlanana kadar daha büyük bir değer atayın **VCPROFILE_ALLOC_SCALE**.

### <a name="vcprofile_alloc_scale-syntax"></a>VCPROFILE_ALLOC_SCALE sözdizimi

> **set VCPROFILE_ALLOC_SCALE**[ __=__ *scale_value*]

*Scale_value* parametresi, test senaryolarını çalıştırmak istediğiniz bellek miktarı için bir ölçeklendirme etkendir.  Varsayılan değer 1'dir. Örneğin, bu komut satırı ölçek faktörünü 2 olarak ayarlar:

`set VCPROFILE_ALLOC_SCALE=2`

## <a name="vcprofile_path"></a>VCPROFILE_PATH

. Pgc dosyalarını oluşturmak için dizini belirtmek üzere **VCPROFILE_PATH** ortam değişkenini kullanın. Varsayılan olarak,. pgc dosyaları profili oluşturulan ikilide aynı dizinde oluşturulur. Ancak, ikili dosyanın mutlak yolu yoksa, ikili dosyanın oluşturulduğu farklı bir makinede profil senaryolarını çalıştırdığınızda olduğu gibi, **VCPROFILE_PATH** hedef makinede bulunan bir yola ayarlayabilirsiniz.

### <a name="vcprofile_path-syntax"></a>VCPROFILE_PATH sözdizimi

> **set VCPROFILE_PATH**[ **=** _yol_]

*Path* parametresini,. pgc dosyalarının ekleneceği dizin yoluna ayarlayın. Örneğin, bu komut satırı klasörünü C:\profile olarak ayarlar:

`set VCPROFILE_PATH=c:\profile`

## <a name="see-also"></a>Ayrıca bkz.

[Profil temelli Iyileştirmeler](profile-guided-optimizations.md)<br/>
[/GENPROFILE ve/FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/USEPROFILE](reference/useprofile.md)<br/>
