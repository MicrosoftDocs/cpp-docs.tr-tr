---
title: "-Tc, - Tp,-TC, - TP (kaynak dosya türünü belirtin) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.CompileAs
- VC.Project.VCCLCompilerTool.CompileAs
- /Tp
- /tc
dev_langs: C++
helpviewer_keywords:
- Tp compiler option [C++]
- /Tc compiler option [C++]
- -Tc compiler option [C++]
- source files, specifying to compiler
- Tc compiler option [C++]
- /Tp compiler option [C++]
- -Tp compiler option [C++]
ms.assetid: 7d9d0a65-338b-427c-8b48-fff30e2f9d2b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 69ccd08967d386780744fb85476033430127ba3a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>/Tc, /Tp, /TC, /TP (Kaynak Dosya Türünü Belirtin)
**Tp** seçeneği belirtir `filename` .c uzantısı yoksa olsa bile bir C kaynak dosyasıdır. **/Tp** seçeneği belirtir `filename` .cpp veya .cxx uzantısını olmasa dahi bir C++ kaynak dosyasıdır. Seçenek arasında bir boşluk ve `filename` isteğe bağlıdır. Her bir seçeneğin bir dosyayı belirtir; Ek dosyaları belirtmek için seçeneği yineleyin.  
  
 **TP** ve **/TP** genel çeşitlemelerini olan **tp** ve **/Tp**. Bunlar komut satırında C kaynak dosyaları olarak adlı tüm dosyaları işlemek için derleyici belirtin (**tp**) ya da C++ kaynak dosyaları (**/TP**), komut satırı seçeneği ile ilgili olarak konumunda dikkate almaksızın. Bu genel seçenekleri yoluyla tek dosyada geçersiz kılınabilir **tp** veya **/Tp**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Tcfilename  
/Tpfilename  
/TC  
/TP  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 C veya C++ kaynak dosyası.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, CL .c uzantısına sahip dosyalar C kaynak dosyalarıdır ve C++ kaynak dosyaları .cpp veya .cxx uzantısına sahip dosyalardır varsayar.  
  
 Zaman ya da **TC** veya **Tc** seçeneği belirtildiğinde, tüm belirtimi [/ZC: wchar_t (wchar_t yerel tür olan)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) seçeneği göz ardı edilir.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **Gelişmiş** özellik sayfası.  
  
4.  Değiştirme **derleme olarak** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>.  
  
## <a name="examples"></a>Örnekler  
 CL komut satırını MAIN.c, TEST.prg ve COLLATE.prg tüm C kaynak dosyalarını olduğunu belirtir. CL PRINT.prg tanımaz.  
  
```  
CL MAIN.C /TcTEST.PRG /TcCOLLATE.PRG PRINT.PRG  
```  
  
 CL komut satırını TEST1.c, TEST2.cxx, TEST3.huh ve TEST4.o C++ dosyaları olarak derlenir ve TEST5.z C dosyası olarak derlenmiş belirtir.  
  
```  
CL TEST1.C TEST2.CXX TEST3.HUH TEST4.O /Tc TEST5.Z /TP  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)