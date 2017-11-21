---
title: "-LN (MSIL modülü Oluştur) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /LN
dev_langs: C++
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 807fd762ab2780b70a395f62efbc72945228b1fa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ln-create-msil-module"></a>/LN (MSIL Modülü Oluştur)
Derleme bildirimi çıktı dosyasına eklenecek değil olduğunu belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/LN  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, **/LN** (bir derleme bildirimi çıktı dosyasına eklenir) etkin değil.  
  
 Zaman **/LN** kullanılır, aşağıdakilerden birini [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) seçenekleri de kullanılmalıdır.  
  
 Derleme meta verilerini bildiriminde yok yönetilen bir program bir modül adı verilir. İle derleme yaparsanız [/c (derleme olmadan bağlama)](../../build/reference/c-compile-without-linking.md) ve **/LN**, belirtin [/NOASSEMBLY (MSIL modülü Oluştur)](../../build/reference/noassembly-create-a-msil-module.md) çıktı dosyası oluşturmak için bağlayıcı aşamasında.  
  
 Derlemeleri oluşturma için bileşen tabanlı bir yaklaşım uygular istiyorsanız modülleri oluşturmak isteyebilirsiniz.  Diğer bir deyişle, türleri yazar ve modüllerine derleyin.  Ardından, bir veya daha fazla modüllerden bütünleştirilmiş oluşturabilir.  Modüllerden derlemeler oluşturma hakkında daha fazla bilgi için bkz: [bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md) veya [Al.exe (derleme bağlayıcı)](/dotnet/framework/tools/al-exe-assembly-linker).  
  
 Bir modül için varsayılan dosya uzantısı .netmodule ' dir.  
  
 İçinde [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] sürümler Visual C++ 2005 önce bir modülü ile oluşturulmuş **/clr:noAssembly**.  
  
 Visual C++ bağlayıcı .netmodule dosyaları giriş olarak kabul eder ve bağlayıcı tarafından üretilen çıkış dosyası bir derlemeyi ya da hiç çalışma zamanı bağımlılığı herhangi bir bağlayıcıya giriş .netmodules ile .netmodule olacaktır.  Daha fazla bilgi için bkz: [bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
-   Belirtin [/NOASSEMBLY (MSIL modülü Oluştur)](../../build/reference/noassembly-create-a-msil-module.md) çıktı dosyası oluşturmak için bağlayıcı aşamasında.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bu derleyici seçeneği programlı olarak değiştirilemez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)