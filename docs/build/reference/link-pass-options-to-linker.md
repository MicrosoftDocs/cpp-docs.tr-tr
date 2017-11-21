---
title: "-bağlantı (geçiş seçenekleri bağlayıcıya) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /link
dev_langs: C++
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e2a193ff5f1e76d4e7ceb160325c1e748634c3a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="link-pass-options-to-linker"></a>/link (Seçenekleri Bağlayıcıya Geçir)
Bir veya daha fazla bağlayıcı seçenekleri bağlayıcıya geçirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/link linkeroptions  
```  
  
## <a name="arguments"></a>Arguments  
 `linkeroptions`  
 Bağlayıcı seçeneği veya bağlayıcıya geçirilecek seçenekleri.  
  
## <a name="remarks"></a>Açıklamalar  
 **/Link** seçeneği ve bağlayıcı seçenekleri herhangi dosya adları ve CL seçenekleri sonra görünmelidir. Bir arasında gerekli bir alandır **/link** ve `linkeroptions`. Daha fazla bilgi için bkz: [bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Bağlayıcı özellik sayfasını tıklatın.  
  
4.  Bir veya daha fazla özelliklerini değiştirin.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bu derleyici seçeneği programlı olarak değiştirilemez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)