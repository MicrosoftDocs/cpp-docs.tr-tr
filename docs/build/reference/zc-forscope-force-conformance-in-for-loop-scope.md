---
description: 'Daha fazla bilgi edinin:/Zc: forScope (döngü kapsamında uygunluğu zorla)'
title: /Zc:forScope (Döngü Kapsamında Uyumluluğu Zorla)
ms.date: 03/06/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.ForceConformanceInForLoopScope
- VC.Project.VCCLWCECompilerTool.ForceConformanceInForLoopScope
- /zc:forScope
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: 3031f02d-3b14-4ad0-869e-22b0110c3aed
ms.openlocfilehash: 7124bba6608facfea546974cfa40ef9556ff713a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114669"
---
# <a name="zcforscope-force-conformance-in-for-loop-scope"></a>/Zc:forScope (Döngü Kapsamında Uyumluluğu Zorla)

Microsoft uzantılarına sahip döngüler [için](../../cpp/for-statement-cpp.md) standart C++ davranışını uygulamak için kullanılır ([/ze](za-ze-disable-language-extensions.md)).

## <a name="syntax"></a>Syntax

> **/Zc: forScope**[ **-** ]

## <a name="remarks"></a>Açıklamalar

Standart davranış, bir **`for`** döngünün başlatıcısının döngüden sonra kapsam dışına gitmesini sağlamak için kullanılır **`for`** . **/Zc: forScope-** ve [/ze](za-ze-disable-language-extensions.md)altında, **`for`** döngünün başlatıcısı yerel kapsam bitene kadar kapsamda kalır.

**/Zc: forScope** seçeneği varsayılan olarak açık. **/Zc:** [/Permissive-](permissive-standards-conformance.md) seçeneği belirtildiğinde forScope etkilenmez.

**/Zc: forScope-** seçeneği kullanım dışıdır ve gelecek sürümlerde kaldırılır. **/Zc: forScope kullanımı-** kullanımdan kaldırma Uyarısı D9035 oluşturur.

Aşağıdaki kod **/ze** altında derlenir ancak **/za** altında değildir:

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

**/Zc: forScope-** kullanırsanız, bir değişken önceki bir kapsamda yapılan bir bildirim nedeniyle kapsam içinde olduğunda uyarı C4288 (varsayılan olarak kapalı) oluşturulur. Bunu göstermek için, `//` örnek kodda bildirmek üzere karakterleri kaldırın `int i` .

[Uygun](../../preprocessor/conform.md) pragmayı kullanarak **/Zc: forScope** öğesinin çalışma zamanı davranışını değiştirebilirsiniz.

Varolan bir. pch dosyasına sahip bir projede **/Zc: forScope** kullanırsanız, bir uyarı oluşturulur, **/Zc: forScope-** yok sayılır ve derleme mevcut. pch dosyalarını kullanarak devam eder. Yeni bir. pch dosyası oluşturulmasını istiyorsanız [/Yıc (önceden derlenmiş üst bilgi dosyası oluştur)](yc-create-precompiled-header-file.md)seçeneğini kullanın.

Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **dil** özellik sayfasını seçin.

1. **Döngü kapsamı Için zorla uygunluğu** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForceConformanceInForLoopScope%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)<br/>
[/Za,/Ze (dil uzantılarını devre dışı bırak)](za-ze-disable-language-extensions.md)<br/>
