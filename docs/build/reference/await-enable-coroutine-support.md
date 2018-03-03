---
title: "-(coroutine desteğini etkinleştir) await | Microsoft Docs"
ms.custom: 
ms.date: 08/15/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /await
- -await
dev_langs:
- C++
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 47134532b16d1b5a907e4ed3170a0827316d7c65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="await-enable-coroutine-support"></a>/ await (coroutine desteğini etkinleştir)  
  
Kullanım **/ await** eş için derleyici desteği etkinleştirmek için derleyici seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
> / bekleme  
  
## <a name="remarks"></a>Açıklamalar  
  
**/ Await** derleyici seçeneği sağlar anahtar sözcükleri ve C++ eş için derleyici desteği **co_await**, **co_yield**, ve **co_return**. Bu seçenek varsayılan olarak etkin değildir. Visual Studio'da eş desteği hakkında daha fazla bilgi için bkz: [Visual Studio Ekip blogu](https://blogs.msdn.microsoft.com/vcblog/category/coroutine/). Eş yordamlar standart teklifi hakkında daha fazla bilgi için bkz: [N4628 çalışma Taslak, eş için C++ uzantıları için teknik belirtim](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/n4628.pdf).  

**/ Await** Visual Studio 2015 başında bir seçenektir.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1. Projenizin açmak **özellik sayfaları** iletişim kutusu.   
  
2. Altında **yapılandırma özellikleri**, genişletin **C/C++** klasör ve **komut satırı** özellik sayfası.  
  
3. Girin **/ await** derleyici seçeneği **ek seçenekler** kutusu. Seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydetmek için.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
  
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)