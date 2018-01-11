---
title: "-V (sürüm numarası) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /v
dev_langs: C++
helpviewer_keywords:
- embedding version strings
- /V compiler option [C++]
- version numbers, specifying for .obj
- V compiler option [C++]
- -V compiler option [C++]
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9a940000b5330c4eccdcabcc5a31f0c3e3e74d65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="v-version-number"></a>/V (Sürüm Numarası)
Kullanım dışı. Bir metin dizesi .obj dosyasında katıştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Vstring  
```  
  
## <a name="arguments"></a>Arguments  
 `string`  
 Sürüm numarası veya telif hakkı bildirimi .obj dosyasında katıştırılmış belirten bir dize.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir sürüm numarası veya telif hakkı uyarısı .obj dosyasıyla stringcan etiketi. Dizesinin bir parçası ise herhangi bir alan veya sekme karakteri çift tırnak işaretleri (") içine alınması gerekir. Ters eğik çizgi (\\) dizesinin bir parçası olması durumunda tüm çift tırnak işareti gelmelidir. Arasında bir boşluk **/V** ve `string` isteğe bağlıdır.  
  
 Aynı zamanda [Açıklama (C/C++)](../../preprocessor/comment-c-cpp.md) derleyici adını ve sürüm numarasını .obj dosyasında yerleştirmek için derleyici açıklama tür bağımsız değişkeni ile.  
  
 **/V** seçeneği Visual Studio 2005'te; itibaren kullanım dışıdır **/V** öncelikle olan sanal aygıt sürücüleri (VXD) oluşturulmasını desteklemede kullanılan ve vxd oluşturma Visual C++ araç takımı tarafından artık desteklenmektedir. Kullanım dışı derleyici seçeneklerinin listesi için bkz: **kullanım dışı ve kaldırılmış derleyici seçenekleri** içinde [derleyici seçenekleri kategoriye göre listelenen](../../build/reference/compiler-options-listed-by-category.md).  
  
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