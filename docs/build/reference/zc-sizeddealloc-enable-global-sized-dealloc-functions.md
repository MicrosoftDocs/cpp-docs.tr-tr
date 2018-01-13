---
title: "/ZC:sizedDealloc (etkinleştirme genel boyutta ayırmayı kaldırma işlevleri) | Microsoft Docs"
ms.custom: 
ms.date: 12/13/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sizedDealloc
- /Zc:sizedDealloc
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- sizedDealloc
- Enable Global Sized Deallocation Functions
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 3a73ace0-4d36-420a-b699-0ca6fc0dd134
caps.latest.revision: "1"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1343c037f87aee609de2b082cb87f7f1f2832221
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="zcsizeddealloc-enable-global-sized-deallocation-functions"></a>/ZC:sizedDealloc (etkinleştirme genel boyutta ayırmayı kaldırma işlevleri)  
`/Zc:sizedDealloc` Derleyici seçeneği söyler tercihen genel çağırmak için derleyici `operator delete` veya `operator delete[]` türünde ikinci bir parametresi olan işlevler `size_t` nesnenin boyutu olduğunda kullanılabilir. Bu işlevleri kullanabilecek `size_t` deallocator performansı iyileştirmek için parametre.   
  
## <a name="syntax"></a>Sözdizimi  
`/Zc:sizedDealloc`[`-`\]  
  
## <a name="remarks"></a>Açıklamalar  
  
C ++ 11'de standart statik üye işlevleri tanımlayabilir `operator delete` ve `operator delete[]` ikinci bir ele `size_t` parametresi. Genellikle bu ile birlikte kullanılan [new işleci](../../cpp/new-operator-cpp.md) daha verimli allocators ve nesne için deallocators uygulamak için işlevleri. Ancak, C ++ 11 genel kapsamlı ayırmayı kaldırma işlevleri eşdeğer bir dizi tanımlamıyor. Türünde ikinci bir parametresi olan C ++ 11, genel ayırmayı kaldırma işlevlerinde `size_t` yerleştirme silme işlevleri olarak kabul edilir. Bunlar, bir boyut bağımsız değişken geçirme açıkça çağrılmalıdır.  
  
C ++ 14 standart derleyici davranışını değiştirir. Genel tanımladığınızda `operator delete` ve `operator delete[]` türünde ikinci bir parametresi ele `size_t`, üye kapsam sürümleri çağrılamaz ve nesnenin boyutu kullanılabilir olduğunda bu işlevleri çağırmak derleyici tercih eder. Derleyici boyutu bağımsız değişkeniyle örtük olarak geçirir. Derleyici ayırması nesnenin boyutu belirleyemediğinde tek bağımsız değişken sürümleri denir. Aksi takdirde, çağrılacak ayırmayı kaldırma işlevi sürümünü seçmek için her zamanki kuralları hala geçerlidir. Genel işlevler çağrıları açıkça belirtilebilir kapsam çözümü işleci eklenerek (`::`) ayırmayı kaldırma işlev çağrısı için.  
  
Varsayılan olarak, Visual Studio 2015'ten başlayarak Visual C++ bu C ++ 14 standart davranışı uygular. Ayarlayarak bu açıkça belirtebilir `/Zc:sizedDealloc` derleyici seçeneği. Bu büyük olasılıkla çiğnemekten temsil eden değişiklik. Kullanmak `/Zc:sizedDealloc-` kodunuzun türünde ikinci bir parametresi kullanın yerleştirme delete işleçleri tanımladığında eski davranışı için koruma seçeneği `size_t`. İkinci parametre türü sahip genel ayırmayı kaldırma işlevlerin varsayılan Visual Studio kitaplık uygulamaları `size_t` tek bir parametre sürümlerini çağırır. Kodunuzu tek tek-parametre genel sağlarsa delete işleci and işleci [] silin, küresel ölçekli ayırmayı kaldırma işlevlerin varsayılan kitaplık uygulamaları genel işlevlerinizi çağırma.  
  
Visual c++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).  
  
## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
2.  Gelen **yapılandırmaları** açılır menü, seçin **tüm yapılandırmaları**.  
3.  Seçin **yapılandırma özellikleri**, **C/C++**, **komut satırı** özellik sayfası.  
4.  Değiştirme **ek seçenekler** eklenecek özellik `/Zc:sizedDealloc` veya `/Zc:sizedDealloc-` ve ardından **Tamam**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)  
[/ZC (Uyumluluk)](../../build/reference/zc-conformance.md)  
