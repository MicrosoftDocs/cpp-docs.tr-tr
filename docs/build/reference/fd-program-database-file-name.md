---
description: Şu konuda daha fazla bilgi edinin:/FD (program veritabanı dosya adı)
title: /Fd (Program Veritabanı Dosya Adı)
ms.date: 11/04/2016
f1_keywords:
- /FD
- VC.Project.VCCLWCECompilerTool.ProgramDataBaseFileName
- VC.Project.VCCLCompilerTool.ProgramDataBaseFileName
helpviewer_keywords:
- /FD compiler option [C++]
- program database file name [C++]
- -FD compiler option [C++]
- PDB files, creating
- program database compiler option [C++]
- .pdb files, creating
- FD compiler option [C++]
ms.assetid: 3977a9ed-f0ac-45df-bf06-01cedd2ba85a
ms.openlocfilehash: 3990cdd6c560dfdeaef7078a29e965831c2a9504
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200669"
---
# <a name="fd-program-database-file-name"></a>/Fd (Program Veritabanı Dosya Adı)

[/Z7,/Zi,/ZI (hata ayıklama bilgileri biçimi)](z7-zi-zi-debug-information-format.md)tarafından oluşturulan program VERITABANı (pdb) dosyası için bir dosya adı belirtir.

## <a name="syntax"></a>Syntax

```
/Fdpathname
```

## <a name="remarks"></a>Açıklamalar

**/FD** olmadan, pdb dosya adı varsayılan olarak VC *x* 0. pdb ' dir; burada *x* kullanılan Visual C++ ana sürümüdür.

Bir dosya adı içermeyen bir yol adı belirtirseniz (yol ters eğik çizgiyle biter), derleyici belirtilen dizinde VC *x* 0. pdb adlı bir. pdb dosyası oluşturur.

Uzantı içermeyen bir dosya adı belirtirseniz, derleyici uzantı olarak. pdb kullanır.

Bu seçenek, en az yeniden oluşturma ve artımlı derleme için kullanılan durum (. idb) dosyasını da adlandırır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Çıkış dosyaları** Özellik sayfasına tıklayın.

1. **Program veritabanı dosya adı** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ProgramDataBaseFileName%2A>.

## <a name="example"></a>Örnek

Bu komut satırı, PROG. pdb adlı bir. pdb dosyası ve program. IDB adlı bir. IDB dosyası oluşturur:

```
CL /DDEBUG /Zi /FdPROG.PDB PROG.CPP
```

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı dosyası (/F) seçenekleri](output-file-f-options.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[Yol adını belirtme](specifying-the-pathname.md)
