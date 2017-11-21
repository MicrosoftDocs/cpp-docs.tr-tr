---
title: "-Fd (Program veritabanı dosya adı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /FD
- VC.Project.VCCLWCECompilerTool.ProgramDataBaseFileName
- VC.Project.VCCLCompilerTool.ProgramDataBaseFileName
dev_langs: C++
helpviewer_keywords:
- /FD compiler option [C++]
- program database file name [C++]
- -FD compiler option [C++]
- PDB files, creating
- program database compiler option [C++]
- .pdb files, creating
- FD compiler option [C++]
ms.assetid: 3977a9ed-f0ac-45df-bf06-01cedd2ba85a
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 09873f44fbf37650e8747afd3fc19aba81603dc1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fd-program-database-file-name"></a>/Fd (Program Veritabanı Dosya Adı)
Tarafından oluşturulan program veritabanı (PDB) dosyası için bir dosya adı belirtir [/Z7, / zi, /zı (hata ayıklama bilgileri biçimi)](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Fdpathname  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Olmadan **/Fd**, PDB dosya adı VC için varsayılan olarak*x*0.pdb, burada *x* Visual C++ ana sürümü kullanılıyor.  
  
 (Yolu sona ters eğik çizgiyi) bir dosya adı içermeyen bir yol adı belirtirseniz, derleyici VC adlı bir .pdb dosyası oluşturur*x*0. pdb belirtilen dizindeki.  
  
 Bir uzantıyı içermeyen bir dosya adı belirtirseniz, derleyici .pdb uzantısı olarak kullanır.  
  
 Bu seçenek ayrıca en az yeniden derleme ve artımlı derleme için kullanılan durum (.idb) dosyası olarak adlandırır.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **çıktı dosyaları** özellik sayfası.  
  
4.  Değiştirme **Program veritabanı dosya adı** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ProgramDataBaseFileName%2A>.  
  
## <a name="example"></a>Örnek  
 Bu komut satırı PROG.pdb ve PROG.idb adlı bir .idb dosya adında bir .pdb dosyası oluşturur:  
  
```  
CL /DDEBUG /Zi /FdPROG.PDB PROG.CPP  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıktı dosyası (/ F) seçenekleri](../../build/reference/output-file-f-options.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Yol adını belirtme](../../build/reference/specifying-the-pathname.md)