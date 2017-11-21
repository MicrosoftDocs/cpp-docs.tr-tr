---
title: "-Zc: forScope (zorla döngü kapsamında uyumluluğu) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.ForceConformanceInForLoopScope
- VC.Project.VCCLWCECompilerTool.ForceConformanceInForLoopScope
- /zc:forScope
dev_langs: C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: 3031f02d-3b14-4ad0-869e-22b0110c3aed
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 72595581e5054630e761f214c1a30c139fb7b69b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="zcforscope-force-conformance-in-for-loop-scope"></a>/Zc:forScope (Döngü Kapsamında Uyumluluğu Zorla)
Standart C++ davranışını uygulamak için kullanılan [için](../../cpp/for-statement-cpp.md) döngüler Microsoft Uzantıları ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).  **/ ZC: forscope** varsayılan olarak açıktır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Zc:forScope[-]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/Zc:forScope-** seçeneği kullanım dışıdır ve gelecek sürümde kaldırılacak. Kullanımı **/Zc:forScope-** kullanımdan D9035 uyarı oluşturur.  
  
 Standart davranıştır izin vermek için bir **için** döngünün Başlatıcı Git sonra kapsam dışında **için** döngü. Altında **/Zc:forScope-** ve [/Ze](../../build/reference/za-ze-disable-language-extensions.md), **için** döngünün Başlatıcı yerel kapsam sonlanana kadar kapsam içinde kalır.  
  
 Altında aşağıdaki kodu derler **/Ze** ancak altında olmayan **/Za**:  
  
```cpp  
// zc_forScope.cpp  
// compile by using: cl /Zc:forScope- /Za zc_forScope.cpp  
// C2065, D9035 expected  
int main() {  
    // Compile by using cl /Zc:forScope- zc_forScope.cpp  
    // to compile this non-standard code as-is.  
    // Uncomment the following line to resolve C2065 for /Za.  
    // int i;  
    for (int i = 0; i < 1; i++)  
        ;  
    i = 20;   // i has already gone out of scope under /Za  
}  
```  
  
 Kullanırsanız **/Zc:forScope-**, C4288 uyarı (varsayılan olarak kapalıdır) bir değişkeni, önceki bir kapsamda yapılan bir bildirimi nedeniyle kapsamları dahilinde olması durumunda oluşturulur. Bunu göstermek için kaldırma `//` bildirmek için örnek kod karakter `int i`.  
  
 Çalışma zamanı davranışını değiştirebilir **/ZC: forscope** kullanarak [uygun](../../preprocessor/conform.md) pragması.  
  
 Kullanırsanız **/Zc:forScope-** varolan .pch dosyasını sahip bir proje ile bir uyarı üretilir, **/Zc:forScope-** göz ardı edilir ve derleme varolan .pch dosyaları kullanarak devam eder. Oluşturulan yeni bir .pch dosyası istiyorsanız kullanın [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md).  
  
 Visual c++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Gezinti Bölmesi'nde açın **yapılandırma özellikleri**, **C/C++**, **dil** özellik sayfası.  
  
3.  Değiştirme **için döngü kapsamında uyumluluğu zorla** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForceConformanceInForLoopScope%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ZC (Uyumluluk)](../../build/reference/zc-conformance.md)   
 [/ Za, /Ze (dil uzantılarını devre dışı bırak)](../../build/reference/za-ze-disable-language-extensions.md)