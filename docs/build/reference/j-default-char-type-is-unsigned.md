---
title: -J (varsayılan karakter türü imzasız) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned
- VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned
- /j
dev_langs:
- C++
helpviewer_keywords:
- defaults, char type
- char data type
- -J compiler option [C++]
- /J compiler option [C++]
- J compiler option [C++]
- default char type is unsigned
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a93172296b0e2e6d54dc428ffc62812ad979b160
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="j-default-char-type-is-unsigned"></a>/J (Varsayılan Karakter Türü İmzasız)
Varsayılan değişiklikleri `char` gelen yazın `signed char` için `unsigned char`ve `char` türü olduğunda sıfır genişletilmiş devam eder bir `int` türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/J  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa bir `char` değeri olarak bildirilen açıkça `signed`, **/J** seçeneği bu etkilemez ve devam eder ise, değer oturum genişletilmiş bir `int` türü.  
  
 **/J** seçeneği tanımlar `_CHAR_UNSIGNED`, ile kullanılan `#ifndef` varsayılan aralığı tanımlamak için Lımıts.h dosyasındaki `char` türü.  
  
 ANSI C ve C++, belirli bir uygulamasına gerektirmez `char` türü. İngilizce dışında bir dil içine sonunda çevrilir karakter verileriyle çalışırken bu kullanışlı bir seçenektir.  
  
> [!NOTE]
>  ATL/MFC ile Bu derleyici seçeneği kullanırsanız, bir hata oluşturulabilir. Tanımlayarak bu hatayı devre dışı bırakılamadı rağmen `_ATL_ALLOW_CHAR_UNSIGNED`, bu geçici çözüm desteklenmez ve her zaman çalışmayabilir.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  İçinde **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **özellikleri**.  
  
2.  Projedeki **özellik sayfaları** iletişim kutusunda, sol bölmede altında **yapılandırma özellikleri**, genişletin **C/C++** ve ardından **komut satırı**.  
  
3.  İçinde **ek seçenekler** bölmesinde belirtin **/J** derleyici seçeneği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Proje Özellikleriyle Çalışma](../../ide/working-with-project-properties.md)