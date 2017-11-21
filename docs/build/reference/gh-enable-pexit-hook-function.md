---
title: "-GH (_pexit kanca işlevini etkinleştir) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _pexit
dev_langs: C++
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 620019d8a286fff472d6f4136bae3046556b367a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="gh-enable-pexit-hook-function"></a>/GH (_pexit Kanca İşlevini Etkinleştir)
Çağrıları `_pexit` her yöntemi veya işlev sonunda işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/GH  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `_pexit` İşlevi herhangi bir kitaplığı parçası değil ve sizin için bir tanımını sağlamak üzere kadar `_pexit`.  
  
 Açıkça çağırma planlamıyorsanız `_pexit`, prototip sağlamanız gerekmez. İşlevi aşağıdaki prototipe vardı ve tüm yazmaçların içeriğini girişinde itme gerekir ve Çıkışta değişmeden içerik pop gibi görünmelidir:  
  
```  
void __declspec(naked) _cdecl _pexit( void );  
```  
  
 `_pexit`benzer `_penter`; bkz [/Gh (_penter kanca işlevini etkinleştir)](../../build/reference/gh-enable-penter-hook-function.md) nasıl yazılacağını örneği için bir `_pexit` işlevi.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)