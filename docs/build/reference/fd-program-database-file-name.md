---
title: -Fd (Program veritabanı dosya adı) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /FD
- VC.Project.VCCLWCECompilerTool.ProgramDataBaseFileName
- VC.Project.VCCLCompilerTool.ProgramDataBaseFileName
dev_langs:
- C++
helpviewer_keywords:
- /FD compiler option [C++]
- program database file name [C++]
- -FD compiler option [C++]
- PDB files, creating
- program database compiler option [C++]
- .pdb files, creating
- FD compiler option [C++]
ms.assetid: 3977a9ed-f0ac-45df-bf06-01cedd2ba85a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cfa59f889c472651eb40ddcf297ca51bd34f4e41
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389947"
---
# <a name="fd-program-database-file-name"></a>/Fd (Program Veritabanı Dosya Adı)

Tarafından oluşturulan program veritabanı (PDB) dosyası için bir dosya adı belirtir [/z7, / zi, /zı (hata ayıklama bilgileri biçimi)](../../build/reference/z7-zi-zi-debug-information-format.md).

## <a name="syntax"></a>Sözdizimi

```
/Fdpathname
```

## <a name="remarks"></a>Açıklamalar

Olmadan **/Fd**, PDB dosya adı varsayılan olarak, VC için*x*0.pdb, burada *x* önemli Visual C++ sürümü kullanılıyor.

Bir dosya adı (yol sona eğik çizgi) içermeyen bir yol adı belirtirseniz, derleyici, VC adlı bir .pdb dosyası oluşturur.*x*belirtilen dizindeki 0. pdb.

Bir uzantı içermeyen bir dosya adı belirtirseniz, derleyicinin .pdb bir uzantısı olarak kullanır.

Bu seçenek ayrıca en az yeniden derleme ve artımlı derleme için kullanılan durum (.idb) dosyasını adlandırır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **Çıkış dosyalarını** özellik sayfası.

1. Değiştirme **Program veritabanı dosya adı** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ProgramDataBaseFileName%2A>.

## <a name="example"></a>Örnek

Bu komut satırı PROG.pdb ve PROG.idb adlı .idb dosyası adlı bir .pdb dosyası oluşturur:

```
CL /DDEBUG /Zi /FdPROG.PDB PROG.CPP
```

## <a name="see-also"></a>Ayrıca Bkz.

[Çıktı Dosyası (/F) Seçenekleri](../../build/reference/output-file-f-options.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Yol Adını Belirtme](../../build/reference/specifying-the-pathname.md)