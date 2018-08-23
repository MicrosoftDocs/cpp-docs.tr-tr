---
title: -LN (MSIL modülü Oluştur) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /LN
dev_langs:
- C++
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ca6d1933b684cc574bc4e0107b9f3f30364c908
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609468"
---
# <a name="ln-create-msil-module"></a>/LN (MSIL Modülü Oluştur)
Bir derleme bildirimi çıkış dosyası içine eklenmesi gerektiğini değil belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/LN  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, **/LN** (bir derleme bildirimi, çıktı dosyasına eklenir) etkin değil.  
  
 Zaman **/LN** kullanılan birini [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) seçenekleri de kullanılmalıdır.  
  
 Derleme meta verileri bildiriminde yok. yönetilen bir program, bir modül adı verilir. Derleme yaparsanız [/c (derleme olmadan bağlamayı)](../../build/reference/c-compile-without-linking.md) ve **/LN**, belirtin [noassembly (MSIL modülü Oluştur)](../../build/reference/noassembly-create-a-msil-module.md) çıkış dosyası oluşturmak için bağlayıcı aşamasındadır.  
  
 Derlemeleri oluşturmak için bileşen tabanlı bir yaklaşımda göz atmak istiyorsanız modüller oluşturmak isteyebilirsiniz.  Diğer bir deyişle, türleri yazabilir ve bunları modülleri derleyin.  Ardından, bir derleme bir veya daha fazla modüllerden oluşturabilirsiniz.  Derlemeleri modülleri oluşturma hakkında daha fazla bilgi için bkz. [bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md) veya [Al.exe (Assembly Linker)](/dotnet/framework/tools/al-exe-assembly-linker).  
  
 Bir modül için varsayılan dosya uzantısı .netmodule'dür.  
  
 Visual C++ 2005 önce Visual C++ sürümlerde bir modül oluşturulurken **/clr:noAssembly**.  
  
 Visual C++ bağlayıcı girişi .netmodule dosyaları kabul eder ve bağlayıcı tarafından üretilen çıkış dosyası bir derleme veya .netmodule herhangi bir bağlayıcıya giriş netmodule'leri hiçbir çalışma zamanı bağımlılığa sahip olacaktır.  Daha fazla bilgi için [bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
-   Belirtin [noassembly (MSIL modülü Oluştur)](../../build/reference/noassembly-create-a-msil-module.md) çıkış dosyası oluşturmak için bağlayıcı aşamasındadır.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bu derleyici seçeneğini program aracılığıyla değiştirilemez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)