---
title: "-Zl (varsayılan kitaplık adını atla) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /zi
- VC.Project.VCCLCompilerTool.OmitDefaultLibName
dev_langs: C++
helpviewer_keywords:
- -Zl compiler option [C++]
- ZI compiler option
- Omit Default Library Name compiler option
- /Zl compiler option [C++]
- default libraries, omitting names
ms.assetid: b27d39d0-44d6-498c-84ae-27c1326fee59
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b77b9c1033be1f6144d92b6051118ca85aaaf20
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="zl-omit-default-library-name"></a>/Zl (Varsayılan Kitaplık Adını Atla)
Varsayılan C çalışma zamanı kitaplığı adı .obj dosyasından atlar. Varsayılan olarak, derleyici kitaplığının adı doğru kitaplık bağlayıcıya yönlendirmek için .obj dosyasına yerleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Zl  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan kitaplık hakkında daha fazla bilgi için bkz: [çalışma zamanı kitaplığını kullan](../../build/reference/md-mt-ld-use-run-time-library.md).  
  
 Kullanabileceğiniz **/Zl** planladığınız bir kitaplık içine yerleştirilecek .obj dosyaları derlemek için. Kaydedilen toplam alan kitaplık adını atlama az miktarda alan tek .obj dosyası kaydeder rağmen birçok nesne modül içeren kitaplığa önemlidir.  
  
 Bu seçenek Gelişmiş bir seçenektir. Bu seçeneğin ayarlanması, bağlantı zamanı, uygulamanız bu desteği bağımlıysa sonuçlanan uygulamanız tarafından gerekli kılınabilen bazı C çalışma zamanı kitaplık desteği kaldırır. Bu seçeneği kullanırsanız, gerekli bileşenleri başka bir şekilde sağlamanız gerekir.  
  
 Kullanım [/NODEFAULTLIB (kitaplıkları yoksay)](../../build/reference/nodefaultlib-ignore-libraries.md). Kitaplık yoksaymak için bağlayıcı yönlendirmek için tüm .obj dosyaları başvurur.  
  
 Daha fazla bilgi için bkz: [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).  
  
 İle derleme yapılırken **/Zl**, `_VC_NODEFAULTLIB` tanımlanır.  Örneğin:  
  
```  
// vc_nodefaultlib.cpp  
// compile with: /Zl  
void Test() {  
   #ifdef _VC_NODEFAULTLIB  
      int i;  
   #endif  
  
   int i;   // C2086  
}  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **Gelişmiş** özellik sayfası.  
  
4.  Değiştirme **varsayılan kitaplık adları atlayın** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)