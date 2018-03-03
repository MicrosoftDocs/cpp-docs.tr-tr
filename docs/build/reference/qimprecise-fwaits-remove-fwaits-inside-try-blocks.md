---
title: "-Qimprecise_fwaits (Try blokları içindeki fwaits'i Kaldır) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Qimprecise_fwaits
dev_langs:
- C++
helpviewer_keywords:
- -Qimprecise_fwaits compiler option (C++)
- /Qimprecise_fwaits compiler option (C++)
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 06c93e60530d870b05c601be4980308feb627b46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="qimprecisefwaits-remove-fwaits-inside-try-blocks"></a>/Qimprecise_fwaits (Try Blokları İçindeki fwaits'i Kaldır)
Kaldırır `fwait` komutları için iç `try` engeller kullandığınızda [/fp: dışında](../../build/reference/fp-specify-floating-point-behavior.md) derleyici seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Qimprecise_fwaits  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek etkisizdir **/fp: dışında** de belirtilmedi. Belirtirseniz **/fp: dışında** derleyici seçeneği ekler bir `fwait` komutu her kod satırı geçici bir `try` bloğu. Bu şekilde, derleyici belirli bir özel durum üreten kod satırını tanımlayabilirsiniz. **/ Qimprecise_fwaits** kaldırır iç `fwait` yönergeleri, yalnızca geçici bekler bırakarak `try` bloğu. Bu performansı artırır ancak derleyici yalnızca hangi söyleyin kuramaz `try` bloğu bir özel durum, hangi satır neden olur.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/Q Seçenekler (düşük düzey işlemler)](../../build/reference/q-options-low-level-operations.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)