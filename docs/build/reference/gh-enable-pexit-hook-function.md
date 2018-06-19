---
title: -GH (_pexit kanca işlevini etkinleştir) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _pexit
dev_langs:
- C++
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57e11c27af36eb539b22f3833a73341ff3065e97
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374511"
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
  
 `_pexit` benzer `_penter`; bkz [/Gh (_penter kanca işlevini etkinleştir)](../../build/reference/gh-enable-penter-hook-function.md) nasıl yazılacağını örneği için bir `_pexit` işlevi.  
  
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