---
title: / Tc, /Tp, TP, /TP (kaynak dosya türünü belirtin) | Microsoft Docs
ms.date: 1/11/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.CompileAs
- VC.Project.VCCLCompilerTool.CompileAs
- /Tp
- /tc
dev_langs:
- C++
helpviewer_keywords:
- Tp compiler option [C++]
- /Tc compiler option [C++]
- -Tc compiler option [C++]
- source files, specifying to compiler
- Tc compiler option [C++]
- /Tp compiler option [C++]
- -Tp compiler option [C++]
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9cb612d5c26fd4db51222c480539867d5e506b70
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>/Tc, /Tp, /TC, /TP (Kaynak Dosya Türünü Belirtin)

**Tp** seçeneği filename bağımsız değişkeni bir C kaynak dosyası olduğunu belirtir bile .c uzantısı yok. **/Tp** seçeneği filename bağımsız değişkeni bir C++ kaynak dosyası olduğunu belirtir dahi .cpp veya .cxx uzantısına sahip değil. Seçeneğini ve dosya adı arasında bir boşluk isteğe bağlıdır. Her bir seçeneğin bir dosyayı belirtir; Ek dosyaları belirtmek için seçeneği yineleyin.

**TP** ve **/TP** genel çeşitlemelerini olan **tp** ve **/Tp**. Bunlar komut satırında C kaynak dosyaları olarak adlı tüm dosyaları işlemek için derleyici belirtin (**tp**) ya da C++ kaynak dosyaları (**/TP**), komut satırı seçeneği ile ilgili olarak konumunda dikkate almaksızın. Bu genel seçenekleri yoluyla tek dosyada geçersiz kılınabilir **tp** veya **/Tp**.

## <a name="syntax"></a>Sözdizimi

> **TP** _dosya adı_  
> **/TP** _dosya adı_  
> **/TC**  
> **/TP**  

## <a name="arguments"></a>Arguments

*Dosya adı*  
C veya C++ kaynak dosyası.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **CL** .c uzantısına sahip dosyalar C kaynak dosyaları ve .cpp veya .cxx uzantısına sahip dosyaları C++ kaynak dosyaları, varsayar.

Zaman ya da **TC** veya **Tc** seçeneği belirtildiğinde, tüm belirtimi [/ZC: wchar_t (wchar_t yerel tür olan)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) seçeneği göz ardı edilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **Gelişmiş** özellik sayfası.

1. Değiştirme **derleme olarak** özelliği. Seçin **Tamam** veya **Uygula** değişikliklerinizi uygulamak için.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>.

## <a name="examples"></a>Örnekler

Bu CL komut satırı MAIN.c, TEST.prg ve COLLATE.prg tüm C kaynak dosyalarını olduğunu belirtir. CL PRINT.prg tanımaz.

> CL ANA. C /TcTEST.PRG /TcCOLLATE.PRG yazdırma. PRG

Bu CL komut satırı TEST1.c, TEST2.cxx, TEST3.huh ve TEST4.o C++ dosyaları olarak derlenir ve TEST5.z C dosyası olarak derlenmiş belirtir.

> CL TEST1. C TEST2. CXX TEST3. HUH TEST4. O TP TEST5. Z /TP

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)  
