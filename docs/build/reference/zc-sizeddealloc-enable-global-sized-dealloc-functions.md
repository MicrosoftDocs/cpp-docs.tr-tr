---
title: "/ZC:sizedDealloc (etkinleştirme genel boyutta ayırmayı kaldırma işlevleri) | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- sizedDealloc
- /Zc:sizedDealloc
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- sizedDealloc
- Enable Global Sized Deallocation Functions
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 3a73ace0-4d36-420a-b699-0ca6fc0dd134
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df3ae48e0d83fc0e0bd0f0b34b5c84c78d069a22
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="zcsizeddealloc-enable-global-sized-deallocation-functions"></a>/ZC:sizedDealloc (etkinleştirme genel boyutta ayırmayı kaldırma işlevleri)

**/Zc:sizedDealloc** derleyici seçeneği söyler tercihen genel çağırmak için derleyici `operator delete` veya `operator delete[]` türünde ikinci bir parametresi olan işlevler `size_t` nesnenin boyutu olduğunda kullanılabilir. Bu işlevleri kullanabilecek `size_t` deallocator performansı iyileştirmek için parametre.

## <a name="syntax"></a>Sözdizimi

> **/Zc:sizedDealloc**[**-**]

## <a name="remarks"></a>Açıklamalar

C ++ 11'de standart statik üye işlevleri tanımlayabilir `operator delete` ve `operator delete[]` ikinci bir ele `size_t` parametresi. Genellikle bu ile birlikte kullanılan [new işleci](../../cpp/new-operator-cpp.md) daha verimli allocators ve nesne için deallocators uygulamak için işlevleri. Ancak, C ++ 11 genel kapsamlı ayırmayı kaldırma işlevleri eşdeğer bir dizi tanımlamıyor. Türünde ikinci bir parametresi olan C ++ 11, genel ayırmayı kaldırma işlevlerinde `size_t` yerleştirme silme işlevleri olarak kabul edilir. Bunlar, bir boyut bağımsız değişken geçirme açıkça çağrılmalıdır.

C ++ 14 standart derleyici davranışını değiştirir. Genel tanımladığınızda `operator delete` ve `operator delete[]` türünde ikinci bir parametresi ele `size_t`, üye kapsam sürümleri çağrılamaz ve nesnenin boyutu kullanılabilir olduğunda bu işlevleri çağırmak derleyici tercih eder. Derleyici boyutu bağımsız değişkeniyle örtük olarak geçirir. Derleyici ayırması nesnenin boyutu belirleyemediğinde tek bağımsız değişken sürümleri denir. Aksi takdirde, çağrılacak ayırmayı kaldırma işlevi sürümünü seçmek için her zamanki kuralları hala geçerlidir. Genel işlevler çağrıları açıkça belirtilebilir kapsam çözümü işleci eklenerek (`::`) ayırmayı kaldırma işlev çağrısı için.

Varsayılan olarak, Visual Studio 2015'ten başlayarak Visual C++ bu C ++ 14 standart davranışı uygular. Ayarlayarak bu açıkça belirtebilir **/Zc:sizedDealloc** derleyici seçeneği. Bu büyük olasılıkla çiğnemekten temsil eden değişiklik. Kullanmak **/Zc:sizedDealloc-** kodunuzun türünde ikinci bir parametresi kullanın yerleştirme delete işleçleri tanımladığında eski davranışı için koruma seçeneği `size_t`. İkinci parametre türü sahip genel ayırmayı kaldırma işlevlerin varsayılan Visual Studio kitaplık uygulamaları `size_t` tek bir parametre sürümlerini çağırır. Kodunuzu tek tek-parametre genel sağlarsa delete işleci and işleci [] silin, küresel ölçekli ayırmayı kaldırma işlevlerin varsayılan kitaplık uygulamaları genel işlevlerinizi çağırma.

**/Zc:sizedDealloc** derleyici seçeneği varsayılan olarak açıktır. [/ İzin veren-](permissive-standards-conformance.md) seçeneği etkilemez **/Zc:sizedDealloc**.

Visual c++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Gelen **yapılandırmaları** açılır menü, seçin **tüm yapılandırmaları**.

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/Zc:sizedDealloc** veya **/Zc:sizedDealloc-** ve ardından **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>
