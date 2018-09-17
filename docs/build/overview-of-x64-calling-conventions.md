---
title: Genel Bakış x64 çağırma kuralları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a05db5eb-0844-4d9d-8b92-b1b2434be0ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e70f4017cb31fcc76b1cf3ef2a77d3a28e31bd28
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707999"
---
# <a name="overview-of-x64-calling-conventions"></a>x64 Çağırma Kurallarına Genel Bakış

İki önemli fark x86 x64 arasındaki 64-bit adresleme yeteneği olan ve genel kullanım için 16 64-bit düz bir dizi kaydeder. Genişletilen kayıt kümesine göz önünde bulundurulduğunda, x64 kullanan [__fastcall](../cpp/fastcall.md) çağırma kuralı ve bir risk tabanlı özel durum işleme modeli. `__fastcall` Kuralı kayıtlara ilk dört bağımsız değişken ve yığın çerçevesi için ek bağımsız değişkenleri geçirmek için kullanılır.

Aşağıdaki derleyici seçeneği, uygulamanız için x64 iyileştirmenize yardımcı olur:

- [/favor (Mimari Özellikleri için İyileştirme)](../build/reference/favor-optimize-for-architecture-specifics.md)

## <a name="calling-convention"></a>Çağırma kuralı

Varsayılan olarak x64 dört kaydı bir hızlı arama çağırma kuralı tarafından uygulama ikili arabirimi (ABI) kullanır. Çağrı yığınındaki bir gölge depolama için bu kayıtları kaydetmek çağrılanlar olarak ayrılmış alanı. Bir işlev çağrısı için bağımsız değişkenler ve bu bağımsız değişkenler için kullanılan kasalar arasında katı bire bir ilişkisi yoktur. 8 baytlık uygun olmayan veya 1, 2, 4 veya 8 bayt olmayan herhangi bir bağımsız değişken başvuruyla geçirildi gerekir. Tek bir bağımsız değişken birden çok kayıt arasında yaymaya girişimi yoktur. X87 yazmaç yığını kullanılmayan. Aranan tarafından kullanılabilir, ancak işlev çağrıları arasında geçici olarak düşünülmelidir. Tüm kayan nokta işlemleri gerçekleştirilir XMM 16 kullanarak kaydeder. Tamsayı bağımsız değişkenleri RCX, RDX, R8 ve R9 yazmaçlarında geçirilir. Kayan nokta bağımsız değişkenler XMM0L, XMM1L, XMM2L ve XMM3L geçirilir. 16 bayt bağımsız değişkenleri başvuruya göre iletilir. Parametre geçirme ayrıntılı olarak açıklanan [parametre geçirerek](../build/parameter-passing.md). Bu kayıtları yanı sıra RAX'daki, R10 R11 XMM4 ve XMM5 geçici olarak kabul edilir. Geçici olmayan diğer tüm kayıtlar. YAZMAÇ kullanımı ayrıntılı olarak belgelenmiştir [kaydetme kullanım](../build/register-usage.md) ve [çağıran/çağrılan kaydedilmiş kayıtları](../build/caller-callee-saved-registers.md).

Çağıranın alanı parametreleri için çağrılanın sorumlu olan ve çağrılan diğer birçok bir parametre almasa bile her zaman dört kayıt parametreleri depolamak için yeterli alan ayırmanız gerekir. Bu, prototipi oluşturulmamış C dili işlevler ve vararg C/C++ işlevleri için destek kolaylaştırır. Vararg veya prototipi oluşturulmamış işlevler için herhangi bir kayan nokta değerleri gereken yinelenen karşılık gelen genel amaçlı kayıt defterinde. İlk dört ötesinde herhangi bir parametre çağrıdan önce ilk dört için gölge depolama yukarıda yığında depolanmış olması gerekir. Vararg işlev ayrıntıları bulunabilir [Varargs](../build/varargs.md). Prototipi oluşturulmamış işlevi bilgileri ayrıntılı olarak [prototipi oluşturulmamış işlevler](../build/unprototyped-functions.md).

## <a name="alignment"></a>Hizalama

Çoğu yapıları, doğal hizalama hizalanır. Birincil özel durumlar ve yığın işaretçisi olan ve `malloc` veya `alloca` bellek, performansa yardımcı olmak için 16 bayt ile hizalanır. 16 bayt üzerindeki hizalama el ile yapılması gerekir, ancak 16 bayt XMM işlemleri için ortak bir hizalama boyutu olduğundan, bu çoğu kodunu çalışması gerekir. Yapı düzeni ve hizalama hakkında daha fazla bilgi için bkz. [türler ve depolama](../build/types-and-storage.md). Yığın düzeni hakkında daha fazla bilgi için bkz. [yığın kullanımı](../build/stack-usage.md).

## <a name="unwindability"></a>Unwindability

Yaprak, herhangi bir geçici olmayan kayıtları değiştirmeyin işlevleri işlevlerdir. Bir yaprak olmayan işlev geçici olmayan RSP, örneğin, bir işlev çağırmanın veya yerel değişkenler için ek yığın alanı ayırma değişebilir. Bir özel durum işlendiğinde geçici olmayan kayıtları kurtarmak için yaprak olmayan işlevler düzgün rastgele bir yönerge işlevi geriye doğru izleme işlemini açıklamaktadır statik veriler ile Açıklama eklenmelidir. Bu veri olarak depolanır *pdata*, veya sırayla başvuran yordamı veri *xdata*, veri işleme özel durum. Xdata geriye doğru izleme bilgileri içerir ve ek pdata veya bir özel durum işleyici işlevine işaret edebilir. Açıklanabilmeleri başlangıçları xdata içinde düzgün bir şekilde açıklandığı gibi olması için ileri derecede kısıtlı. Yığın işaretçisi yaprak işlevlerinde dışında bir bitiş veya giriş parçası olmayan kod herhangi bir bölgedeki 16 bayt hizalı olmalıdır. Yaprak işlevleri pdata ve xdata gerekli değildir, dolayısıyla yalnızca bir dönüş benzetimini yaparak sapmasına. İşlev açıklanabilmeleri ve sonuç uygun yapısı hakkında daha fazla ayrıntı için bkz: [giriş ve bitiş](../build/prolog-and-epilog.md). Özel durum işleme ve özel durum işleme ve pdata xdata ve geriye doğru izleme hakkında daha fazla bilgi için bkz. [özel durum işleme (x64)](../build/exception-handling-x64.md).

## <a name="see-also"></a>Ayrıca Bkz.

[x64 Yazılım Kuralları](../build/x64-software-conventions.md)