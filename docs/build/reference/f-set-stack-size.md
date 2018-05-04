---
title: -F (yığın boyutunu Ayarla) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /f
dev_langs:
- C++
helpviewer_keywords:
- set stack size compiler option
- F compiler option [C++]
- -F compiler option [C++]
- /F compiler option [C++]
- stack, setting size
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed0ad03d18493cc5618f9aad2a16b07e4a01717f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="f-set-stack-size"></a>/F (Yığın Boyutunu Ayarla)
Program yığın boyutunu bayt cinsinden ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/F number  
```  
  
## <a name="arguments"></a>Arguments  
 `number`  
 Yığın boyutunu bayt cinsinden.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek olmadan yığın boyutu 1 MB ile varsayılan olarak ayarlanır. `number` Bağımsız değişken ondalık veya dil C gösterimi olabilir. Bağımsız değişkeni 1'den bağlayıcı tarafından kabul maksimum yığın boyutu değişebilir. Bağlayıcı yakın 4 bayt belirtilen değere yukarı yuvarlar. Kenar boşlukları arasındaki boşluğu **/F** ve `number` isteğe bağlıdır.  
  
 Programınızı yığın taşması iletileri alırsa yığın boyutunu artırın gerekebilir.  
  
 Ayrıca yığın boyutunu da ayarlayabilirsiniz:  
  
-   Kullanarak **/yığın** bağlayıcı seçeneği. Daha fazla bilgi için bkz: [/yığın](../../build/reference/stack.md).  
  
-   EDITBIN .exe dosyası kullanıyor. Daha fazla bilgi için bkz: [EDITBIN başvurusu](../../build/reference/editbin-reference.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)