---
title: '/ ZC: sizeddealloc (Global boyutlu ayırmayı kaldırma işlevlerini etkinleştir)'
ms.date: 03/06/2018
f1_keywords:
- sizedDealloc
- /Zc:sizedDealloc
helpviewer_keywords:
- -Zc compiler options (C++)
- sizedDealloc
- Enable Global Sized Deallocation Functions
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 3a73ace0-4d36-420a-b699-0ca6fc0dd134
ms.openlocfilehash: 160e90f0b068da6fe8330ac97dfd8bda52f05a38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536610"
---
# <a name="zcsizeddealloc-enable-global-sized-deallocation-functions"></a>/ ZC: sizeddealloc (Global boyutlu ayırmayı kaldırma işlevlerini etkinleştir)

**/ZC: sizeddealloc** derleyici seçeneği tercihen genel çağırmak için derleyiciye `operator delete` veya `operator delete[]` türünde ikinci bir parametreye sahip işlevler `size_t` nesnenin boyutu ne zaman kullanılabilir. Bu işlevler kullanabilir `size_t` birleştiricinin performansını iyileştirmek için parametre.

## <a name="syntax"></a>Sözdizimi

> **/ ZC: sizeddealloc**[**-**]

## <a name="remarks"></a>Açıklamalar

C ++ 11'de standart statik üye işlevleri tanımlayabilir `operator delete` ve `operator delete[]` saniyenin ele `size_t` parametresi. Genellikle bunlar birlikte kullanılır [new işleci](../../cpp/new-operator-cpp.md) daha verimli ayırıcılar ve nesne için deallocators uygulamak için işlevleri. Ancak, C ++ 11 ayırmayı kaldırma işlevlerini genel kapsamda eşdeğer bir kümesini tanımlamıyor. Türünde ikinci bir parametreye sahip C ++ 11, genel ayırmayı kaldırma işlevlerini de `size_t` yerleştirme delete işlevleri olarak kabul edilir. Bunlar, bir boyut bağımsız değişkeni geçirerek açıkça çağrılmalıdır.

C ++ 14 standart derleyici davranışını değiştirir. Genel tanımladığınızda `operator delete` ve `operator delete[]` türünde ikinci bir parametre alır `size_t`, derleyici üye kapsamı sürümleri çağrılmayacağı ve nesnenin boyutu kullanılabilir olduğunda bu işlevleri çağırmak tercih eder. Derleyici örtük olarak bir boyut bağımsız değişkeni geçirir. Derleyici serbest bırakılmakta nesnenin boyutunu belirlerken tek bağımsız değişken sürümleri çağrılır. Aksi takdirde, ayırmayı kaldırma işlevi çağırmak için sürümünü seçmek için genel kurallar hala geçerlidir. Genel işlevler için çağrıları açıkça belirtilebilir kapsam çözümleme işleci eklenerek (`::`) ayırmayı kaldırma işlevi çağrısı için.

Varsayılan olarak, Visual C++ Visual Studio 2015'ten başlayarak, bu C ++ 14 standart davranışı uygular. Ayarlayarak bunu açıkça belirtebilirsiniz **/ZC: sizeddealloc** derleyici seçeneği. Bu büyük olasılıkla bozucu temsil eder. değişiklik. Kullanma **/Zc:sizedDealloc-** kodunuzu türünde ikinci bir parametre kullanın yerleştirme delete işleçleri tanımladığında eski davranışı için koruma seçeneği `size_t`. Varsayılan Visual Studio kitaplığı uygulamaları ikinci parametre türü olan genel ayırmayı kaldırma işlevlerini `size_t` tek parametre sürümleri çağırır. Kodunuzu tek tek-parametre genel sağlarsa delete işleci ve operator delete [], global boyutlu ayırmayı kaldırma işlevlerini varsayılan kitaplık uygulamaları genel işlevlerinizi çağırma.

**/ZC: sizeddealloc** derleyici seçeneği varsayılan olarak açıktır. [/ Permissive-](permissive-standards-conformance.md) seçeneği etkilemez **/ZC: sizeddealloc**.

Visual C++'ta uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Gelen **yapılandırmaları** açılır menü öğesini **yapılandırmalarında**.

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/ZC: sizeddealloc** veya **/Zc:sizedDealloc-** seçip **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>
