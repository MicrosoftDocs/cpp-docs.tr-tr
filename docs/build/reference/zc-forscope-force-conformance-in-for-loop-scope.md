---
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
ms.openlocfilehash: 7f98667d3a771994d1b4e54b429f42cb566c102c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810267"
---
# <a name="zcforscope-force-conformance-in-for-loop-scope"></a>/Zc:forScope (Döngü Kapsamında Uyumluluğu Zorla)

Standart C++ davranışını uygulamak için kullanılan [için](../../cpp/for-statement-cpp.md) Microsoft uzantıları ile ([/Ze](za-ze-disable-language-extensions.md)).

## <a name="syntax"></a>Sözdizimi

> **/Zc:forScope**[**-**]

## <a name="remarks"></a>Açıklamalar

Standart bir davranıştır izin vermek için bir **için** döngü Başlatıcısı Git kapsam dışına **için** döngü. Altında **/Zc:forScope-** ve [/Ze](za-ze-disable-language-extensions.md), **için** döngü başlatıcısı, yerel kapsama sonlandırılana kadar kapsam içinde kalır.

**/ZC: forscope** seçeneği varsayılan olarak açıktır. **/ ZC: forscope** zaman etkilenmez [/ permissive-](permissive-standards-conformance.md) seçeneği belirtildi.

**/Zc:forScope-** seçeneği kullanım dışıdır ve gelecek sürümde kaldırılacak. Kullanım **/Zc:forScope-** kullanımdan kaldırma uyarısı D9035 oluşturur.

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

Kullanırsanız **/Zc:forScope-**, C4288 uyarı (varsayılan olarak kapalı) bir değişken, bir önceki kapsamındaki yapılan bildirimi nedeniyle kapsamları dahilinde olması durumunda oluşturulur. Bunu göstermek için kaldırma `//` bildirmek için örnek kod karakter `int i`.

Çalışma zamanı davranışını değiştirebilirsiniz **/ZC: forscope** kullanarak [uygun](../../preprocessor/conform.md) pragması.

Kullanırsanız **/Zc:forScope-** varolan .pch dosyasını içeren bir proje, bir uyarı oluşturulduğu, **/Zc:forScope-** göz ardı edilir ve derleme, var olan .pch dosyaları kullanarak devam eder. Oluşturulan yeni .pch dosyası istiyorsanız kullanın [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](yc-create-precompiled-header-file.md).

Visual C++'ta uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **dil** özellik sayfası.

1. Değiştirme **için döngü kapsamında uyumluluğu zorla** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForceConformanceInForLoopScope%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)<br/>
[/Za, /Ze (Dil Uzantılarını Devre Dışı Bırak)](za-ze-disable-language-extensions.md)<br/>
